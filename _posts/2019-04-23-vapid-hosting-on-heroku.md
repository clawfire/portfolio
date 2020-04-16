---
layout:	post
title:	"Vapid hosting on Heroku"
date:	2019-04-23
featured_image: /img/0*UBH0g-fFJ34PfFa1.jpeg
---

#### How to deploy a Vapid website on Heroku and configure the database, transfer your data but still have the file storage issue.

[Vapid](https://www.vapid.com/) is a CMS that provide a dashboard to enter content, run with a lot of different kind of databases and let you do all of that from the HTML you are writing (thanks to [Mustache](http://mustache.github.com)/[Handlebars](https://handlebarsjs.com/) like syntax). It’s my new go for any little side project even if I have one main issue there: Going to production.

Because Vapid is a node package that let you spaw a dev server and works on it but when it comes to production, you have the official paid service (starting at 7$/month/site) which support the dev of the software of course but seems a bit expensive when you compare to all the solutions you have nowadays: Now.sh, Heroku, AWS, …

And since a lot of people are looking about how to deploy on those kinds of services, I gave it a try with Heroku. Here’s my journey.

### Creating a new app

![](/img/1*3JCGVNLZ9FdaagVwbI1MrQ.png)

Let’s start by creating a new app, with the free tiers offered by the services.

That’s enough to start deploying, but then I recommend to switch to a paid plan to keep your site running, otherwise it’s paused between activity period and takes time to boot up again).

Once done, you should add a free *PostgreSQL* add-on. Go into the *Ressources* tab and search for postgres . Take *Heroku Postgres* and choose the *Hobby Dev — free* version.

![](/img/1*5uBTXshd21oocufKqy2UNQ.png)

### Preparing the vapid install

Now, I assume you already have a vapid site locally made and just want to deploy it.

#### Editing the package.json file

Since we’ll use *PostgreSQL* we need to tell vapid that we are using something else than the default *SQLite* database. And since it seems vapid check when starting we are installing the node packages for it (even if we don’t need it here) we’ll add it too.

You should add the dialect config inside vapid section. And we’ll use the environment variable DATABASE\_URL passed by default by Heroku to the application for connexion string.

See the pg dependency? It’s the *PostgreSQL* package I told you before. Sadly I didn’t find a way to get rid of it so far. I opened a bug on Vapid’s Github repo.

#### Deploying the app

Heroku provide 3 deployment methods :

* Using Heroku’s GIT
* Using Github
* Using a container registry
I choose the first one because it’s basically just adding a Heroku remote to your project and you are free to push there whenever you want. Which is really convenient I find.

It takes just a `heroku git:remote -a APPNAME` . That’s it.

Now, I just have to run a git push heroku master and wait a few seconds. My app is now deployed and accessible to the public 🥳.

### Optional: Importing your data

Since I already have some data I input into my Vapid website and didn’t want to have to re-create everything here’s how I did:

1. Connect to SQLite and export data into several CSV files
2. Connect to PostgreSQL and import my files

#### Exporting Data

I’m on a Mac, so I look quickly on the internet and find an SQLite client with GUI called [DB Browser for SQLite](https://sqlitebrowser.org/) which is free 💰.

Open the `data/vapid.sqlite` and then browse each table and export them. I personally went for tableName.csv inside the same data folder. Just to keep organized.

#### Importing Data

That’s a little bit trickier but, don’t panic. First, you have to visit your deployed website and create an admin account. It which build the dashboard and create the different tables into the DB.

Go back on the Heroku admin panel of your app. Find the *Ressources* tab. You should have your *Heroku Postgres* add-on. Click on it to open, in a new window, the admin of this add-on.

![](/img/1*wQOLR88JmSnJRH6pWpIJuw.png)

Into *Settings* tab, you should find a *View Credentials…* button. Click on it!

At the point, I used [Postico](https://eggerapps.at/postico/) which is shareware but works to import my data without having to pay for it. Using the credentials I connect to my Heroku DB and import my CSV files into each table of the PostgreSQL.

That’s all 👍🏼

### The elephant in the room

Nope, I’m not gonna talk about PHP 😅 but fact that you can’t use image datatype with this method. Why? Because [the file storage is ephemeral in Heroku](https://help.heroku.com/K1PPS2WM/why-are-my-file-uploads-missing-deleted). That means each time your app is put in sleep, the file storage is deleted. In fact, your entire app is deleted until someone try to reach it again and then a new container is created and served. Your data into the DB are safe because the DB is not stored on that container but an independent, persistent, service.

What to do then? Storing files on separate file storage seems a good way to go. Unfortunately Vapid doesn’t provide at that time some mechanism to be able to upload elsewhere the data. It shouldn’t be too difficult to do but if they want to be really open to everyone tastes, they will need to develop a connector method or rely on a third-party tool like they did for the database abstraction to be compatible with AWS S3 and other providers.

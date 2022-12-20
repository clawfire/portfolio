---
layout: post
date: 2022-12-20 21:21:45 +0100
published: true
featured_image: "/img/2022/12/christopher-burns-kj2sanhg-hg-unsplash.jpg"
title: How to create a RSS feed bot for Mastodon
description: I wanted to create a bot for Mastodon that read RSS feed and post toots,
  turns out it's super simple and you don't have to know how to code.

---
Everything started from [a toot from Joël](https://chaos.social/@jollysea/109544971382423186) about the new [StroumMonitor](https://zesumme-spueren.lu/resources/stroum-monitor/) from Creos. It's basically a forecast of the electricity network load, and it should help the Luxembourgish residents to adapt their usage depending of it. The forecast comes as a widget you can embed on several websites like [zesumme spueren](https://zesumme-spueren.lu/resources/stroum-monitor/) (save \[energy\] together), an API and a RSS feed.

I took the liberty to [put all of those resources on data.public.lu](https://data.public.lu/fr/datasets/stroummonitor-la-meteo-de-lelectricite-pour-une-consommation-responsable/), the open-data initiative from Luxembourg. If someone from Creos reads this, just create an account, then an organisation, and ping me so I can transfert the dataset to you 🙃.

Ok so, Joël was wondering if we could make a bot, on Mastodon, that would toot about the forecast. I immediately thought about this RSS feed and start assembling something with my favorites no-code tools: Zapier & IFTTT.

## The bot account

First, you need to create a new Mastodon account for your bot. I made one on my own Mastodon instance but you can make it on any server. It’s perfectly fine.

Then, and that’s important Mastodon etiquette here, mark the account as a bot. On Settings -> Profile, check the « this is a bot » checkbox. I would rather recommend too to complete the profile so people will get more confortable with following you.

Now, we need to create a new « app » for our account , in order to get an API key. Still on Settings -> Development -> New app.

You just need a name and to uncheck all the permission except `write`.  More specifically, you can only check `write:statuses`. Leave all the other fields as it is and save.

You now have the application created, and on the details you can see App ID, Secret and Access token. That’s what we gonna need later!

## The no-code service

Okay so, here’s the deal. My favorite service to do that would have been [Zapier](https://zapier.com/). Unfortunately, using Webhooks to post content on Mastodon is a premium feature. While I do have a premium account, I want to show you how to do it for free. So we gonna use the more simple platform [IFTTT](https://ifttt.com/join?referral_code=DPqXQkwEOeVzx-z84a8IlV8il7veJg6P) .

Let’s click « Create »
![](/img/2022/12/ef83f08a-460a-4568-8a2a-5bdb385d25e1.png)
And choose **RSS** for the « If This » part
![](/img/2022/12/3b732382-6a64-4d2c-a170-e0a2d6d41379.png)

Then « New feed item » and paste the RSS url  `https://www.creos-net.lu/rss/stroumMonitor` and click « Create trigger »

![](/img/2022/12/9454416e-d793-4eef-b007-251e0c37e8c8.png)
Now select Add in the « Then That »  part and choose  **Webhooks** and « Make a web request ».  Now fill those fields like instructed below:

* **URL** is `[your instance url]/api/v1/statuses?access_token=[the access token we talked before]`. In my case it’s then `https://m.thibau.lt/api/v1/statuses?access_token=[mytoken]`
* **Method** should be `POST`
* **Content Type** should be `application/json`
* **Additional Headers** should be empty
* **Body** should be your text, using the « add ingredient » button. In my case it’s `[EntryTitle] pour le [EntryContent]`.  Why that? Simply because `EntryTitle` contain the text « Prévisions de la charge nationale »  and the `EntryContent` is date and forecast like « Mardi - 20 décembre 2022 - Statut vert : Système électrique en équilibre - Soyons toutefois conscients de notre consommation »

Save and … TADAAAA

So, bit of explanation here. For every new RSS item, IFTTT will send a `POST` request to your Mastodon instance, to the statuses (toots) endpoint, using your access token so the server will know where to write the toot. That’s all.

## Going further & ressources

Obviously you can adapt this with any kind of trigger you want, thanks to the power of IFTTT. New tweet, new Facebook Status, new email received … or new reading in some smart IoT device.

I put under the ressources to the Creos open-data on the Luxembourgish portal, and my reuse. If you wanna check on it 😃.

<div data-udata-dataset="63a1c7fc95d5ae2ad821ede7"></div><script src="https://data.public.lu/static/oembed.js" async defer></script>

<div data-udata-reuse="63a1c95595d5ae2ad821ede8"></div><script src="https://data.public.lu/static/oembed.js" async defer></script>

**Disclamer**
IFTT Link  are referral, I’ll get 10% off my subscription if and only if you subscribe for a paid plan.
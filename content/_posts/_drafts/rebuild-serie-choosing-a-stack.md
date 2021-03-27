---
layout: post
date: 2020-03-22 16:41:30 +0100
published: false
featured_image: ''
title: 'Rebuild Serie: Choosing a Stack'
description: 'On this first post, I''ll talk about my journey of finding the right
  stack to host my existing and future content. '

---
_This post is part of the_ [_Rebuilding my Portfolio_](https://thibaultmilan.com/blog/rebuilding-my-portfolio-serie) _series._

First, I checked what tools I already know:

* Wordpress is an easy answer for blogging. I moved from dotclear to Wordpress years ago. But Wordpress feels heavy. You can’t run it on small instances nowadays. It’s too heavy and, in a way, bloated.
* Ghost. A Ruby alternative, built with the UX of Medium.com in mind. I do love that one, even had a paid account a couple of years, supporting the development of the solution. But I’m not a ruby guy and a bit lazy about learning how to keep it running. Plus, the hosting on Simple Hosting by Gandi is over complicated for a newbie like me.
* [Jekyll](https://jekyllrb.com/), a static content site generator I know from a couple of years and I played with by the time I was looking to something more potent that Github Pages (the basic versions. The elaborate one allow you to build a website with Jekyll and host it. I ran a Personal blog on that for a couple of years. It’s all free 😁)
* [Vapid](https://www.vapid.com/). A static site generator with an admin (which is not provided by Jekyll, you have to write markdown files, then compile them manually into HTML code and upload it). It’s tempting, but I found too many limitations. And the admin is defined by the code you put into your “code” so it’s not a templating engine as we know it.

There was a 5th option, to be honest: finding a new promising and exciting tool to try, and run into it. Losing myself in very deceptive results and wasting my time 😁 That’s quite tempting 😜

## Jekyll

I decided to proceed with Jekyll for multiple reasons:

1. I don’t want server-side processing. Bye-bye PHP. I loved you but we have grown apart and now I’m like ... I can still write code but I don’t love doing it. So, exit Wordpress.
2. I don’t want to have to learn a (new) language. I do know Ruby and RoR. I wrote some code years ago. But never went deep with it. So even if Ghost is just a wonderful piece of art regarding the User eXperience, I’m gonna pass. I’m a bit sad, but I know I would require too much attention if I went that way. Starting by finding how the fuck I’m running this on a server 😁
3. I liked [Vapid](https://www.vapid.com/), but as I said, the way of declaring the admin UI inside of your templating code kinda made me feel it's not a good thing. For me. (There's plenty of advantages to [Vapid](https://www.vapid.com/) and the project is very young so there's so much room to do great stuff!).
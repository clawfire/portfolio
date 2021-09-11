---
layout: post
date: 2021-09-11 11:38:35 +0200
published: true
featured_image: "/img/2021/09/firmbee-com-ememmpuojlw-unsplash.jpeg"
title: How to fix Google Drive authorization issues
description: When you upgrade Google File Stream to Google Drive, especially on Big
  Sur, authorization problems may arise. This is how to fix it.

---
When you upgrade Google File Stream to Google Drive, especially on Big Sur, authorization problems may arise. This is how to fix it.

***

When I upgraded to Mac OS Big Sur, at the same time, Google decided to decommission Google File Stream in profit of Google Drive, which should be a nice addition since Google Drive include several new features such as multiple accounts and the ability to sync some of your computer folder with Google Drive (without needing to move those into Google Drive folder).

## So what's the tea?

Well, after upgrading Google File Stream to Google Drive and launching it, you got such an error message :  
![](/img/2021/09/capture-d-ecran-2021-09-10-a-18-12-10.png)

This tells you that you need to authorize some sub-program from Google Drive to run. Since a couple of major versions of Mac OS, Apple now enforce app to be signed or delivered from the Mac App Store to be run without any message. Google chose not to do it (they did do just a self-signature; in fact, which requires you to approve the first run), so that's why you need to confirm the first run.

But, apparently, Google reuse the same app id (`com.google.drive`) so mac OS doesn't display any authorization into the Privacy and Security panel. I thought at first of some app cache issues, but I did remove and clean the leftover of the app and reinstall it to have the same issues.

## How to fix it?

It's pretty straightforward but doesn't feel right at first. Let me explain.

1. Run the new Google Drive app
2. Close the error message
3. On the menubar, select Google Drive and log out. You should find a message inviting you to do so.
4. The app should restart. If not, close it and re-open it.
5. Log in back
6. The app should restart.
7. It works! 
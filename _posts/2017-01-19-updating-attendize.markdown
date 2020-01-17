---
layout:	post
title:	"Updating Attendize"
date:	2017-01-19
featured_image: /img/1*UhmknOr5NgAgICKvrl-52Q.png
---

After having hard time to get it work, I found nearly 0 documentation about how to update it…

I’m using the super duper [Attendize](http://attendize.com), a open-source ticketing system, for some of my activities. After having hard time to get it work, I found nearly 0 documentation about how to update it.

Fortunately, as it’s an open-source software, I was able to open an issue and ask the developer community around this software how to do it.

[Update procedure · Issue #285 · Attendize/Attendize I have 0.8 installed, 1.0 is out but no update procedure anywhere. Any clues ?](https://github.com/Attendize/Attendize/issues/285#issuecomment-272705469)

So, in order to update your installation you have to :

1. Copy over files with the newer version (via SFTP)
2. Log-in with `ssh` to your server and enter `php artisan migrate` into the root folder to launch the database migration.
That’s it 🙌🏼.

I’m a little bit concerned about the FTP / SSH thing in 2017 so I’m gonna look to a better way to do it, with some CI tools to automate the file deployment and command running to migrate DB. Keep you posted 😉

---
title: "Personal Notes - Quick Nginx"
date: 2018-04-05T22:19:44+08:00
draft: false

thumbnailImagePosition: left
thumbnailImage: ./img/nginx.png

categories:
- notes

---


Another quick post on where all the nginx files and what to change:
<!--more-->

Normally Nginx default file goes to here: `/var/www/html/index.nginx-debian.html`

There's a config file which I'm not entirely sure what it does: `/etc/nginx/nginx.conf`

This is the path to look for the **default** file `/etc/nginx/sites-enabled`

Within the default file look for this line, and adjust accordingly `root /var/www/html/XXXXXX;`
(I think there are different server blocks, but that's to figure out for later!)


Once all changed make sure you run these commands

```
sudo service nginx stop
sudo service nginx start
sudo service nginx restart
```


Also, another quick scp thing:

Way to do it:
`scp -r ./folderyouwant alfred@destinationfolder/here`

Example:
`scp -r ./rpage alfred@shiny2.alfredlin.com:/home/alfred`






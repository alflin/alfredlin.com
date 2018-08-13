---
title: "Crowdsourcing Password Webapp"
date: 2018-04-05T22:40:11+08:00

thumbnailImagePosition: left
thumbnailImage: ./free_ofo/ofo_lock.png
image: free_ofo/ofo_lock.png
metaAlignment: center
draft: false
---

I developed a quick and dirty shiny web app that allowed users to crowd source usernames and passwords for the Ofo manual lock bikes.
<!--more-->

![alt text](/free_ofo/freeofo.gif "app")


Tech Stack Used: R, Shiny, Nginx 

Link: [http://shiny2.alfredlin.com/posts/ofo_free/](http://shiny.alfredlin.com/posts/ofo_free/)

Github: [https://github.com/alflin/ofo_free](https://github.com/alflin/ofo_free)

# Background

Ofo is a bike sharing company based in China which at first used manual locks for their bikes. This meant that if you rode the same bike multiple times, you'd just use the same password to open the lock. This is different from the bikes nowadays that use QR codes which allowed for dynamic passwords.

During this time, I thought it'd be cool to build something that would allow users to share their bike numbers and passwords, eventually if there was enough traction, users would just use the webapp and not have to pay.

This was developed a while back in 2016 when I first learned how to use Shiny. I built the app in Chinese as I thought this would only be used in China.


# The App

The front-end is actually quite simple, I mostly just used the DT package (R's interface with datatable library). 

Here's where I used the datatable:

![alt text](/free_ofo/free_ofo_voting.png "datatable")



One thing I realized with DT was that the default language is set in English. This mean the "Next Page" or "Search" text would all show up in English. A quick google search showed that someone has already taken this into account and just an easy change in parameters fixed this:

`language = list(url = '//cdn.datatables.net/plug-ins/1.10.11/i18n/Chinese.json')`


On the input section, I used Shiny's native input widgets which was quite simple to implement:

![alt text](/free_ofo/free_ofo_adding.png "adding")


The extra piece I added was using shinyjs when I realized the app took a while to load (maybe because it reads from a csv rather than from an actual RDS or database file). The shinyjs piece essentially just added an extra splash screen telling the user to wait while the rest of the app loaded.

Here's the picture of the loading screen:

![alt text](/free_ofo/free_ofo_loading.png "loading")


# Some Issues

This was my first time building a webapp with Shiny and on the database section, I actually only used R to write to a CSV file, so this app would not work if there were multiple users who put in entries simultaneously.


# Conclusion

This was a fun little exercise of building a webapp on Shiny using R. Definitely could be cleaned up in-terms of UI and even just adding an actual database. I think the bulk of my time was spent on figuring out how to actually host the webapp by building out a shiny server. Luckily, a lot of my issues were solved by following Dean Attali's post [here](https://deanattali.com/2015/05/09/setup-rstudio-shiny-server-digital-ocean/).












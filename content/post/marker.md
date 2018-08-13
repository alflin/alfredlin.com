---
title: "Map Marker Web App"
date: 2018-04-05T22:40:11+08:00

thumbnailImagePosition: left
thumbnailImage: ./ofo_map/ofo_map.png
image: ofo_map/ofo_map.png
metaAlignment: left
draft: false
---

*A Webapp created from Shiny framework written in R that allows for the user to view/add/delete markers on a map.*

<!--more-->

# Background
This was a side project where I wanted to futher explore the shiny framework after I went through [this] tutorial.
##### The App: 
webapp with a hacky-login screen with different admin access to view/create/delete different markers on to a map.

Here I created a use case to view/add/delete the three different bike sharing bikes in singapore on the map.

# *Front End*

#### Map Layer

I used the leaflet package to create the main map layer with some customized javascript to enable the deletion of markers

## Login-Screen

I used a hacky way to create a login screen to allow accounts with different levels of access (view vs create vs delete permission).

I added some custom code to re-popup the login screen if the account details didn't match. This is definitely not the cleanest way to create permissioning rights, but as a quick hacky solution it was enough.

# Backend - SQLITE

I used an sqlite database to save all the marker data. The user accounts were hardcoded into the app's logic. Ideally I would also put user accounts in the database as well, especially for security reasons, but during the time of development I just wanted a proof of concept.

# Conclusion

I wanted ot test out a very quick way to productionize a GUI web app and realized it was a very quick way to do it using Shiny. Although the problem occurs when you consider scale & security issues.




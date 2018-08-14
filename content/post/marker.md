---
title: "Map Marker Web App"
date: 2018-07-05T22:40:11+08:00

categories:
- projects
tags:
- R_showcase
- SQLite

thumbnailImagePosition: left
thumbnailImage: ./ofo_map/ofo_map.png
metaAlignment: left
draft: false
---

*A Webapp created from Shiny framework written in R that allows for the user to view/add/delete markers on a map.*

<!--more-->

# Background
This was a side project where I wanted to futher explore the shiny framework after I went through [these](https://shiny.rstudio.com/tutorial/) tutorials.

- Tech Stack Used: R, Shiny, Nginx, SQLite
- Demo: [http://shiny2.alfredlin.com/posts/ofo_map/](http://shiny2.alfredlin.com/posts/ofo_map/)
- Github: [https://github.com/alflin/ofo_map](https://github.com/alflin/ofo_map)

##### The App: 
This is a webapp with different admin access to view/create/delete different markers on to a map.
Here, I used an example of bike sharing companies in Singapore where a user would click to create a marker on the map of which specific company bike as the marker.

![alt text](/ofo_map/ofo_map.png "app")

# *Front End*

#### Map Layer

I used the leaflet package to create the main map layer with some customized javascript to enable the creation and deletion of markers. The package also came with lots of bells and whistles which I only enabled a few of the features such as search.


![alt text](/ofo_map/ofo_map_add.png "add")
*Main mapping screen with the top right corner allowing for filtered views*

![An easy way to enable map searching in from the leaflet package](/ofo_map/ofo_map_search.png "search")
*An easy way to enable map searching in from the leaflet package*

![alt text](/ofo_map/ofo_map_delete.png "delete")
*Added some custom javascript to enable a delete button on each marker*

## Login-Screen

I used a hacky way to create a login screen to allow accounts with different levels of access (view vs create vs delete permission).

I added some custom code to re-popup the login screen if the account details didn't match. This is definitely not the cleanest way to create permissioning rights, but as a quick hacky solution it was enough.

Here I created a use case to view/add/delete the three different bike sharing bikes in singapore on the map.

![alt text](/ofo_map/ofo_map_login2.png "login2")

# Backend - SQLITE

I used an sqlite database to save all the marker data. The admin user accounts were hardcoded into the app's logic. Ideally I would also put user accounts in the database as well, especially for security reasons, but during the time of development I just wanted a proof of concept.

![alt text](/ofo_map/ofo_map_db.png "db")


# Conclusion

I wanted to test out a very quick way to productionize a GUI web app and realized it was a very quick way to do it using Shiny. Although the problem occurs when you consider scale & security issues.




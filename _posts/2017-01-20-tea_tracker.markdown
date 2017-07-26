---
layout: post
title:  "Brewteaful"
date:   2017-01-20 07:36:24 -0500
---


Brewteaful is a tool designed for tea lovers who would like an easier way to keep track of all the different kinds of tea that they own. Use this tool to record important tea brewing information such as: `brewing time`, `brewing temperature`, `purchase date`, and `measurements`. Also, discover new teas by viewing the latest submissions of fellow users.

![](https://puu.sh/tsP2u/40a04c7af6.png)

User-owned teas, as well as all of the teas submitted onto the website, are listed out neatly on their individual pages for quick readablilty. New entries get added onto the top of the list on the main index page, since it is a list of most recently submitted teas. Users are able to add an infinite amount of teas to their account; however, the amount of recent teas viewable on the index page is limited to 15 to avoid page congestion.

![](https://puu.sh/tsPTa/77b6c1e23f.png)

On the user's tea list page, the purchase date is listed along with the tea's name if it was provided. Older teas lose their flavor over time, and this functionality makes it easier to prioritize the consumption of older tea.

**Workflow**

This project was designed according to the MVC (model-view-controller) design pattern. This project has two models: a `User` model and a `Tea` model. Btoh models inherit from `ActiveRecord::Base`. A user `has_many` teas, and tea `belongs_to` user. To faciliate this relationship, the database entry for the `teas` table contains the foreign key of `user_id`.

I began working on the `User` model first, since it is the primary table in this database and is encountered first on the home page of this project. User information is validated for uniqueness and presence, and passwords are encrypted using `bcrypt` and are authenticated to make sure user logins are valid. After completing the various routes such as register, login, logout, and the user's show page, I worked on the routes regarding the `Tea` model. The teas controller follows CRUD (create, read, update, delete) functionality. Routes have their corresponding view pages, and also provide helper error messages whenever a user sends invalid information.

A video demo is uploaded [here](https://youtu.be/0aYpcURfGi0).
The source files can be found [here](https://github.com/krishl/tea-tracker).

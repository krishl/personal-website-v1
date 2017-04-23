---
layout: post
title:  "Restaurant Planner"
date:   2017-04-22 23:19:02 -0400
---


This Rails app was created for those who often discover new restaurants and foods to try and need a place to record these new discoveries for later.

I approached this project with four models in mind: a `Users` model, a `Foods` model, a `Restaurants` model, and a `RestaurantFood` join model. The associations for these models are as follows - 

`User has_many Restaurants`, `User has_many Foods`

`RestaurantFood has_many Restaurants`, `RestaurantFood has_many Foods`

`Food has_many Restaurants, through Restaurant_foods`, `Food has_many Restaurant_foods`, `Food belongs_to User`

`Restaurant has_many Foods, through Restaurant_foods`, `Restaurant has_many Restaurant_foods`, `Restaurant belongs_to User`

When setting up my routes, I decided to branch all pages off of `users`.

The Devise gem was used to handle user authentication, and users are also able to log in via GitHub.

I followed MVC and used CRUD methods throughout this project. The third-level nested attribute in my forms gave me some problems, but they were solved by writing out methods that manually created and saved these attributes. I noticed many of my scoped views were very similar to each other, so I used partials and passed through the necessary variables through them to keep the code functional and DRY. Validations and checks were also implemented to avoid invalid data and to prevent users from viewing and manipulating another user's entries.

The repository for this project can be found [here](https://github.com/krishl/restaurant-planner).

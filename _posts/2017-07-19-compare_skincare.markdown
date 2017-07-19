---
layout: post
title:  "Compare Skincare"
date:   2017-07-19 14:02:53 +0000
---


Everybody is different in their own way, and this statement does not exclude our skin's reactions to skincare! For my final project I decided to create a tool that lets users compare the ingredients of different products to aid in identifying beneficial and/or detrimental ingredients.

I began this project by creating a Rails backend to serve as my project's API. I created a new rails app with Postgresql, since I also wanted to prepare it for deployment. I also enabled Cross-Origin Resource Sharing (CORS) in order to accept cross-origin AJAX requests.

First I began by setting up the associations between my models. Although I have major plans for this app, I wanted to start simple and first fill the project requirements before adding extra functionality. For now I am starting with the essential models: `Product` and `Ingredients`. I am also introducing a `ProductIngredients` model to act as a join table since this is a many-to-many relationship.

I intially used `ActiveModelSerializers` to structure my data for this project and later decided on using `Jbuilder` instead since the data structure that ActiveModelSerializers created was too nested. Jbuilder allowed me to create my own structure, thereby avoiding any deeply nested data.

My frontend was created using `create-react-app`. This is similar to `rails new`, where the basic files get created and configured for you. I approached the frontend portion of my project by first drawing out pictures of how I want my app to look like. Once I became satisfied with the design, I thought of it in terms of React components and drew out a tree diagram which illustrated the relationships between components.

One of the first things I learned about React was that it involves many different files. It can easily get confusing very quickly. Because of my diagrams, it became easy to keep an organized workflow. While working on this project, I learned of a package called `aphrodite-jss` that enables users to create CSS specific to the file that you are working on. This was very handy in that I didn't have to worry about CSS from other files conflicting with the file that I am trying to style.

Creating this app was truly a major learning experience. I feel like I couldn't have understood React as much as I do now without having done this project. It is very difficult understanding all of the processes that occur by simply reading about it. Actively working through a full project has forced me to think more critically about every step and see how each step affects the overall picture.

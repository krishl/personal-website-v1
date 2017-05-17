---
layout: post
title:  Jquery Restaurant Planner
date:   2017-05-17 10:50:21 +0000
---


This project required me to take my existing rails project and add javascript capabilities to it.

In order to load my index pages via jQuery and an Active Model Serialization JSON Backend, I first added the Active Model Serializer gem into my Gemfile and ran `rails g serializer restaurant` and `rails g serializer food` in my terminal to create the serializers. I added additional attributes to the serializers, since I wanted more information than just their ids. Next, I added event listeners to both models in order to listen for button clicks. For every click event that occurs on the "Sort By Restaurant" button or on the "Sort by Menu Item" button, an AJAX request is fired to retrieve the data necessary for the page. After the necessary JSON data was retrieved, I iterated over it using the `forEach()` method.

Next, I started working on the jQuery for the Restaurant Show page and for the Food Show page. I added their appropriate associations on their serializers and edited their controllers in order to render json for their show pages. One problem I did come across was when I was trying to make the food prices available next to the food names in the same bullet point, as well as a delete button for that restaurant_food. I did not know of any built-in method that automatically combines the `restaurant.foods` array with the `restaurant.restaurant_foods` array together in the way I wanted them, so I went about this by splitting it into two main blocks of code.

I first iterated through `restaurant.foods`, while preparing the html for the second iteration by adding an empty span tag with an id that matches the element's array index - 

```
restaurant.foods.forEach(function(food, i) {
        var rListItem = `<li><a href="/users/${userId}/foods/${food.id}">${food.name}</a> <span id="rPrice${i}"></span> | <span id="rDelete${i}"></span>`
        $("ul.rFoods").append(rListItem)
      })
```

Next, I iterated through `restaurant.restaurant_foods` and filled in the empty span tags -

```
restaurant.restaurant_foods.forEach(function(restaurant_food, i) {
        $(`span#rPrice${i}`).text(`${accounting.formatMoney(restaurant_food.price)}`)
        $(`span#rDelete${i}`).html(`<a data-confirm="Are you sure?" rel="nofollow" data-method="delete" href="/restaurant_foods/${restaurant_food.id}">Delete</a>`)
      })
```

Since I wanted the price to automatically be correctly formatted as currency, I decided to use the [accounting.js library](http://openexchangerates.github.io/accounting.js) in order to use its `formatMoney()` method.

The next task at hand was to add the ability to create a new Restaurant entry and a new Food entry from the User Show page. Since this single page had two forms doing very similar things, The main challenge of this was to keep everything extremely organized, especially the class and id names for the various html tags. I also added a few div toggles so that only relevant divs are displayed to the user. I never had truly seen the importance of assigning classes and id's until now.

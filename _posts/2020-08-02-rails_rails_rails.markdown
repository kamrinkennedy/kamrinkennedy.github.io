---
layout: post
title:      "Rails, Rails, Rails"
date:       2020-08-02 19:51:43 -0400
permalink:  rails_rails_rails
---

> 
> For my Rails portfolio project, I've created a web application name Barmaid's Tale. It is designed for bartenders (or just home mixologists!) to be able to share and review new craft cocktail recipes with one another. In order to accomplish this, several factors needed to be taken into consideration from the getgo:

* Create models for Users, Spirits, Recipes, and Reviews and their relations
* Set up necessary CRUD and RESTful routes 
* Set up nested routes for user ease
* Implement Google Omniauthorization
* Maintain separation of concerns with helper methods and partials


One of the most important part of this project was setting up the object relations between the different models. For my application, User models are created upon signup. They have many recipes and reviews. Recipes are created by users. They have many reviews, and they belong to one user. They also belong to one "Main Spirit". For simplicity sake, I personally seeded out several different Spirit options for the user to choose from instead of instantiating their own. I chose to do this in order to prevent the database from being filled in with several extraneous entries that were unneeded. Finally, the reviews are also created by users. They belong to one user as well as one recipe.

Additionally, given that there is a join table (Reviews) that belongs to both a user and a recipe, I was able to establish a many-to-many relationship between Users and Recipes.

![](https://i.imgur.com/7qVgaHR.png)

![](https://i.imgur.com/ugeSb6u.png)

This creates a few extra methods, such as #reviewers as an instance method for the Recipe class. This would allow you to view all of the Users that have reviewed a particular instance of a recipe. Inversely, we are also able to use #reviewed_recipes on a User instance to see which recipes that they own have been reviewed.

For the purpose of this application, not all models required CRUD capabilities or entirely RESTful routes. The Recipes and Reviews hold most of the CRUD capabilities (and therefor RESTful routes).

![](https://i.imgur.com/TstzKP5.png)

Of course, there are also some non-restful routes added in as well for the sake of user ease, URL readability, and added features: 

![](https://i.imgur.com/vu04GGH.png)

In particular, this nested routing allows the user to create a new recipe for a particular spirit from that spirit's show page without having to provide the form with that information by accessing it through the URL format: "/main_spirits/:id/recipes/new". :id in this instance corresponds to the ID of the spirit.

One interesting challenge in this application was implementing omniauthorization. I chose to utilize google's oauth for this application. It works by first sending an authorization request to google. Google then authenticates the user's credentials within their own systems. Then, google sends a callback function to my application with user credentials. Finally, my application creates a new user in the database using those credentials, specifically the UID and email.

To differentiate between signing up through the application itself versus logging in through Google, I created a Class method in the Users model to instantiate a new user through omniauthorization, filling in or generating all of the necessary fields for a new user to be added to the database.

![](https://i.imgur.com/vhLqFRp.png)

This leads directly into separations of concerns. I've written several class, instance, and helper methods throughout my application in order to keep it DRY ("don't repeat yourself"). Additionally, I've separated my forms for reviews and recipes in order to clean up the view pages.

![](https://i.imgur.com/xl9f2zo.png)

![](https://i.imgur.com/ZZQQo0E.png)

![](https://i.imgur.com/RSCX89l.png)

![](https://i.imgur.com/o3ANhE0.png)

In the above image, the methods created for calculating rating averages were done using Active Record queries as opposed to pure Ruby code. This is a much more efficient method of retrieving information from your database. 

If you would like to explore this application more:

[GitHub Repository](https://github.com/kamrinkennedy/barmaids_tale)
<br>
[YouTube Walkthrough](https://youtu.be/MP5TiLMxrxg)




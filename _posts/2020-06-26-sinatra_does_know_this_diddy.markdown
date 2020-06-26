---
layout: post
title:      "Sinatra *Does* Know This Diddy!"
date:       2020-06-26 17:19:33 +0000
permalink:  sinatra_does_know_this_diddy
---

> 
> This blog post will be outlining my experience building a *Sinatra* web application for the FlatIron full time software engineering program. I chose to build a gaming library, where users are able to sign up, login, and manage their library of games and the platforms on which they are plaid. Users are also able to view other users own libraries of games. To do all of this, a few core things were required:

1. Create models of users, games, and platforms and connect them to a database.
2. Establish associations between different model classes
3. Validate and authorize user signup and login information
4. Create controller classes to dictate the flow of the application
5. Utelize *RESTful* routes between controllers and views

This application uses *ActiveRecord* to establish a database in conjunction with *SQLite3*. In addition, I used *Rake* to create migration files and establish my schema. Users were created with the attributes of a username and a password. Password hashing and salting was done using *BCrypt*. Platforms were created with the attributes of a name, online capability, and reference a user_id. Games were created with the attributes of a name, number of players, and reference both a user_id as well as platform_id. Here is the ultimate schema for the models to be created:

![](https://imgur.com/a/LvrtRnL)

ActiveRecord allows us to easily establish relationships between objects through both outlining it in the schema as pictured above, but also through our class models themselves by giving them relation statements. These statements provide many methods to our models that allow them to easily search for other related objects. As per my schema, a User has_many games and platforms, a Platfrom has_many games and belongs_to a user, and a Game has_many users and platforms.

![](https://imgur.com/e0f1cHK)![](https://imgur.com/TA498DY)![](https://imgur.com/pU2hP2G) 

As seen in the User model above, ActiveRecord also gives us some tools for authentication. These statements require all users to have both a username and password, as well as requiring each new User in the database to have a unique username that does not already exist. Additionally, I added two helper methods in my App Controller to assist with authentication throughout the application.

![](https://imgur.com/fgmqbpx)
> The #current_user method is memoized, which means it can be used throughout all of the controller and view files.
> 

There are four total controller classes in this program. The ApplicationController starts everything off. It is run in the enviornment.rb file, and all of the other controllers inherit from it. The UserController is responsible for navigating RESTful routes for signing up as a new user as well as logging in as an existing one. The GameController is responsible for the creation, editing, and deletion of games, and likewise with the PlatformController.

![](https://imgur.com/LEy3qiv)
> The ApplicationController also reroutes errors and sets secret sessions(necessary for user auth)
> 

The final and most prominent challenge in building this application was establishing the many *RESTful* routes to connect my requests. Each game that is created has the ability to be viewed, edited, and deleted. This satisfies our *'CRUD'* functionality that we expect.

![](https://imgur.com/ubLkedk)

![](https://imgur.com/YuPNaIn)





---
layout: post
title:      "Stick to the (java)Script"
date:       2020-08-30 21:25:35 -0400
permalink:  stick_to_the_java_script
---

For my javaScript portfolio project, I have decided to create an application that allows the user to keep track of upcoming trips and to add activites to a trip that a user would like to take part in over the course of their vacation. Although I do have previous experience in functional javaScript, transitioning to an object-oriented javaScript approach was indeed trialsome. My main objectives in order to accomplish this applications were as follows:

* Construct a Rails API background
* Construct a frontend using HTML, javaScript, and CSS
* Separate frontend concerns between and index.js file and Model/Adapter files
* Manipulate the DOM using javaScript Event Listeners

Constructing a backend API using rails is actually rather easy. By running the command `rails new ` with the `--api` flag attached to it automatically sets up our rails application to be used as an api. Our cors file dictates where we allow requests to come in from, as well as what types of requests are allowed.

![](https://i.imgur.com/C72E7GC.png)

From here, it's simply a matter of setting up your controller actions to expect as well as return json responses.

![](https://i.imgur.com/N8ZFDJg.png)

The frontend, however, was not so cut and dry. Ultimately, there is one index.js file that dictates the control flow of the application. The destination.js and activity.js files establish class models that allow us to interact with the database. The destinationAdapter.js and activityAdapter.js are in charge of coordinating all of the fetch requests.

![](https://i.imgur.com/mJcJU9p.png)


One thing that I did to assist in my unique application was create the dateParser class. This class allowed me to easily take date input data (in the format of `yyyy/mm/dd`) and to return a more readable date. 

![](https://i.imgur.com/F3EJ9B8.png)

I added a slew of customized event listeners to handle all clicks and update the dom without refreshing the page. The index.js houses this functionality.

![](https://i.imgur.com/9OD61Fg.png)

If you would like to explore this application more:

[Github Repository](https://github.com/kamrinkennedy/backend-travel-mapper)
<br>
[YouTube Walkthrough](https://youtu.be/yx21fWsE1TE)



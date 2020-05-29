---
layout: post
title:      "U.S.S. Brews Cruise: My CLI Adventure"
date:       2020-05-29 18:43:47 +0000
permalink:  u_s_s_brews_cruise_my_cli_adventure
---


> I have officially completed my first project, and with that, my first application as a web developer. My command line interface application accesses an API containing information about thousands of breweries throughout the nation. Users are able to search for breweries in the paramater of a city or a state and view more detailed information from there.
> 

![](https://media.publit.io/file/Brewery-Display.png)

This application uses an API from [](https://www.openbrewerydb.org/). Personally, I very much enjoy visiting breweries when I travel to new places. Having access to this data inspired me to create an application that compiles them and gives you points of reference and contact to learn more. 

Initially, this application was built only with the ability to search for breweries by state. However, I wanted to add the capability of searching for all of the breweries in a given city, as that may yield more useful information. I was able to achieve this by adding the following *if statement* in my API class:

![](https://media.publit.io/file/API-clip.png)

By doing this, my application first checks to see if the supplied input successfully retrieves information from a list that is searched through by state. If nothing valid applies, it will return an empty array. Then, my program instead searches through a list by city. If the user input is invalid for both city and state, the program will prompt the user for new input.

One other challenge that I encountered in this application was formatting the phone numbers that were retrieved from the API. From there, we recieve the phone numbers as a string of numbers.*(Ex. "5556667777")*  I found this hard to read, and I wanted to format it into what we're more used to seeing when we read phone numbers. I did this by writing a custom writer method for the phone property in my Brewery class: 

![](https://media.publit.io/file/phone-writer.png)

Lastly, I really wanted to make my application visually appealing. Having multiple different colors at play makes it easier to read as well as aesthetically pleasing. For this, I installed the Rainbow gem. This gem allows you to alter your output text in a variety of ways, but I primarily stuck with changing the colors:

![](https://media.publit.io/file/rainbow-editing.png)

If you would like to explore my project more:

[Explore Github Repository](https://github.com/kamrinkennedy/breweries)

[Watch YouTube Presentation](https://www.youtube.com/watch?v=Op0F270K_f4)


---
layout: post
title:      "Acting is Reacting"
date:       2020-09-29 18:12:25 +0000
permalink:  acting_is_reacting
---


It's been quite the journey getting to this point. React has proven to me that it was indeed worthy of being the apex learning point of this curriculum. While challenging to gain a strong grasp of, React is quite impressive in its ability to render a lot of information in a small amount of code. 

For my application, I chose to create an actor's hub. Currently, it exists as a database of actors that would most practically be used by an agent or casting director. In the future, I wish to refactor it with user authorization so that it's truly a website for actors; one where they can create their own profile and upload all of the pertinent information.

This project was also built using Redux. While also coming with its own unique learning curve, Redux provides you with a much easier way of maintaining and tracking a global state (saved in the "store"). Instead of passing down properties down multiple generations of components, it gives any component the ability to connect to the store directly. 

I also used React-Router to create routes and links in my application.

![](https://i.ibb.co/mHGQYGF/redux-router.pnghttp://)

By wrapping the App component in both the Redux Provider and Redux Router components, every child component (the whole application!) has access to these two features.

Additionally, we were required to use Redux 'thunk' for sending asynchronous http requests and dispatching actions to our reducers. I really enjoed implementing this part. It cleans up a lot of logic from the components of the application while also following a fairly standard convention.

![](https://i.ibb.co/z7dKrcQ/thunk-example.pnghttp://)

One particular struggle that I had (that I never intentionally sought out) was setting up some nested routes. Ultimately, I was able to set the baseline routes in higher up components, with their children routes being defined at lower levels.

![](https://i.ibb.co/QbsC3h5/react-router.png)

While I've easily spent more time on this project than any of the previous, my work is far from done. I'm excited to continue developing it into something more dynamic, exciting, and appealing.

[Github Frontend Repo](https://github.com/kamrinkennedy/acting-out-frontend)
[YouTube Walkthrough](http://)



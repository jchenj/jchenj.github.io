---
layout: post
title: "UX Principles"
date: 2020-04-24
---

I was working on a Flask app today that takes user input and transforms it into an API call. The web app then return the data provided by the API to the user. I had provided a text box for the user input, and once I had the basic version of the app working I started thinking about how to deal with invalid user input. Should I add a `try, except` block into the function that calls the API? How should I evaluate whether input was valid - by whether it led to a 404 status response, whether the input was in the list of possible responses provided by the API, or in another way? 

In discussing this, I was introduced to a principle of user experience design: if it's possible to design a system that limits the possibility of users to make errors, this is a preferred approach. In my current case, using a dropdown menu that only allows users to select from valid responses would mitigate the need to validate text inputs, which could have typos and other midhandlings of valid responses, in addition to invalid responses. 

I learned that while this UX design principle can help with input validation, [defensive programming](https://en.wikipedia.org/wiki/Defensive_programming) best practices would also call for input validation at the level of Flask as well, to mitigate against users who might bypass the browser altogether and attempt to submit requests using the Wget software package, for example. 

While I've still yet to implement these principles fully in the current project - the dropdown list I created isn't submitting the selected values for some reason, and I haven't gotten to the second level of validation yet - this was important learning for the day and motivates me to learn more about UX design going forward. This experience highlighted for me that UX design impacts the programmer as well as the user, as it determines what code I'll write.  
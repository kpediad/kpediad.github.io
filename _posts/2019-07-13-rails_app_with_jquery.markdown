---
layout: post
title:      "Rails app with jQuery"
date:       2019-07-13 06:01:25 +0000
permalink:  rails_app_with_jquery
---


The application that I created for this specific assignment is called [MovieDB-jQuery](https://github.com/kpediad/MovieDB-jQuery).  It is a rails based MVC web app for users to list and review movies. Rails facilitates the back-end API of the application while javascript (specifically jQuery) via AJAX calls to the API, is used to create specific parts of the user experience. The basis for this app is my previous assignment, but this time the 'show movie' and 'index reviews for a movie' pages (they are both the same page) have been implemented using AJAX requests, JSON responses, Javascript Objects, prototype functions on these objects and dynamic manipulation of the DOM via jQuery. Some extra functionality has been included on this page in order for a user to be able to submit a new review for a selected movie. Again the review form is submitted via AJAX and the new review appears on the page dynamically without any full page reloads apart from the initial one.

A 'movie' javascript object is constructed (via constructor notation) from the JSON response of the server when the page loads initially. This 'movie' object contains apart from its regular attributes, an array of 'review' objects (also defined using JS constructor notation and populated from the server's initial JSON response) that can contain 0 to many reviews.

The page is constructed using a very simple page template that contains only placeholders and no information whatsoever. All the information presented on the page is embedded dynamically using jQuery. The review index can be sorted in various ways. This sorting also happens dynamically via javascript. The add new review form is also is inserted and removed from the page via jQuery. The form details are posted via AJAX and the new review appears on the index without any full page loads. AJAX does the trick in this case as well. Any informational messages from the server are read using AJAX and presented onto the page dynamically.

All of the above cover the requirements for this assignment in full. I hope you enjoy using this app as much as I enjoyed developing it. 

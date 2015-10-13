# Website Optimization

---

## Introduction

This is Project 4 for Udacity's Front-End Web Developer Nanodegree.

Main objectives of this project:

* Optimize a provided website so that it achieves a target PageSpeed score of at least 90 and runs at 60fps

## Online Live View

The website is available online for viewing at [http://shikeyou.github.io/WebsiteOptimization/](http://shikeyou.github.io/WebsiteOptimization/)

## Files

These are the files/folders for the PageSpeed optimization:

* **index.html:** The main HTML5 page to optimize for a PageSpeed score of at least 90

* **css/print.min.css:** css style for printing, to be loaded with a media query

* **img:** Production images folder

* **img-src:** Source images folder

These are the files/folders for the 60fps optimization:

* **views/js/main.js** main javascript file to optimize

* **views/pizza.html** main HTML5 pizza page

* **views/images:** Production images folder

* **views/images-src:** Source images folder

* **views/css:** provided css folder

Pages that are not relevant to this project are removed, thus there are some broken links. This is deliberate because those provided pages were not optimized.

## Running The Project

1. Clone the repository

2. Open *index.html* in a web browser (Google Chrome is recommended)

## Changes that I have done

### Optimization task for index.html

* made analytics.js load async
* added 'media="print"' for print.min.css loading
* moved async javascript scripts to the top, before css
* moved inline javascript for analytics to the bottom
* made google web font css download non-blocking
* inlined css and js
* minified css and js
* compressed profile.jpg to save some bytes
* created a smaller version of pizza.jpg of width 100px and compressed it as pizza-small.jpg. This file is loaded in index.html instead of pizza.jpg

### 60fps task in view/js/main.js

* in updatePositions(), I shifted layout query (document.body.scrollTop) out of the for-loop and referred to this stored value in the loop to do batch style calculation. This prevents a forced synchronous layout.

* in changePizzaSizes(), instead of querying layout to calculate a width percentage, I'm determining the pre-calculated percentage value in the size switch. This helps to avoid a forced synchronous layout. The original helper function determineDx() is totally removed.
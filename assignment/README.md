# Assignment 03: Sequencing a Choropleth Map Through Temporal Data

## Table of Contents

<!-- TOC -->

- [Assignment 03: Sequencing a Choropleth Map Through Temporal Data](#assignment-03-sequencing-a-choropleth-map-through-temporal-data)
    - [Table of Contents](#table-of-contents)
    - [Part I. Completing the lesson (5 pts)](#part-i-completing-the-lesson-5-pts)
    - [Part II. Building an interactive map (7.5 pts)](#part-ii-building-an-interactive-map-75-pts)
        - [Data](#data)
        - [Deliverables](#deliverables)

<!-- /TOC -->

## Part I. Completing the lesson (5 pts)

Save and commit your work to complete the Oregon Map of Unemployment Rates as outlined within [lesson 03](./README.md). Then use this as a basis for completing Part II of this assignment.

## Part II. Building an interactive map (7.5 pts)

Create an interactive web map of unemployment rates by county for the entire country. However, let's add some constraints that you might find in real-world applications. Imagine if your data couldn't be modified in an external app before delivering it to the browser. The goal is to write a script to process the data, and handle problems, at runtime.

This assignment has a few challenges. Expect to handle missing data; we are working with temporal data that perhaps could fundamentally change over time. While you have the opportunity to view these data on your favorite desktop apps to understand these challenges, please do not modify them in any way.

Another consideration is keeping external libraries updated. The lesson uses earlier versions of Leaflet and Chroma.js. Part of development is being aware of the latest versions of these libraries, and how they might impact your code. The answer might seem straightforward – use the latest versions. This is generally true, especially in regards to security and bug fixes. New versions might provide useful enhancements, too. The problem arises when the latest versions might not be backwards compatible with your code. You'll need to be aware of this, and make appropriate decisions.

### Data

Within the *assignment/data/* directory, examine the *us-counties.json* file. Like the GeoJSON used in the lesson, it contains no quantitative attribute data, but merely a "GEOID" attribute, which is each state and county FIPS code, concatenated together. 

Also within the *assignment/data/* directory is a data file, *us-unemployment-counties.csv*. This does not contain a "GEOID" attribute.  You'll need to modify the script to bind this data to spatial layer, e.g., concatenating the appropriate fields to make this attribute.

Begin by copying the completed lesson *index.html* file to the *assignment/* directory. 

### Deliverables

Your map should fulfill the following requirements:

* Load two external files, a GeoJSON, and a CSV, at runtime.
* Process these data, binding attribute data to geometries.
* Draw a classed choropleth map of unemployment rates for US counties using an appropriate classification method, e.g., k-means or quantile, or quartile and a sequential color scheme. Consult the [Chroma.js](https://gka.github.io/chroma.js/#chroma-limits) for options.
* Draw an accompanying legend with an appropriate legend title and class break labels.
* Display the map at 100% width and height of the browser window's viewport.
* Allow the user to zoom and pan.
* Provide a slider control that allows the user to step through the years of data, 2001-2021.
* Has state outlines drawn on top of the county outlines.
* Provide a meaningful title and modal content for the map. Can any summary observations about county unemployment rates be made?

In addition to these requirements, your map should also provide the following UI enhancements for the user:

* A visual affordance when the user hovers over specific counties (e.g., making the stroke of the county yellow).
* A tooltip or popup triggered when the user clicks or hovers on a particular county, which provides the name of the county and the specific unemployment rate for the currently displayed year.
* Accommodate missing data in the legend, popup, and anywhere else it might be displayed to the user.

Finally:

* Change the color and font used in document. However, make sure they do not conflict with the tone of the map's content nor with the map's color scheme. 
* Test your web map on different browsers and devices via the browser's developer tools. Make sure it works as expected.

Your final map should behave like this (without the addition of the state outlines):

![Final map for assignment 03](graphics/assignment-final.gif)  
*Final map for Assignment 03.*


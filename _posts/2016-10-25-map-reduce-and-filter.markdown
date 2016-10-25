---
published: true
title: Map, Reduce and Filter
layout: post
tags: [javascript, functional, rome]
---
Map, reduce and filter are three useful functions to manipulate Javascript arrays. We can use the Filter function to return a filtered array where each element matches specified criteria. The Map function can be used to apply an operation to properties of each element in an array, and return a new array with the transformed values. The Reduce function can be used to 'fold' or combine values of an array using a function of our choosing.

As a mental model for remembering how these functions can work together, my favorite analogy is the Roman census. Let's say that the emperor is planning a census with the goal of getting a headcount of all Roman citizens in the empire. 

```

// The empire is an array of provinces

var empire = [Sicilia, CorsicaSardinia, HispaniaCiterior, HispaniaUlterior...]

/* Citizens only need to be counted in provinces where citizenship has been extended - let's Filter on the CitizenshipGranted property */

var provinceswithcitizens = empire.filter(function(province) { return province.CitizenshipGranted; }

/* Now we have an array with all the provinces that have citizens in them. However, we can't immediately access the number of citizens in each province, because they are grouped by military and civilians. Since this is the only information we need from this array, let's use the Map function to get the numbers of total citizens in each province that we're looking for. */

var citizencounts = provinceswithcitizens.map(function(province) { return province.militarycitizens + province.civiliancitizens; }


/* We finally have an array of the number of citizens in each province. Now we can easily 'fold' it up using the Reduce function. */

var totalcitizens = citizencounts.reduce( (prev, curr) => prev + curr );

```

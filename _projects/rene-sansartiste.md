---
title: "René Sansartiste"
description: 'Pseudorandom painting algorithm that uses a similarity heuristic to gradually "paint" a reference image'
status: "Inactive"
start-year: 2023
end-year: 2023
index: 4
---

![Messi World Cup Timelapse]({{ site.baseurl }}/assets/img/rs-messi-timelapse.gif)

## Overview
*René Sansartiste* is a painting algorithm that gradually "paints" a painting that approximates a user-supplied reference image. 

The algorithm attempts to make several brush strokes per second. Each attempted stroke is made with with a randomly determined color, at a randomly determined point on the canvas, with a randomly determined shape, curvature, breadth, length, and end point. A similarity heuristic function then compares each pixel in the rectangular bounding box surrounding the attempted brush stroke to the pixel at the same position prior to the brush stroke. If the overall similarity of the bounding box to the same bounding box in the reference image after the attempted brush stroke is higher than it was before the brush stroke, the brush stroke is accepted. If not, it is rejected. This way, each brush stroke brings the painting closer to the pixel color data of the reference image.

![Noam Chomsky]({{ site.baseurl }}/assets/img/rs-chomsky.png)

## Etymology

The name "René Sansartiste" is a pun and an homage.

1. The name René is the French version of the Latin masculine name Renatus, which means "reborn". Cobbling together the meanings of "René sans artiste" in French would result in the phrase "reborn without (an) artist".
2. "René Sansartiste" is supposed to sound like someone saying "Renaissance artist" in a French accent.
3. The name René is an homage to the French polymath [René Descartes](https://en.wikipedia.org/wiki/Ren%C3%A9_Descartes), often cited as an example of the term *Renaissance man*. Descartes' invention of the Cartesian coordinate system is integral to the painting algorithm and similarity heuristic that *RS* uses to choose whether to accept or discard an attempted brush stroke.

## To-Do
* Overhaul UI
* Optimize painting algorithm
* Publish source code
* Release as downloadable program

## Technologies
#### Java
The source code for *Delta Time* is written in Java 17.

---
layout: post
title:  "Hough Transform"
date:   2018-09-13 13:15:56 +0200
categories: Hough Transform Explorable Explanation
---

<head>
    <script src="https://d3js.org/d3.v5.min.js"></script>
    <style>
      .my-hough-wrapper {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 1em;
      }
      .my-image {
        width: 50%;
      }
      @media screen and (max-width: 600px) {
        .my-hough-wrapper {
          grid-template-columns: 1fr;
        }
        .my-image {
          width: 100%;
        }
      }
    </style>
</head>


I think the (classical) [Hough transform](https://en.wikipedia.org/wiki/Hough_transform) is a
great technique, but I found it really hard to understand it from formulas and static images.
That's the reason why I created an explorable explanation of it:

*Hover one of the plots to see the corresponding transform in the other one.
Click on the left plot to insert points. Drag points to change their position. Click on a point to remove it.
For touchscreen users: use two fingers for scrolling.*


<div class="my-hough-wrapper">
  <div id="svg1"></div>
  <div id="svg2"></div>
</div>

### Real-World Data

The left plot below shows edge pixels extracted from a simple image:

<div align="center">
<img src="https://fkohlgrueber.github.io/hough-transform-d3/static/hough-scaled.jpg" alt="Hough input image">
</div>

<br>

The right plot shows the hough transform for each edge pixel. Dark regions
suggest lines formed by the edge pixels. Hover them to see which line in the image they represent.

<div class="my-hough-wrapper">
  <div id="svg3"></div>
  <div id="svg4"></div>
</div>

<script src="https://fkohlgrueber.github.io/hough-transform-d3/hough.js"></script>
<script>
  insert_hough_plots("svg1", "svg2")
  insert_hough_plots_2("svg3", "svg4")
</script>


Code is available on [Github](https://github.com/fkohlgrueber/hough-transform-d3)

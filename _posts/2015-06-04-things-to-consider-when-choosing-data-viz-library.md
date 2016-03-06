---
layout: post
title: 6 Things to consider when choosing a Data Visualization library
redirect_from: "/2015/06/04/things-to-consider-when-choosing-data-viz-library/"
permalink: data-viz-library-selection
---

Looking around the internet for a charting library was an overwhelming task. So many different libraries to choose from, with different features offered to me. Here is a comprehensive list that I used to determine which data visualization library would work best for my project.

**Customizability**

Customizability is one of the biggest things to consider when choosing a library. The ability to modify a default type of graph is extremely important. Things like hooking up events to the graph (click, change, etc) is very important once you get into practice. The ability to change colors, edit legends, remove grid lines, etc., will be some of the things that the project may require and that you will have to consider.

**Cross Browser Compatibility**

When choosing a charting library you must consider cross browser compatibility. If you are implementing a system for an enterprise client there is a high chance that they support older browsers. When thinking about data visualization you need to make sure that the library you are evaluating will work across all browsers you support with a minimal amount of work.

**Cross Device Compatibility**

If the application you are writing supports mobile devices you will want the library you are looking at to handle this for you.

**Available Charts**

Having a wide variety of charts available to you is important; this is why you are going to want to choose a library that provides a rich selection of graphs. If the application you are writing for a future release requires a different type of graph you are going to want your current charting library to provide you with that graph and not bring another library into your application.

**Learning Curve**

A charting library that will take the minimal time to learn things such as its API and base functionality is ideal. Libraries like D3.js are very powerful when you want to make a graph that the world has never seen, but require a huge time investment. If you are modifying an popular type of graph (bar graph, pie graph, etc) I would consider one that has a minimal time investment to get up and running.

**Input Data Format**

The input data format is important because you want the library to accept as many data formats possible. JSON is becoming the leading standard but you might be looking for something different.

**Final thoughts:**

You can use [JsGraphs](http://www.jsgraphs.com) to compare different libraries. After considering these things I decided to use highcharts.js. It has worked great for the application we are writing and would recommend it to anyone who is in need of a charting library. [HighCharts](http://www.highcharts.com/)

-victor
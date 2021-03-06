---
layout: post
title: "Creating Computer Floors using SurfacePatternToCurves"
date: 2019-10-15 17:30:00
author: Leslie Ing
categories: dynamo revit bim computer floor python
description: "In this blog post we will describe the usage of the SurfacePatternToCurves node"
image: 'https://github.com/3BMLabs/LABS/raw/master/assets/blog_assets/2019-10-01/SurfacePatternToCurves_Demo_1.gif'
hero_height: is_small
published: true
---

In this blog post we will describe the usage of the SurfacePatternToCurves node. This node is the first one of many to come, created for the [3BMLabs.DigiFab Dynamo Package](https://github.com/3BMLabs/.DigiFab "3BMLabs.DigiFab repository"). It is used to help create raised computer floor elements, using the hatch pattern on a Revit floor.

## Why?

At 3BM engineering we often use computer floors in our projects. These floors are defined by the characteristic of being elevated above the floor slab by pedestals to create space for wiring. This allows for a maximum amount of freedom of workspace organisation. 

![Computer Floors](https://raw.githubusercontent.com/3BMLabs/LABS/master/assets/blog_assets/2019-10-15/PBF_HighRes-Project_DOW_Terneuzen-Wurks-36-ps.jpg)

In our workflow we need to know the grid of these raised tiles and place adaptive components to make use of clash detection. In the old process we imported exploded Autocad drawings. Using this node we can speed up the workflow, because it reads the hatch pattern of the material of the floor slab and recreates the pattern in Dynamo. This saves us a lot of time doing manual tasks working in multiple sofware programs.

## What?

Let's first take a look at the in- and output of the SurfacePatternToCurves node. 

![node](https://github.com/3BMLabs/LABS/raw/master/assets/blog_assets/2019-10-15/SurfacePatternToCurves%20node.png)

The node accepts as input a model element, in our case a floor: "FloorElement".

"Grouped Perimeter IntersectionPoints", is a list of points on the self-intersections of the surface pattern and on the intersection of the pattern with the surface boundary. These points are transposed, in such a way that they form pairs of startpoints and endpoints.

"Surface" is the top surface of the model element.

The "Gridlines" output will output the surface pattern in a list of curves.

The two outputs "GridU" and "GridV" output the same curves as Gridlines, but are seperated in the two directions of the surface pattern, and thus in two outputs.

## How?

##### Example 1: Using SurfacePatternToCurves to create a grid for Computer Floor tiles
![SurfacePatternToCurves_Demo_1](https://github.com/3BMLabs/LABS/raw/master/assets/blog_assets/2019-10-01/SurfacePatternToCurves_Demo_1.gif)



##### Example 2: Using SurfacePatternToCurves to create points for adaptive components 
![SurfacePatternToCurves_Demo_2](https://github.com/3BMLabs/LABS/raw/master/assets/blog_assets/2019-10-15/SurfacePatternToCurves_Demo_2.gif)



## Where?

The node and the example file can be installed from the Dynamo package manager, or downloaded from our [Github Page](https://github.com/3BMLabs/.DigiFab "3BMLabs.DigiFab repository").

## Help?

In a next installment of the blog we will go into a deeper understanding of the node. However, if you have any questions or issues feel free to create a [new issue](https://github.com/3BMLabs/.DigiFab/issues "3BMLabs.DigiFab repository issues") on our GitHub repository. 


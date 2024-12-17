---
layout: default
title: CNC milling simulation. 
permalink: /projects/
---
## CNC milling/collision simulation.
![Screenshot of project](assets/images/project1.png)

The main idea of the project was to create a very fast milling/collision simulation in a manufacturing process as you
can see in the figure below.

# ToDo: Result with collision time and simulation


Note that this problem can be splitup in two. 

The main issue is that the shape evolves in time during manufacturing and to compute collision detection sequentially 
is a huge bottleneck. For that reason CAM software's usually computes the collisions in time windows as shown below: 



The positive side is that you can reduce the milling/collision simulation time a lot but at the risk to get many 
potential collisions between the different shapes, i.e. machine plus working-piece. 




## Project 2: Interactive Dashboard
<iframe width="560" height="315" src="https://www.youtube.com/embed/example" frameborder="0" allowfullscreen></iframe>



<a href="/ivan-homepage/">
    <button style="padding:10px 20px; background-color:#007BFF; color:white; border:none; border-radius:5px; cursor:pointer;">
        Back to Home
    </button>
</a>
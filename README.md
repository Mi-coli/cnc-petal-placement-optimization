# Optimization of Rose Petal Placements on Sheet Metal

*PROJECT CURRENTLY IN PROGRESS!* Please don't mind any missing pieces in my documentation or README as I'm still actively making changes

Python version: 3.11.7 <br/>

I recently got really into metalwork and forging, and as my first large project I decided to make metal roses that I can gift and sell at small markets. This project requires cutting out petal shapes out of sheets of metal, welding them together onto a "stem" (aka a metal rod), and then forging the petals so that they can be bent into shape. The steps to make the rose will be included at the bottom of this README, as well as the SVG files that I created for the shapes and cut out on the plasma CNC cutter. However, one issue that I came across while starting this project was optimizing the shape placement on my stock metal in order to get as many roses as possible, without wasting any material (because who has money for that these days?). 

In order to solve this problem, I wrote a python script that utilizes a simple packing problem approach, using a greedy placement algorithm. The shapes that I am trying to fit on my stock sheet metal are large/medium/small circles (representing the shapes of the three sizes of petals), small rectangle (representing the approximate shape of my leaves), and one large rectangle (representing the star shape that is found at the base of the petals on a rose. At the moment, this is a rough approximation, where the rectangle is a bounding box of the desired shape. I plan on refining this and making the bounding box more precise in the near future)

![](rose_optimization/a.jpg)


# Optimization of Rose Petal Placements on Sheet Metal

*PROJECT CURRENTLY IN PROGRESS!* <br>
Please don't mind any missing pieces in my documentation or README as I'm still actively making changes

Python version: 3.11.7 <br/>

I recently got really into metalwork and forging, and as my first large project I decided to make metal roses that I can gift and sell during small maker markets. This project requires cutting out petal shapes out of sheets of metal, welding them together onto a "stem" (aka a metal rod), and then forging the petals so that they can be bent into shape. The steps to make the rose will be included at the bottom of this README, as well as the SVG files that I created for the shapes and cut out on the plasma CNC cutter. However, one issue that I came across while starting this project was figuring out how to optimize the shape placement on my stock metal in order to get as many roses as possible (because who has money to let material go to waste these days??). 

In order to solve this problem, I wrote a python script that utilizes a simple packing problem approach, using a greedy placement algorithm. The shapes that I am trying to fit on my stock sheet metal are large/medium/small circles (representing the shapes of the three sizes of petals), small rectangle (representing the approximate shape of my leaves), and one large rectangle (representing the star shape that is found at the base of the petals on a rose. At the moment, this is a rough approximation, where the rectangle is a bounding box of the desired shape. I plan on refining this and making the bounding box more precise in the near future).

One key thing to consider is that the current algorithm doesn't account for orientation, meaning that there is a chance that rotating one of the non-circular shapes might provide for a more optimal fit. I included this as one of my TO-DOs (as well as accounting for the exact shapes of the leaves and star, as mentioned above), but for now the algorithm appeared to work sufficiently well, so I decided to use it as is for my first batch, in order to meet my deadline.

If you are a Python novice, then I recommend you stick to the Jupyter notebook since it's way more user-friendly, shows images in the same window (which makes it a bit more seamless when playing with diferent sizing and margins), and doesn't require any additional installations. I only included the .py because I wouldn't be able to live with myself if I only had a notebook as a completed project.  

# Finished Rose
Powdercoated mat black

<div style="display: flex; gap: 10px;">
  <img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/powdercoated2.jpg?raw=true" alt="Image 1" width="300"/>
  <img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/powdercoated4.jpg?raw=true" alt="Image 2" width="300"/>
</div>

No Finish/Unpainted

<div style="display: flex; gap: 10px;">
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/rose5.jpg?raw=true" alt="Image 1" width="300"/>
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/rose4.jpg?raw=true" alt="Image 1" width="300"/>
</div>

<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/rose8.jpg?raw=true" alt="Image 1" width="300"/>


# Now how do we make this thing?

For this project, I used 22 gauge mild steel sheet and a steel rod. I found that 22ga is the ideal thickness, since anything thicker doesn't look delicate enough to be a rose, and anything thinner is too malleable, which makes the rose petals too easy to damage and deform.

Initially, I freehanded the shapes onto the surface using a mug as a guide for my circle. Feel free to freehand them yourself or use the shapes I provided in the `shape_files` folder. Trace out each shape and cut out it out from your stock material. This step varies depending on if you're cutting out by hand or using the plasma CNC, but for the initial proof of concept, I usually prefer to make things by hand since machine calibrating can be time-consuming (and is the least interesting part of the process, in my opinion).

<div style="display: flex; gap: 10px;">
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/f.png?raw=true" alt="Image 1" width="300"/>
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/a.jpg?raw=true" alt="Image 1" width="300"/>
</div>

I then measured out the diameter of the metal rod that I planned on using for the stem, and punctured a hole of that size in the center using a step drill. Using a metal sanding belt, I gave the petals more shape, and then using a wire wheel brush, I removed the remaining marker marks off the surface, as well as any of the sharp edges that resulted from the cutting process. This also prepared the surface for welding.

<div style="display: flex; gap: 10px;">
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/b.jpg?raw=true" alt="Image 1" width="250"/>
<p align="center"> <img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/c.jpg?raw=true" alt="Image 1" width="250"/> 
</div>

Next, I textured the petals with a hammer to give them a more realistic look (yet another reminder that flaws are what makes things beautiful), and then made sure that all the parts can fit snugly on the "stem". You want a tight tolerance here, because if there is a large gap between the petals and the stem, it'll be harder to weld; and welding thin sheet metal to thick metal is already tricky, so no need to make more work for yourself. 

<div style="display: flex; gap: 10px;">
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/d.jpg?raw=true" alt="Image 1" width="300"/>
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/e.jpg?raw=true" alt="Image 1" width="500"/>
</div>

Then, we weld it all together.

I made sure to weld the star shape from the bottom, and the petals from the top. That way, when the star shape is folded down, it will cover the weld spot, and when the petals are folded up, they will hide the weld that is holding them in place. Additionally, this will prevent any gaps between the start shape and the outermost petal.

<p align="center"> <img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/g.png?raw=true" alt="Image 1" width="600"/>

*In progress*
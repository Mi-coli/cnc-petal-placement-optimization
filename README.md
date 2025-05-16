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
  <img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/powdercoated2.jpg?raw=true" alt="Image 1" width="400"/>
  <img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/powdercoated4.jpg?raw=true" alt="Image 2" width="400"/>
</div>

No Finish/Unpainted

<div style="display: flex; gap: 10px;">
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/rose5.jpg?raw=true" alt="Image 1" width="400"/>
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/rose4.jpg?raw=true" alt="Image 1" width="400"/>
</div>

<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/finished_and_unfinished.jpg?raw=true" alt="Image 1" width="400"/>


# Now how do we make this thing?

### Materials:
- 22 gauge mild steel sheet (or any kind of weldable metal)
- Metal rod

### Tools:
- Metal cutting shear (handheld or press, although handheld is a bit on the tougher side for this gauge thickness)
- MIG/TIG welder
- Drill and a step drill bit
- Metal sanding belt
- Wire wheel brush
- Forge or propane torch 
- Pliers (for bending petals, so they need to have some level of heat resistance)
- Hammer
- PPE (it's not always attractive, but it is always recommended)

I found that 22ga is the ideal thickness, since anything thicker doesn't look delicate enough to be a rose, and anything thinner is too malleable, which makes the rose petals too easy to damage and deform.

Initially, I freehanded the shapes onto the surface using a mug as a guide for my circle. I found out that the sizes of the circles used for the petals needs to vary in radius in order for the petals to look blended when folded. Feel free to freehand them yourself and test out different diameters or use the shapes I provided in the `shape_files` folder which already have the proportions that I found worked for me. 

Shapes you need:

<p align="center"> <img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/rose_shapes.png?raw=true" alt="Image 1" width="600"/>

Trace out each shape and cut out it out from your stock material.

<div style="display: flex; gap: 10px;">
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/f.png?raw=true" alt="Image 1" width="300"/>
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/a.jpg?raw=true" alt="Image 1" width="300"/>
</div>

Measure out the diameter of the metal rod that you plan on using for the stem, and drill a hole of that size in the center using a step drill. Use a metal sanding belt to give the petals more shape and then removed the remaining marker marks off the surface, as well as any sharp edges, using a wire wheel brush. This also prepares the surface for welding.

<div style="display: flex; gap: 10px;">
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/b.jpg?raw=true" alt="Image 1" width="300"/> 
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/c.jpg?raw=true" alt="Image 1" width="300"/> 
</div>

Next, texture the petals with a hammer to give them a more realistic look (yet another reminder that flaws are what makes things beautiful), and make sure that all the parts can fit snugly on the "stem". I recommend hammering the stem a bit too, since this will give it a bit of a natural bend and will give it more dimension. You want a tight tolerance here, because if there is a large gap between the petals and the stem, it'll be harder to weld; welding thin sheet metal to thick metal is already tricky, so no need to make more work for yourself. 

<div style="display: flex; gap: 10px;">
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/d.jpg?raw=true" alt="Image 1" width="300"/>
<img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/e.jpg?raw=true" alt="Image 1" width="500"/>
</div>

Then, weld it all together.

<p align="center"> <img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/g.png?raw=true" alt="Image 1" width="600"/>

At this point your rose will look like a 5 year old's abstract drawing, so remember to trust the process. 

You can now clamp the rose and get ready to bend the petals. I recommend using a handheld torch over a forge since 22ga doesn't hold on to the heat long enough, but if you're using a thicker gauge you might be able to get away with the forge.

<p align="center"> <img src="https://github.com/Mi-coli/cnc-petal-placement-optimization/blob/main/instructional_images/bending_petals.png?raw=true" alt="Image 1" width="600"/>


The final step is to texture and attach the leaves. I usually leave this part for last because the leaf placement can get in the way of clamping the stem properly during the bending process.

And that's it!

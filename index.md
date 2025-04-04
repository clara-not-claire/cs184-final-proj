# CS 184 Final Project: Glass Half Full, Glass Half Empty
Christine Zhang, Clara Hung, Kerrine Tai, and Ramya Chitturi

<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

## Project Summary
In this project, we want to explore ray tracing techniques through different media. We aim to create a realistic rendering of a scene underwater and in other media with different indices of refraction.

## Problem Description
Currently, our Homework 3 simulation models assume our scene is in a vacuum. This makes ray tracing simple in the sense that light rays do not need to change direction unless they hit an object or a wall. However, we know that in the real world, we often see objects through different media, and scenes can appear distorted (e.g. a straw in water or an object behind a glass). This problem is important because we want to be able to render scenes realistically, even if part of the scene is submerged in water or some other substance. This means we have to model light refraction through our graphics ray tracing techniques.

To approach this project, we will build on our code for Homework 3. We will use Snell’s Law to calculate the angle at which light refracts when it hits a medium with a different index of refraction, and we will change the direction of the light ray to the new calculated direction. We will do this for each ray by seeing whether it intersects the boundary between media, and making it refract if it does intersect. Then, we plan to generalize this to multiple different media. For the water effects, we plan to look online for resources on how to render realistic-looking water.

We anticipate running into a few challenges during this project, the main one being that we are unsure how to generate realistic-looking water for some part of the scene to be submerged in. While implementing the light rays’ refraction using Snell’s Law is a problem we believe we can solve, creating a water-like appearance on the scene is another question entirely. Other challenges include adding other effects to the water to make it look more realistic, such as caustic effects, which we are not sure how we will tackle.

## Goals & Deliverables

### What We Plan to Deliver
**Step 1**: Successful implementation of Snell's Law
- We will use Snell’s law to calculate the angle of the light ray as it passes through the boundary between air and water. This will allow us to properly transform the light ray that starts from the light on the top of the scene into a light ray as it would appear underwater. We will also modify the code to add a water visual below the water line, which would need to have some kind of translucent appearance. We also plan to use substances other than water, which should just be a different index of refraction in the implementation.
- Our deliverables will be successfully rendered images that display the “straw in water” effect, where we can clearly see the light refract when it hits the boundary between the water and air. We hope that we can have realistic-looking water, and we will also render images using substances other than water.

**Step 2**: Render raytracing through multiple layers of different mediums
- We will extend this implementation to allow different layers of media that have different indices of refraction, such as a layer of air, then oil, then water. 
- Our deliverables will be successfully rendered images that contain at least two different layers of media, with the light refracting properly through each layer. 

**Step 3**: Efficient implementation and light reflection through parameterized boundaries
- We aim to allow the boundary between media to be any continuous function (e.g. a sine wave) to more realistically model some real-world cases. To achieve this, we will follow a similar approach using Snell’s Law and calculate angles at which light rays hit the boundary, regardless of the exact shape of the boundary. This will allow us to calculate the refraction angles and directions of light rays for any continuous function as the boundary between media.
- Our deliverables will be successfully rendered images displaying a scene with correct light refraction for a parabolic boundary as well as a sine wave boundary.
- We will also verify that our images do not take significantly longer to render than the images from Homework 3, which will ensure that our implementation of refraction is efficient.

### What we hope to achieve
**Step 1**: 
- We want to try adding caustic effects to the walls submerged in water for a more realistic scene. TODO ADD MORE HERE

**Step 2**:
- We hope to try adding different light sources in the scene at different locations and directions. TODO ADD MORE HERE



## Schedule
**Week 1, April 7-11**
- Implement the refractive functionality, assuming that the water surface is flat (at a constant height).

**Week 2, April 14-18**
- Make realistic water (adding a blue, transparent medium up to the water level to make the image appear partially underwater)
- Potentially adding on to the BSDF functionality to model the water’s surface, if needed
- Implement refraction for substances other than water, like oil. Find these refractive indices and change the inputs to Snell’s Law accordingly.

**Week 3, April 21-25**
- Model light as passing through multiple layers of different liquids.
- Model the water surface as a continuous function, not just at a flat level. Have the water be at an angle, have waves, use a quadratic function, etc.
- Begin project webpage

**Week 4, April 28-May 2**
- Finish up any tasks from above.
- If time permits, try adding different/multiple light sources to the scene.
- Create project video, finalize webpage, and generate deliverable images.


## Resources
- Use Project 3 repository as a starting point for code
- David J. Griffiths: _Introduction to Electrodynamics_, Ch 9
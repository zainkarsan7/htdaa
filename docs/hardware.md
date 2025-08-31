---
layout: default
title: Hardware
nav_order: 4
---

# Hardware

### Plasma Cutting
<br>
The workflow follows scan plan act, with assessment of the action as it affects an environmental metric, like CO2 equivalents. 

<img src="{{ '/assets/images/graphic_abstract.png' | relative_url }}">


<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/portal_out.mp4" type="video/mp4"/>
</video>
<br>
<div class="d-flex">
  <div class="flex: 0 0 50%; mr-8">
    <img src="{{ '/assets/images/torch_orns.jpg' | relative_url }}">
  </div>
   <div style="flex: 0 0 50%;">
    <p>
      With the perception pipeline, a portal frame disassembly is attempted. Removing the beam based on the weld locations means the robot reorients several times to cut each weld. The result is not as clean as if the cutting orientation was normal. Reorienting the torch means a series of path planning excercises to ensure reachability and avoid collision
    </p>
  </div>
</div>
The gui supporting the perception pipeline is also used for path planning. Here regardless of strategy, the section cut is treated as a sequence of poses with an ambiguous orientation. Multiple samples are taken for numerical IK, levenberg marquardt is used, weighting heavily on the elbow joints to prevent orientation flips. A graph of poses and way points are constructed with edges constructed between poses belonging to subsequent waypoints weighted by the norm of the change in pose. 
<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/path_out.mp4" type="video/mp4"/>
</video>

<br>
<div class="d-flex">
  <div class="flex: 0 0 50%; mr-8">
    <img src="{{ '/assets/images/cherry_picker_1.jpg' | relative_url }}">
  </div>
   <div style="flex: 0 0 50%;">
    Scaling up the process is the next step, abandoning the assumption of static positioning of the robot and its workpiece. The goal is to augment any long reach construction equipment with an intelligent plasma cutting robot. 
  </div>
</div>
<br>
<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/cherry_out.mp4" type="video/mp4"/>
</video>

### Welding for Repair 
<br>
On a side note, the process of cutting and welding is largely similar, torches brought some 3-7mm away from a workpiece and sampling IK sufficiently to avoid collision with workpiece. Becomes more challenging once the robot is mounted to a hebebuhne. Here is a quick current reading test from the very beginning of the PhD. 

<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/Current_Measuring.mp4" type="video/mp4"/>
</video>











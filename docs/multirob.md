---
layout: default
title: Multi-Robotic Setup
nav_order: 4
---

<video autoplay muted loop playsinline controls="" width="100%">
    <source src="../../assets/videos/rumlang_2_small.mp4" type="video/mp4"/>
</video>
<br>
<div class="d-flex">
  <div class="flex: 0 0 50%; mr-8">
    <img src="{{ '/assets/images/toy_ex.png' | relative_url }}">
  </div>

   <div style="flex: 0 0 50%;">
    <p>
      Assemblies can be represented with elements as nodes, and edges as connections. Here's a simple example. The graph hold topological information but not spatial information. Computing spatial relationships can be encoded in so called contact and constraint matrices. The algorithms to compute them are shown below. The disassembly sequence starts with a node, using some heuristic like the least number of connected parts, choose blocking elements until nothing is in the way, remove the node, and adjust the matrices.
    </p>
  </div>
</div>


<img src="{{ '/assets/images/workflow.jpg' | relative_url }}">

<img src="{{ '/assets/images/procession_diag_out.png' | relative_url }}">

<img src="{{ '/assets/images/Gyro_Pick_Place-01.jpg' | relative_url }}">

<img src="{{ '/assets/images/tkinter_gyro_gui.png' | relative_url }}">

<img src="{{ '/assets/images/Process_3.png' | relative_url }}">

<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/gyro_out.mp4" type="video/mp4"/>
</video>

<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/multirob_out.mp4" type="video/mp4"/>
</video>

---
layout: default
title: Perception
nav_order: 2
---

# Perception

Strategies for finding corners, joints, connections using computer vision or deep learning. Simplest is to use a custom trained yolo model on a prompt like 'weld' and extract geometric information from the prediction. 
<div class="d-flex">
  <div style="flex: 0 0 67%;" class="mr-4">
    <video autoplay muted loop playsinline controls="" width="100%">
    <source src="../../assets/videos/yolo_snip_out.mp4" type="video/mp4"/>
    </video>
  </div>
   <div style="flex: 0 0 33%;">
      The quality of the prediction depends on the breadth of the dataset, and a collection of hyperparameters, with overtraining or lack of generalizeability being symptoms of poorly chosen hyperparameters. 
  </div>
</div>

<img src="{{ '/assets/images/hyperparam.png' | relative_url }}">
<br>

With a sufficient weld detection model running, extracting a toolpath for linear beads is feasible with segmentation and skeletonization, offered by Meta's SAM and scikitlearn. 

<img src="{{ '/assets/images/segtocut.png' | relative_url }}">

This prediction in image space correlates to poses in 3D space, using an Azure Kinect and its SDK to map between. 

<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/flock_out.mp4" type="video/mp4"/>
</video>

For simple cut geometries, and reasonable poses for the robot, naive planning from the controller IK is sufficient, but for welds around corners or flanges, sampling or gradient-based planners are necessary.

<div class="d-flex">
  <div class="flex: 0 0 67%; mr-8">
    <img src="{{ '/assets/images/pcd_post.png' | relative_url }}">
  </div>
   <div style="flex: 0 0 33%;">
    <p>
      Here, point cloud processing beginning with DBSCAN clustering, noise removal, and multi-planar ransac to extract cut lines. 
    </p>
  </div>
</div>

<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/beam_cut_out.mp4" type="video/mp4"/>
</video>
<br>
Shown here a gui demonstrating a ransac-esque cuboid strategy on a point cloud stream. The strategy is to sample several points, compute an oriented bounding box, then compare the box orientation with the points that reside inside it.  
<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/cuboid_out.mp4" type="video/mp4"/>
</video>
<br>
Many other strategies, shown below, finding corners with a Harris Detector, Hough Transforms and their intersections, SAM and intersecting regions, and their mapping to 3D in a pybullet environment. 
<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/cv_gui_out.mp4" type="video/mp4"/>
</video>

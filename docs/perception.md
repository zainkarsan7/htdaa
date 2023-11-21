---
layout: default
title: Perception
nav_order: 2
---

# Perception

Two kinds:
* Geometric Perception
* Deep Perception

<br>

### Geometric Perception

Harris corner detection, SIFT, Hough Transform, Blob Detectors<br>

Look at an image and identify geometric primitives, corners, edges (global and local), map similar points, track objects, iterative closest point <br>

### Deep Perception

Rapidly growing, new papers every week making things faster, more reliable/robust<br>

Need two things: Massive Compute Power (with GPUs) and carefully curated datasets <br>

OR<br>

Use pretrained models, adjust the output layer, train on your own dataset, smaller and tailored to application.
Or just use new models straight out of the box like Segment Anything, or CLIP which are trained on super large datasets $$10^6 - 10^9$$ labelled samples. <br>

Mask R-CNN for Instance segmentation, Semantic segmentation, Keypoint Identification
Deep learning methods implicitly describe uncertainty, by giving probabilities of outcomes. Successful architectures are simple. 
Dex-Net 2.0, kPAM-SC, Space Api, more models out there relevant to point cloud segmentation, shape completion, instance segmentation etc. 

### Robotics and Disassembly Domain

Representing grasp poses as quaternions, category level pose estimation, keypoints based on part categories, fasteners, flanges, clips, building components $$\rightarrow$$ category level disassembly actions

<br>
<br>
Put some experiments in deep percetion and geometric perception here:

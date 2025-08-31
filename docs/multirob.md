---
layout: default
title: Multi-Robotic Setup
nav_order: 4
---

Plasma cutting alone isn't sufficent to perform a disassembly task with little or no human intervention. Here, propose a lifting robot, as flexible to the lifting scenario as possible. 
<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/gyro_out.mp4" type="video/mp4"/>
</video>
<br>


<div class="d-flex">
  <div style="flex: 0 0 50%;" class="mr-8">
    <img src="{{ '/assets/images/procession_diag_out.png' | relative_url }}">
  </div>

   <div style="flex: 0 0 45%;">
    
      Using gyroscopic precession to impart a torque on the crane hook. Two electromagnets grip the workpiece. This machine turns potentially any lifting equipment into an intelligent gripper with roughly 400kg payload. Simple hough transform on the webcam provides an orientation setpoint. 
  </div>
</div>

<div class="d-flex">
  <div style="flex: 0 0 50%;" class="mr-8">
<img src="{{ '/assets/images/tkinter_gyro_gui.png' | relative_url }}">
  </div>

   <div style="flex: 0 0 45%;">
    
     A simple gui to control the gyroscopic lifter, for activating the motors, entering tracking mode, and enabling magnets. 
  </div>
</div>
<br>
Together with the plasma cutting robot, this workflow proceeds with two robots working simultaneously to remove a steel element from a prototypical structure, following this workflow:
<img src="{{ '/assets/images/workflow.jpg' | relative_url }}">
The gyroscope saturates quickly, so tilting the wheel back and forth overcomes this problem, but moving it laterally or increasing the speed and mass would also help. 
Residual stress in the assembly overcomes the magnets which can't comply to the potentially non-flat workpiece. The demo had to be paused halfway through disassembly and a different set of magnets were installed. 
<br>
<video autoplay muted loop playsinline controls="" width="100%">
<source src="../../assets/videos/multirob_out.mp4" type="video/mp4"/>
</video>
<br>

<div class="d-flex">
  <div style="flex: 0 0 50%;" class="mr-8">
<img src="{{ '/assets/images/Process_3.png' | relative_url }}">
  </div>
   <div style="flex: 0 0 45%;">
     Different workholding strategies are being investigated, mechanical clamp, and higher payload compliant magnets are the next steps in development. Revising the gyroscopic lifter and working on the communication between these two robots would enable more robust behaviour onsite. 
  </div>
</div>








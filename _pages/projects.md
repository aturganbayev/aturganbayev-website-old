---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

<style>h1.page__title { display: none; }</style>

<h1 style="margin-top: 0; margin-bottom: 20px;">Projects</h1>

<h2 style="margin-top: 0; margin-bottom: 4px;">
  Automated Flashlight Assembly with UR5 &nbsp;<a href="https://github.com/aturganbayev/ME5286_UR5_Flashlight_Assembly#me5286-lab-4--ur5-flashlight-assembly" style="font-size: 0.6em; font-weight: normal;">GitHub</a> &nbsp;<a href="/files/ME5286_Flashlight_Assembly.pdf" style="font-size: 0.6em; font-weight: normal;">Report</a>
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>March 2026</em> &nbsp;|&nbsp; ME 5286 – Robotics, University of Minnesota &nbsp;|&nbsp; Minneapolis, MN
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Tools &amp; Technologies:</strong> UR5, RoboDK, Python, Cartesian &amp; joint-space motion planning, pneumatic clamping
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Programmed a UR5 collaborative robot via the RoboDK Python API to autonomously assemble a three-part flashlight (head, battery, endcap) without human intervention.</li>
  <li>Defined 15 Cartesian targets for pick-and-place, insertion, and fastening operations; used joint-space motion for fast transits and Cartesian linear motion near contact points to prevent collisions.</li>
  <li>Implemented a multi-stroke pre-threading routine followed by torque-controlled final tightening, coordinated with a pneumatic chuck and optical sensor for stable part fixturing.</li>
  <li>Completed the full assembly sequence in 1 minute 39 seconds, within the 110-second requirement.</li>
</ul>
<div style="margin-top: 10px;">
  <iframe width="720" height="405" src="https://www.youtube.com/embed/OAarKcr0SdI" title="UR5 Flashlight Assembly" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="max-width: 100%;"></iframe>
</div>

<hr style="margin: 30px 0;">

<h2 style="margin-top: 0; margin-bottom: 4px;">
  TurtleBot3 Obstacle Avoidance &amp; ArUco Marker Navigation &nbsp;<a href="https://github.com/aturganbayev/CSCI5551-EE5271_Turtlebot_Navigation" style="font-size: 0.6em; font-weight: normal;">GitHub</a> &nbsp;<a href="/files/CSCI5551_Final_Project.pdf" style="font-size: 0.6em; font-weight: normal;">Report</a>
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>Fall 2025</em> &nbsp;|&nbsp; CSCI 5551 / EE 5271 Final Project, University of Minnesota &nbsp;|&nbsp; Minneapolis, MN
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Tools &amp; Technologies:</strong> TurtleBot3 Burger, ROS2 Humble, LiDAR, Raspberry Pi camera, Gazebo, RViz, Python
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Developed a LiDAR-based obstacle avoidance pipeline on TurtleBot3 Burger using two ROS2 nodes: <code>obstacle_detector</code> (monitors the front LiDAR sector and publishes Boolean obstacle topics) and <code>obstacle_avoidance</code> (overrides velocity commands to turn and back away when an obstacle is within 30 cm).</li>
  <li>Integrated a Raspberry Pi camera onto TurtleBot3 Burger — a non-standard hardware addition — calibrated its intrinsic parameters using a ROS2 checkerboard calibration package, and added a static TF frame to correctly represent the camera pose relative to the robot base link.</li>
  <li>Implemented ArUco marker tracking and following: the <code>aruco_follower</code> node fuses camera-derived heading to the marker with LiDAR range measurements to drive the robot to a target distance while stopping when the marker leaves the camera's field of view.</li>
  <li>Validated both algorithms first in Gazebo simulation, then transferred them to the real robot with LiDAR noise filtering adjustments for reliable real-world performance.</li>
</ul>
<div style="margin-top: 10px;">
  <iframe width="720" height="405" src="https://www.youtube.com/embed/5Qi0RW_q2Dw" title="TurtleBot3 Obstacle Avoidance & ArUco Navigation" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="max-width: 100%;"></iframe>
</div>

<hr style="margin: 30px 0;">

<h2 style="margin-top: 0; margin-bottom: 4px;">
  Shoulder Rehabilitation Robotic Exoskeleton
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>April 2022 – April 2025</em> &nbsp;|&nbsp; Nazarbayev University &amp; <a href="https://cemrr.nu.edu.kz/en">CEMRR</a> &nbsp;|&nbsp; Astana, Kazakhstan
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Tools &amp; Technologies:</strong> CAD, 3D printing, four-bar linkage design, cable-driven parallel mechanisms, mechanical prototyping
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Designed and built a 5-DOF hybrid robotic shoulder exoskeleton — a 2-DOF rotational four-bar linkage combined with a 3-DOF cable-driven parallel mechanism — enabling full-range shoulder rotations while preserving alignment with the human glenohumeral joint center of rotation.</li>
  <li>Developed 3D-printed miniature prototype models to validate human-robot mechanism coupling before scaling up to the full device.</li>
  <li>Completed a fully assembled, wearable exoskeleton targeting intensive task-specific exercises for stroke survivors, bridging the gap between mechanical design and clinical rehabilitation requirements.</li>
  <li>Work originated as a BS graduation project at Nazarbayev University and was extended into a fully functional device at the Center of Excellence in Medical Robotics &amp; Research (CEMRR).</li>
</ul>

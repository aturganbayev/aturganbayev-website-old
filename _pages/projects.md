---
layout: archive
title: "Projects"
description: "Robotics projects by Azamat Turganbayev: UR5 tactile surface exploration, automated flashlight assembly, TurtleBot3 obstacle avoidance and ArUco navigation, a 5-DOF shoulder rehabilitation exoskeleton, and its 3D-printed miniature precursor mechanism."
permalink: /projects/
author_profile: true
---

<style>h1.page__title { display: none; }</style>

<style>
.exo-gallery { position: relative; width: 100%; max-width: 405px; margin: 0 auto; }
.exo-track {
  display: flex; overflow-x: auto; aspect-ratio: 3 / 4;
  scroll-snap-type: x mandatory; border-radius: 6px;
  scrollbar-width: none; -ms-overflow-style: none; -webkit-overflow-scrolling: touch;
  background: rgba(127, 127, 127, 0.08);
}
.exo-track::-webkit-scrollbar { display: none; }
.exo-slide {
  flex: 0 0 100%; width: 100%; height: 100%; object-fit: cover;
  scroll-snap-align: center; display: block; cursor: zoom-in;
}
.exo-arrow {
  position: absolute; top: 50%; transform: translateY(-50%); z-index: 2;
  width: 38px; height: 38px; border: none; border-radius: 50%;
  background: rgba(0, 0, 0, 0.45); color: #fff; font-size: 18px; line-height: 1;
  display: flex; align-items: center; justify-content: center;
  cursor: pointer; opacity: 0.85; transition: opacity 0.2s;
}
.exo-arrow:hover { opacity: 1; }
.exo-prev { left: 8px; }
.exo-next { right: 8px; }
.exo-thumbs { display: flex; justify-content: center; flex-wrap: wrap; gap: 6px; margin-top: 8px; }
.exo-thumb {
  padding: 0; border: 2px solid transparent; border-radius: 4px;
  background: none; line-height: 0; overflow: hidden; cursor: pointer; opacity: 0.65;
  transition: opacity 0.2s, border-color 0.2s;
}
.exo-thumb img { width: 54px; height: 54px; object-fit: cover; display: block; }
.exo-thumb:hover { opacity: 1; }
.exo-thumb.active { border-color: var(--global-link-color, #2a7ae2); opacity: 1; }
.exo-lightbox {
  position: fixed; inset: 0; z-index: 9999; padding: 20px;
  display: flex; align-items: center; justify-content: center;
  background: rgba(0, 0, 0, 0.9); cursor: zoom-out;
}
.exo-lightbox[hidden] { display: none; }
.exo-lightbox-img { max-width: 95%; max-height: 95%; object-fit: contain; border-radius: 4px; }
.exo-lightbox-close {
  position: absolute; top: 12px; right: 22px; color: #fff;
  font-size: 40px; line-height: 1; cursor: pointer;
}
</style>

<h1 style="margin-top: 0; margin-bottom: 20px;">Projects</h1>

<h2 id="tactile-ur5" style="margin-top: 0; margin-bottom: 4px;">
  Tactile Surface Exploration with UR5 &nbsp;<a href="https://github.com/aturganbayev/tactile_UR5" style="font-size: 0.8em; font-weight: normal;">GitHub</a>
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>May 2026 – Present</em> &nbsp;|&nbsp; <a href="https://tact.nu.edu.kz/">Tactile Robotics Laboratory</a> &nbsp;|&nbsp; Astana, Kazakhstan
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Tools &amp; Technologies:</strong> UR5, URScript, Python, trimesh, NumPy, SciPy (ICP), pandas, Matplotlib, Docker (URSim), ATI Nano17 force sensor, NI-DAQ
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Built an end-to-end pipeline for automated tactile exploration of a silicone cone with a UR5 collaborative arm, from CAD-derived surface geometry to executed touch sequences with synchronized contact-force recording on both simulated and physical robots.</li>
  <li>Sampled 3,000 surface points with normals from the cone STL using <code>trimesh</code>, then calibrated to the robot base frame with an axis-constrained, translation-only ICP fit (cone axis pinned vertical to avoid a spurious tilt from apex-clustered touch points), reaching ~2.2&nbsp;mm RMS alignment error.</li>
  <li>Generated full-surface and 15-strip vertical touch-pose patterns with height-scaled orientation tilt (5°–15°) for tool clearance, then executed them via a custom Python UR5 IK solver (needed because the controller's single-seed IK fails to converge for poses spread around the cone), streaming URScript approach-press-retract sequences over a raw TCP socket.</li>
  <li>Synchronized ATI Nano17 force readings with the UR5's real-time TCP pose stream via NI-DAQ, auto-detecting each press and logging its peak force and pose for offline analysis.</li>
</ul>
<div style="margin-top: 10px;">
  <iframe width="720" height="405" src="https://www.youtube.com/embed/ED0S0Vk0w-s" title="Tactile Surface Exploration with UR5" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="max-width: 100%;"></iframe>
</div>

<hr style="margin: 30px 0;">

<h2 style="margin-top: 0; margin-bottom: 4px;">
  Automated Flashlight Assembly with UR5 &nbsp;<a href="https://github.com/aturganbayev/ME5286_UR5_Flashlight_Assembly#me5286-lab-4--ur5-flashlight-assembly" style="font-size: 0.8em; font-weight: normal;">GitHub</a> &nbsp;<a href="/files/ME5286_Flashlight_Assembly.pdf" style="font-size: 0.8em; font-weight: normal;">Report</a>
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
  TurtleBot3 Obstacle Avoidance &amp; ArUco Marker Navigation &nbsp;<a href="https://github.com/aturganbayev/CSCI5551-EE5271_Turtlebot_Navigation" style="font-size: 0.8em; font-weight: normal;">GitHub</a> &nbsp;<a href="/files/CSCI5551_Final_Project.pdf" style="font-size: 0.8em; font-weight: normal;">Report</a>
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>Fall 2025</em> &nbsp;|&nbsp; CSCI 5551 / EE 5271 Final Project, University of Minnesota &nbsp;|&nbsp; Minneapolis, MN
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Tools &amp; Technologies:</strong> TurtleBot3 Burger, ROS2 Humble, LiDAR, Raspberry Pi camera, Gazebo, RViz, Python
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Developed a LiDAR-based obstacle avoidance pipeline on TurtleBot3 Burger using two ROS2 nodes: <code>obstacle_detector</code> (monitors the front LiDAR sector and publishes Boolean obstacle topics) and <code>obstacle_avoidance</code> (overrides velocity commands to turn and back away when an obstacle is within 30 cm).</li>
  <li>Integrated a Raspberry Pi camera onto TurtleBot3 Burger, a non-standard hardware addition, calibrated its intrinsic parameters using a ROS2 checkerboard calibration package, and added a static TF frame to correctly represent the camera pose relative to the robot base link.</li>
  <li>Implemented ArUco marker tracking and following: the <code>aruco_follower</code> node fuses camera-derived heading to the marker with LiDAR range measurements to drive the robot to a target distance while stopping when the marker leaves the camera's field of view.</li>
  <li>Validated both algorithms first in Gazebo simulation, then transferred them to the real robot with LiDAR noise filtering adjustments for reliable real-world performance.</li>
</ul>
<div style="margin-top: 10px;">
  <iframe width="720" height="405" src="https://www.youtube.com/embed/5Qi0RW_q2Dw" title="TurtleBot3 Obstacle Avoidance & ArUco Navigation" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="max-width: 100%;"></iframe>
</div>

<hr style="margin: 30px 0;">

<h2 id="exoskeleton" style="margin-top: 0; margin-bottom: 4px;">
  Shoulder Rehabilitation Robotic Exoskeleton &nbsp;<a href="https://cemrr.nu.edu.kz/en/news/9" style="font-size: 0.8em; font-weight: normal;">News</a> &nbsp;<a href="https://www.youtube.com/watch?v=BF6AlbPFsx4&t=535s" style="font-size: 0.8em; font-weight: normal;">Interview</a>
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>September 2023 – April 2025</em> &nbsp;|&nbsp; Nazarbayev University &amp; <a href="https://cemrr.nu.edu.kz/en">CEMRR</a> &nbsp;|&nbsp; Astana, Kazakhstan
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Tools &amp; Technologies:</strong> CAD, 3D printing, four-bar linkage design, cable-driven parallel mechanisms, mechanical prototyping
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Designed and built a 5-DOF hybrid robotic shoulder exoskeleton, a 2-DOF rotational four-bar linkage combined with a 3-DOF cable-driven parallel mechanism, enabling full-range shoulder rotations while preserving alignment with the human glenohumeral joint center of rotation.</li>
  <li>Developed 3D-printed miniature prototype models to validate human-robot mechanism coupling before scaling up to the full device.</li>
  <li>Completed a fully assembled, wearable exoskeleton targeting intensive task-specific exercises for stroke survivors, bridging the gap between mechanical design and clinical rehabilitation requirements.</li>
  <li>Work originated as a BS graduation project at Nazarbayev University and was extended into a fully functional device at the Center of Excellence in Medical Robotics &amp; Research (CEMRR).</li>
</ul>
<div class="exo-gallery" style="margin-top: 10px;">
  <div class="exo-track">
    <img class="exo-slide" src="/images/exoskeleton/1.jpg" alt="Shoulder rehabilitation exoskeleton, photo 1 of 4" loading="lazy">
    <img class="exo-slide" src="/images/exoskeleton/2.jpg" alt="Shoulder rehabilitation exoskeleton, photo 2 of 4" loading="lazy">
    <img class="exo-slide" src="/images/exoskeleton/3.jpg" alt="Shoulder rehabilitation exoskeleton, photo 3 of 4" loading="lazy">
    <img class="exo-slide" src="/images/exoskeleton/4.jpg" alt="Shoulder rehabilitation exoskeleton, photo 4 of 4" loading="lazy">
  </div>
  <button type="button" class="exo-arrow exo-prev" aria-label="Previous photo">&#10094;</button>
  <button type="button" class="exo-arrow exo-next" aria-label="Next photo">&#10095;</button>
  <div class="exo-thumbs"></div>
  <div class="exo-lightbox" hidden>
    <span class="exo-lightbox-close" aria-hidden="true">&times;</span>
    <img class="exo-lightbox-img" src="" alt="">
  </div>
</div>

<hr style="margin: 30px 0;">

<h2 id="mini-shoulder" style="margin-top: 0; margin-bottom: 4px;">
  3D-Printed Miniature Model for Human-Robot Shoulder Coupling &nbsp;<a href="https://ieeexplore.ieee.org/document/10458641" style="font-size: 0.8em; font-weight: normal;">Paper</a>
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>January 2023 – September 2023</em> &nbsp;|&nbsp; Nazarbayev University &nbsp;|&nbsp; Astana, Kazakhstan
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Tools &amp; Technologies:</strong> SolidWorks, MATLAB, four-bar linkage kinematics, cable-driven parallel mechanisms, 3D printing
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Designed a 5-DOF miniature shoulder coupling mechanism combining a 2-DOF crank-rocker four-bar linkage for the shoulder girdle with a 3-DOF cable-driven parallel mechanism for the glenohumeral joint, modeling the shoulder's three rotational and two translational degrees of freedom.</li>
  <li>Derived forward and inverse kinematics for both the four-bar linkage and the cable-driven mechanism, then validated the equations against a SolidWorks CAD model in MATLAB, matching cable lengths and joint angles to within 1–2&nbsp;mm and a few degrees.</li>
  <li>Designed a pretension mechanism to eliminate cable slacking and derailment, and built an adjustable 3D-printed prototype with reconfigurable cable connection points for testing different coupling strategies.</li>
  <li>This foundational prototype later informed the full-scale 5-DOF exoskeleton developed at CEMRR.</li>
</ul>
<div class="exo-gallery" style="margin-top: 10px;">
  <div class="exo-track">
    <img class="exo-slide" src="/images/mini_shoulder/prototype.jpg" alt="3D-printed miniature shoulder mechanism prototype, photo 1 of 3" loading="lazy">
    <img class="exo-slide" src="/images/mini_shoulder/cas.jpg" alt="Miniature shoulder mechanism CAD joint detail, photo 2 of 3" loading="lazy">
    <img class="exo-slide" src="/images/mini_shoulder/sketch.jpg" alt="Miniature shoulder mechanism CAD overview, photo 3 of 3" loading="lazy">
  </div>
  <button type="button" class="exo-arrow exo-prev" aria-label="Previous photo">&#10094;</button>
  <button type="button" class="exo-arrow exo-next" aria-label="Next photo">&#10095;</button>
  <div class="exo-thumbs"></div>
  <div class="exo-lightbox" hidden>
    <span class="exo-lightbox-close" aria-hidden="true">&times;</span>
    <img class="exo-lightbox-img" src="" alt="">
  </div>
</div>

<script>
(function () {
  function initGallery(gallery) {
    var track = gallery.querySelector('.exo-track');
    var slides = [].slice.call(track.querySelectorAll('.exo-slide'));
    var thumbsWrap = gallery.querySelector('.exo-thumbs');
    var lightbox = gallery.querySelector('.exo-lightbox');
    var lightboxImg = lightbox ? lightbox.querySelector('.exo-lightbox-img') : null;
    var current = 0;

    slides.forEach(function (img, i) {
      var b = document.createElement('button');
      b.type = 'button';
      b.className = 'exo-thumb' + (i === 0 ? ' active' : '');
      b.setAttribute('aria-label', 'Go to photo ' + (i + 1));
      var t = document.createElement('img');
      t.src = img.src; t.alt = '';
      b.appendChild(t);
      b.addEventListener('click', function () { goTo(i); });
      thumbsWrap.appendChild(b);
    });
    var thumbs = [].slice.call(thumbsWrap.children);

    function goTo(i) {
      i = Math.max(0, Math.min(slides.length - 1, i));
      track.scrollTo({ left: i * track.clientWidth, behavior: 'smooth' });
    }
    function setActive(i) {
      if (i === current) return;
      current = i;
      thumbs.forEach(function (d, j) { d.classList.toggle('active', j === i); });
    }

    var raf;
    track.addEventListener('scroll', function () {
      if (raf) cancelAnimationFrame(raf);
      raf = requestAnimationFrame(function () {
        setActive(Math.round(track.scrollLeft / track.clientWidth));
      });
    });
    gallery.querySelector('.exo-prev').addEventListener('click', function () { goTo((current - 1 + slides.length) % slides.length); });
    gallery.querySelector('.exo-next').addEventListener('click', function () { goTo((current + 1) % slides.length); });

    if (lightbox && lightboxImg) {
      slides.forEach(function (img) {
        img.addEventListener('click', function () {
          lightboxImg.src = img.src;
          lightboxImg.alt = img.alt;
          lightbox.hidden = false;
        });
      });
      lightbox.addEventListener('click', function () { lightbox.hidden = true; });
    }
  }
  function init() { [].slice.call(document.querySelectorAll('.exo-gallery')).forEach(initGallery); }
  if (document.readyState === 'loading') {
    document.addEventListener('DOMContentLoaded', init);
  } else {
    init();
  }
})();
</script>

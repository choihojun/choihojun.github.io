---
layout: page
title: Human Tracking Drone
description: Vision-based person-following drone on a Parrot AR.Drone platform
img: assets/img/robotics/drone_imgs/parrot_ar.png
importance: 2
category: "Undergraduate Projects"
giscus_comments: false
---

A quadrotor that detects a person and autonomously follows them, built on a Parrot
AR.Drone 2.0. The drone streams video to a host computer, which runs person detection
and sends flight commands back over Wi-Fi to keep the target centered in frame at a
set following distance.

**Role:** Team Leader (5 members) · **Duration:** [Jan–Jun 2019] · **Platform:** Parrot AR.Drone 2.0 · **Tools:** [Python, OpenCV, ROS]

As team leader I owned the tracking and control pipeline and coordinated computer
vision, communication, and testing across the team.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/drone_imgs/drone.png" title="Parrot AR.Drone with ducted prop guards" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/drone_imgs/tracking.png" title="Person detection bounding box in the camera feed" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/drone_imgs/system.png" title="System diagram of the tracking pipeline" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: the Parrot AR.Drone platform. Middle: [person detection on the onboard camera
    feed]. Right: [control loop from detection to flight command].
</div>


<div class="row justify-content-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <div class="rounded z-depth-1" style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;">
            <iframe src="https://www.youtube.com/embed/OojMY1wX3Fo" title="Human tracking drone demo" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;"></iframe>
        </div>
    </div>
</div>
<div class="caption">
    The drone detecting and following a walking person.
</div>


## Approach

**Perception.** The drone's forward camera feed was processed on a host computer using
[a HOG/Haar person detector in OpenCV] to locate the target's bounding box each frame.
[Describe how you handled the target when detection dropped for a frame or two.]

**Tracking control.** The horizontal offset of the bounding box from the image center
drove a [PID] controller on yaw, keeping the person centered. The bounding box [height/area]
was used as a distance proxy to hold a fixed following gap by commanding forward/back pitch.

**Communication.** Detection and control ran off-board; commands were sent to the AR.Drone
over its Wi-Fi link [via the ARDroneLib / ROS ardrone_autonomy driver], since the platform
does not expose enough onboard compute for real-time vision.

## Result

[Describe what worked: e.g., the drone reliably followed a walking person indoors at
~[X] m distance, recovering from brief occlusions. Add one concrete number — following
distance, frame rate, or how long it held lock.]

## Takeaways

[This project was my first time closing a control loop around a perception system —
the drone only flew as well as the detector was stable, which is where I first ran into
the reliability problems of vision under changing light. Working with battery-constrained
flight platforms later became my M.S. research focus.]
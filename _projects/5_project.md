---
layout: page
title: Fish Drone
description: A swimming fish-shaped robot with a streamlined servo-driven body
img: assets/img/robotics/fish/fish_robot.png
importance: 5
category: "Undergraduate Projects"
---

A fish-shaped swimming robot that propels itself through water with an undulating,
streamlined body instead of a propeller. Built by a six-person team on an Arduino and four
servos, the robot mimics how a real fish moves. We entered it in the College of Engineering
academic fair, where it won the **Grand Prize** (₩2,000,000).

**Role:** Team Leader (6 members) · **Duration:** May–Sep 2017 · **Tools:** Arduino, HS-5625MG servos, Tinkercad (CAD)

As team leader I coordinated three main workstreams — the fish body design (CAD in Tinkercad),
the software (including the streamlined swimming algorithm), and system integration. I also
managed the project overall: documentation, and ordering the parts we needed through school funding.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/fish/fish_robot.png" title="The completed fish drone" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/fish/field_test.png" title="Testing the fish drone in water" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/fish/presentation.jpg" title="Presenting the project at the academic fair" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: the completed fish drone. Middle: a field test in water. Right: presenting the
    project at the College of Engineering academic fair.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <div class="rounded z-depth-1" style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;">
            <iframe src="https://www.youtube.com/embed/uo1Al7basMc" title="Fish drone swimming demo" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;"></iframe>
        </div>
    </div>
</div>
<div class="caption">
    The fish drone swimming under servo-driven body motion.
</div>

## The robot

**Body.** The fish body was designed in Tinkercad and shaped to be streamlined, so it could
move through water with a natural, fish-like motion rather than being pushed by a propeller.

**Actuation.** The body was articulated by servos arranged in a line from head to tail —
head-to-body, body-to-body, and body-to-fin joints — each driven by an Arduino. Every joint
has its own center angle and range of motion, so the body can bend along its length rather
than at a single hinge.

**Swimming algorithm.** Each joint sweeps back and forth through a triangular waveform, but
the joints are offset from each other by a fixed phase. That phase offset makes the bend
travel down the body as a wave from head to tail — a traveling wave — which is what propels
the fish forward instead of just flexing in place. The robot receives a heading angle and a
magnitude value over a Zigbee link; the magnitude sets the swimming speed, and the controller
ramps speed up gradually rather than jumping to the target so the motion stays smooth.

## Result

Won the **Grand Prize** at the 2017 College of Engineering academic fair, with a
₩2,000,000 award.

## Takeaways

[Optional: 1–2 sentences — e.g. leading a six-person team through mechanical design, control
software, and integration at once, and seeing a bio-inspired design idea actually swim.]
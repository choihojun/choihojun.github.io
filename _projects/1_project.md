---
layout: page
title: Smart Car
description: Autonomous RC car with lane detection and infrared obstacle avoidance
img: assets/img/robotics/auto_car_imgs/auto_car.png
importance: 1
category: "Undergraduate Projects"
related_publications: false
---

Participated in the 2018 Intelligent Model Car Competition, hosted by Hanyang
University's Automotive Control & Electronics Laboratory (ACE Lab) and sponsored by
Infineon, BMW Korea, MathWorks, Continental, and Mando.

**Role:** Team Leader (5 members) · **Duration:** Jun–Aug 2018 · **Platform:** Infineon AURIX TC237 · **Tools:** C, MATLAB/Simulink

A 1/10-scale autonomous vehicle that tracks a printed lane using a line scan camera and
avoids obstacles with infrared sensors. The car had to complete a track with
curves, a school zone, and a hill without leaving the lane, and the score
was determined by lap time and penalties.

As team leader I owned the control loop and sensor interface, and coordinated mechanical design, PCB assembly, and algorithm across the team.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/auto_car_imgs/auto_car.png" title="smart car" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/auto_car_imgs/connect.png" title="wiring" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/auto_car_imgs/3d_print.png" title="mount using 3D printer" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: assembled vehicle with line scan camera mast and DC motor (with Encoder) drivetrain.
    Middle: custom control board wiring the MCU, motor driver, and sensor lines.
    Right: 3D-printed camera mount and chassis brackets designed in SolidWorks.
</div>

## Demo

<div class="row justify-content-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <div class="rounded z-depth-1" style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;">
            <iframe src="https://www.youtube.com/embed/nvvU88x4Zqw" title="Smart Car demo" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;"></iframe>
        </div>
    </div>
</div>
<div class="caption">
    Autonomous lane tracking and obstacle avoidance demo.
</div>

<div class="row justify-content-center mt-4">
  <div class="col-sm-auto text-center">
    <a class="btn btn-sm z-depth-0" role="button" href="https://github.com/choihojun/2018SMCC" target="_blank" rel="noopener">
      <i class="fa-brands fa-github"></i>&nbsp; Source code
    </a>
  </div>
</div>


## Approach

**Lane detection.** The line scan camera returns a single row of 128 intensity values at
up to 1 kHz. We thresholded each frame adaptively to locate the lane edges and computed
the lane center as the steering reference. Adaptive thresholding was necessary because the
venue lighting varied across the track and a fixed threshold lost the line under the
overhead lamps.

**Steering control.** A PID controller mapped the lateral error to a servo angle.
We tuned the gains empirically and added a derivative filter to suppress jitter from
single-frame noise.

**Speed control.** Vehicle speed was reduced in proportion to the measured curvature so the
car could enter corners without losing the line, then restored on straights.

**Obstacle avoidance.** Infrared sensors on the front and sides triggered a lane-change
maneuver, after which the controller re-acquired the lane.

## Result

The competition admits
100 teams nationwide each year; our team advanced past the preliminary round
to the final (top 20 of 100 teams)

## Takeaways

This was my team project to participate competition where a control loop had to run reliably in real time on a
resource-constrained MCU, and where a tuning decision showed up immediately as physical
behavior. That combination — embedded firmware close to the vehicle — is what I still work on.
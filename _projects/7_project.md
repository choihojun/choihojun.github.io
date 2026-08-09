---
layout: page
title: Custom RC Car
description: A store-bought RC car rebuilt with Arduino, Zigbee, and a load-cell throttle
img: assets/img/robotics/custom_RC_car/entire_car.jpg
importance: 7
category: "Undergraduate Projects"
---

A hobby-grade RC car (about ₩30,000 off the shelf) stripped down and rebuilt into a custom
drive-by-wireless vehicle. We replaced the internals with an Arduino and motor driver, drove
the car over a Zigbee radio link, and built a foot-pedal controller that lets a person drive
it like a real car. Exhibited at the College of Engineering academic fair.

**Role:** Team Leader (2 members) · **Duration:** Jun–Aug 2016 · **Club:** Default (Dept. of Electronic Engineering) · **Tools:** Arduino, Zigbee, 3D printing

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/custom_RC_car/entire_car.jpg" title="Rebuilt RC car with Arduino, motor driver, and 3D-printed steering gear" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/custom_RC_car/entire_system.jpg" title="Foot-pedal controller with load cell and handle" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: the rebuilt vehicle, with the Arduino, motor driver, and 3D-printed steering gear.
    Right: the driver-side controller — a load-cell foot pedal for throttle and a handle on a
    potentiometer for steering.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <div class="rounded z-depth-1" style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;">
            <iframe src="https://www.youtube.com/embed/c1tXamIk4vg" title="Custom RC car driving demo" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;"></iframe>
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <div class="rounded z-depth-1" style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;">
            <iframe src="https://www.youtube.com/embed/pj6mRnfRBkk" title="Steering mechanism demo" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;"></iframe>
    </div>
    </div>
</div>
<div class="caption">
    Left: driving the car over the custom track. Right: the 3D-printed steering mechanism in motion.
</div>

## The vehicle

We bought a cheap RC car, removed its original control electronics, and kept only the
chassis, drive motor, and body. In their place went an Arduino and a motor driver, powered
by a 7 V battery pack.

**Throttle.** The original drive motor was retained, with its speed set by the Arduino through
the motor driver. Speed commands arrived wirelessly over a Zigbee link, so the car had no
tether to the driver.

**Steering.** The stock car had no proportional steering, so we built our own. A 3D-printed
gear assembly on the front axle turns the wheels, driven by a basic hobby servo (the common
blue-cased type). This gave us controllable steering angle instead of the simple left/right
of the original toy.

## The controller

Rather than a handheld remote, we built a controller a person operates like driving a real car.
It sends commands to the vehicle as the Zigbee master (transmit side).

**Throttle pedal.** A load cell mounted under a foot pedal reads how hard the driver presses,
and that pressure maps to vehicle speed — press harder to go faster, just like a gas pedal.

**Steering wheel.** A potentiometer with a custom-built handle attached serves as the steering
wheel; its angle sets the car's steering direction.

We also built the driving course the car ran on, and exhibited the whole system at the
College of Engineering academic fair.

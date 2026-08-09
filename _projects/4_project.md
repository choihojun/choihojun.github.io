---
layout: page
title: Line Tracer
description: A PID line-following robot built on ATmega128 for a national competition
img: assets/img/robotics/line_tracer/line_tracer.png
importance: 4
category: "Undergraduate Projects"
---

A line-following robot built from scratch on an ATmega128, tuned with onboard PID control and
entered in a national line tracer competition. The robot reads a floor line with infrared
sensors and steers a stepper-driven chassis to stay on track, with an onboard LCD and buttons
for live PID tuning.

**Role:** Solo project · **Duration:** Apr–Aug 2013 · **MCU:** ATmega128 (Atmel Studio) · **Chassis:** Aluminum plate

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/line_tracer/line_tracer.png" title="Line tracer robot with IR sensor array and LCD" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The line tracer: aluminum chassis, forward IR sensor board, stepper drive, and a 16×2 LCD
    with buttons for on-the-fly PID tuning.
</div>


## Demo

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <div class="rounded z-depth-1" style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;">
            <iframe src="https://www.youtube.com/embed/X-XB1hN8KlE" title="Line tracer practice run" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;"></iframe>
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <div class="rounded z-depth-1" style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;">
            <iframe src="https://www.youtube.com/embed/yByiRi2yWzk?start=2108" title="Line tracer competition run" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;"></iframe>
        </div>
    </div>
</div>
<div class="caption">
Left: a practice run before the competition. Right: the competition run (<a href="https://www.youtube.com/watch?v=yByiRi2yWzk&t=2108s" target="_blank" rel="noopener">my run is at 35:08–37:45</a>).
</div>


## Hardware

I built the robot from the ground up on an aluminum-plate chassis.

| Part | Component |
|---|---|
| MCU | ATmega128 (programmed in Atmel Studio) |
| Drive | PK244 stepper motor with SLA7024 driver |
| Line sensing | Transmit/receive infrared sensor pair, each with a 330 Ω resistor |
| Interface | 16×2 LCD + buttons for PID tuning and sensor readout |
| Power | 9 V battery |
| Chassis | Aluminum plate; the sensor board used single-sided perfboard |

The sensor section was built on single-sided solderable perfboard, mounted at the front so the
IR pair could read the line ahead of the wheels.

## Control

**Line sensing.** The paired infrared emitters and receivers detected the contrast between the
line and the floor, giving the robot its position error relative to the line.

**PID steering.** A PID controller ran on the ATmega128, converting that error into steering
corrections for the stepper drive. Because tuning gains by re-flashing is slow, I added a 16×2
LCD and buttons so I could adjust the PID constants and check live sensor values directly on
the robot — no laptop needed between runs.

## Competition

Entered in the **16th National Line Tracer Robot Competition** (Aug 17), hosted by the
micro-robot society ZETIN at the University of Seoul and supported by the Center for Innovative
Engineering Education
(<a href="https://newcompetition.zetin.uos.ac.kr/competitions/62a776e783d54e3eca2f58da" target="_blank" rel="noopener">competition page</a>).
The robot did not finish the preliminary round: I had calibrated the IR sensors under one
lighting condition, but the venue lighting differed enough that the sensor thresholds no
longer held, and the robot lost the line. As my first solo embedded build, it's where I
learned how much a sensing system depends on the environment it's tuned in — a lesson that
still shapes how I think about real-world sensing.

## Takeaways

Itwas my first solo embedded build, where getting the PID loop stable
on real hardware taught me how much tuning matters versus theory.
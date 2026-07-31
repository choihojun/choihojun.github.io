---
layout: page
title: Pattern-Reading Mobile Robot
description: A Pioneer 3-DX robot that reads a floor mosaic through real-time vision
img: assets/img/robotics/mobile_robot/pioneer3.png
importance: 3
category: "Undergraduate Projects"
---

A mobile robot that navigates a floor covered with randomly arranged colored tiles,
recognizing the tiles and their pattern through real-time computer vision. Built on a
Pioneer 3-DX platform driven by an onboard laptop, the system had to analyze what it saw
and correct its path on the fly, since the tile spacing and layout were never announced
in advance.

**Role:** Team Leader (2 members) · **Duration:** May–Oct 2016 · **Platform:** Pioneer 3-DX + laptop · **Tools:** [C++/Python, OpenCV, ARIA]

Developed for the **Vision Centric Challenge (VCC), College division** at the 2016 World
Championship of Robot Contest (WCRC). The 2016 season mission, **"Mosaic,"** required the
robot to distinguish colored paper tiles and their arrangement by vision alone. Because the
gaps between tiles and the exact layout were not disclosed beforehand, the robot had to
interpret the scene in real time and adjust its route accordingly. Our team earned an
**Encouragement Award**.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/mobile_robot/pioneer3.png" title="Pioneer 3-DX robot with downward-facing camera" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/mobile_robot/pattern.png" title="Colored tile mosaic on the competition floor" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/mobile_robot/recognition.png" title="Tile recognition result" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: the Pioneer 3-DX platform. Middle: [the tile mosaic the robot reads]. Right:
    [the recognized pattern output].
</div>

<div class="row justify-content-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <div class="rounded z-depth-1" style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;">
            <iframe src="https://www.youtube.com/embed/7r35HwBlk-A" title="Pattern-reading mobile robot demo" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;"></iframe>
        </div>
    </div>
</div>
<div class="caption">
    The robot reading the tile mosaic and adjusting its path in real time.
</div>

## Approach

**Tile recognition.** A [downward-facing] camera captured the floor, and [OpenCV] was used to
segment the colored tiles and classify each by color. [Describe how you handled lighting
variation or color thresholding on the venue floor.]

**Pattern interpretation.** From the segmented tiles the system reconstructed the local
mosaic layout, [describe how you inferred the arrangement / which pattern it matched].

**Real-time path correction.** Because the tile spacing and layout were unknown in advance,
the robot could not follow a fixed route. It updated its heading from the current camera
frame, [describe the control — e.g., steering toward the next target tile / re-centering on
the pattern], driving the Pioneer 3-DX from the laptop [via the ARIA library].

## Result

Earned an **Encouragement Award** at the 2016 WCRC Vision Centric Challenge (College division).
[Add one concrete detail if you have it: recognition accuracy, how reliably it completed the
course, or run time.]

## Takeaways

Because the layout was never given ahead of time, the robot had to act on what it saw rather
than on a pre-planned route — my first project where perception had to drive control in real
time, under conditions I couldn't script in advance. That problem, making a system behave
reliably on messy real-world input, is one I've kept working on since.
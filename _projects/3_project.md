---
layout: page
title: Pattern-Reading Mobile Robot
description: A Pioneer 3-DX robot that reads a floor mosaic through real-time vision
img: assets/img/robotics/mobile_robot/pioneer3.png
importance: 3
category: "Undergraduate Projects"
---

A mobile robot that reads a character laid out on the competition floor and identifies it
through computer vision. On a large white panel, pink and blue paper tiles were arranged in a grid to spell out a letter or digit, like a dot-matrix display. The robot drove alongside the panel in a single back-and-forth pass with a downward-facing camera, reconstructed the color grid from its scans, and reported which character the pattern formed. Built on a Pioneer 3-DX platform driven by an onboard laptop.

**Role:** Team member (2 members) · **Duration:** May–Oct 2016 · **Platform:** Pioneer 3-DX + laptop · **Tools:** C++/Python, OpenCV

Developed for the **Vision Centric Challenge (VCC), College division** at the World
Championship of Robot Contest (WCRC) — the Korean national qualifier, where top teams
advance to the international final. The 2016 season mission, **"Mosaic,"** required the
robot to distinguish colored paper tiles and their arrangement by vision alone. Because the
gaps between tiles and the exact layout were not disclosed beforehand, the robot had to
interpret the scene in real time and adjust its route accordingly. Our team earned an
**Encouragement Award**.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/mobile_robot/pioneer3.png" title="Pioneer 3-DX robot alongside the mosaic panel" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/robotics/mobile_robot/mosaic_panel_reconstruction.png" title="Reconstructed tile grid forming a character" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: the Pioneer 3-DX scanning alongside the panel. Right: the reconstructed tile grid
    forming a character.
</div>


<div class="row justify-content-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <div class="rounded z-depth-1" style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;">
            <iframe src="https://www.youtube.com/embed/7r35HwBlk-A" title="Pattern-reading mobile robot demo" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;"></iframe>
        </div>
    </div>
</div>
<div class="caption">
    The robot scanning the tile mosaic and spinning in place to signal a correct match with the target answer.
</div>

## Approach

**Scanning.** The robot drove parallel to the panel in a single back-and-forth pass, capturing
the floor with a downward-facing camera. Each frame covered only part of the panel, so full
coverage came from the robot's motion rather than one wide shot.

**Grid reconstruction.** [OpenCV] segmented each frame into pink, blue, and background by color,
and the per-frame results were assembled — using [odometry / position along the panel] — into
the full grid of colored cells.

**Recognition.** The reconstructed color grid was read as a dot-matrix pattern and classified
into a letter or digit via template matching against known character patterns.

## Result

Earned an **Encouragement Award** in the Vision Centric Challenge (College division) at the
2016 WCRC Korean national qualifier
([results announcement](http://world-robofest.com/?act=board.index&bbs_code=notice&bbs_mode=view&bbs_seq=1107)).


---
layout: post
title: Autonomous Robot
tags:
  - programming
  - mechanical
  - project
  - howto
description: >
  Autonomous vehicle. PID controlled line following robot.
hero: https://images.unsplash.com/photo-1449965408869-eaa3f722e40d?auto=format&fit=crop&w=1350&q=60&ixid=dW5zcGxhc2guY29tOzs7Ozs%3D
overlay: green
published: true
---
Autonomous line following robot driven by PID controller.
{: .lead}
<!–-break-–>

**About this project**
This project was a *class* related project.

**Key features**
* Self-driving
* Differential steering mechanism
* PID controlled

**Source code**
Function that read 5 different IR sensor values and compute the differential factor
<script src="https://gist.github.com/akiet00/790f24a2bf2a1eea8fa1ac3d6d817589.js"></script>

After feeding the sensors' data into the PID controller, we can feed the output of the PID controller into a function which controls the speed of the motor.

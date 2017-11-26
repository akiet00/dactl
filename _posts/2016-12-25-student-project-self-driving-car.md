---
layout: post
title: Autonomous Robot
tags:
  - robotics
  - undergrad
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
'''javascript
void read_sensor_values()
{
sensor[0] = digitalRead(A0); // Reading input from IR sensors
sensor[1] = digitalRead(A1);
sensor[2] = digitalRead(A2);
sensor[3] = digitalRead(A3);
sensor[4] = digitalRead(A4);
for (int i = 0; i &lt; 5; i++) {
Serial.print(sensor[i]); Serial.print(&quot; &quot;);
}
Serial.println();
if ((sensor[0] == 0) &amp;&amp; (sensor[1] == 0) &amp;&amp; (sensor[2] == 0) &amp;&amp; (sensor[3] == 0) &amp;&amp; (sensor[4]
== 1))
error = 4;

else if ((sensor[0] == 0) &amp;&amp; (sensor[1] == 0) &amp;&amp; (sensor[2] == 0) &amp;&amp; (sensor[3] == 1) &amp;&amp;
(sensor[4] == 1))
error = 3;
else if ((sensor[0] == 0) &amp;&amp; (sensor[1] == 0) &amp;&amp; (sensor[2] == 0) &amp;&amp; (sensor[3] == 1) &amp;&amp;
(sensor[4] == 0))
error = 2;
else if ((sensor[0] == 0) &amp;&amp; (sensor[1] == 0) &amp;&amp; (sensor[2] == 1) &amp;&amp; (sensor[3] == 1) &amp;&amp;
(sensor[4] == 0))
error = 1;
else if ((sensor[0] == 0) &amp;&amp; (sensor[1] == 0) &amp;&amp; (sensor[2] == 1) &amp;&amp; (sensor[3] == 0) &amp;&amp;
(sensor[4] == 0))
error = 0;
else if ((sensor[0] == 0) &amp;&amp; (sensor[1] == 1) &amp;&amp; (sensor[2] == 1) &amp;&amp; (sensor[3] == 0) &amp;&amp;
(sensor[4] == 0))
error = -1;
else if ((sensor[0] == 0) &amp;&amp; (sensor[1] == 1) &amp;&amp; (sensor[2] == 0) &amp;&amp; (sensor[3] == 0) &amp;&amp;
(sensor[4] == 0))
error = -2;
else if ((sensor[0] == 1) &amp;&amp; (sensor[1] == 1) &amp;&amp; (sensor[2] == 0) &amp;&amp; (sensor[3] == 0) &amp;&amp;
(sensor[4] == 0))
error = -3;
else if ((sensor[0] == 1) &amp;&amp; (sensor[1] == 0) &amp;&amp; (sensor[2] == 0) &amp;&amp; (sensor[3] == 0) &amp;&amp;
(sensor[4] == 0))
error = -4;
else if ((sensor[0] == 0) &amp;&amp; (sensor[1] == 0) &amp;&amp; (sensor[2] == 0) &amp;&amp; (sensor[3] == 0) &amp;&amp;
(sensor[4] == 0))
{
if (previous_error &lt; 0)
error = -5;
else
error = 5;
}
Serial.print(&quot;Error value: &quot;); Serial.println(error);
}
'''

<p>My PID Function</p>
'''javascript
void PID()
{
P = error; // Proportional factor
I = previous_I + error; // Integral factor, EXTREMELY sensitive. Adjust in small
increment.
D = error - previous_error; // Derivative factor
PID_value = (Kp * P) + (Ki * I) + (Kd * D);
previous_I = I;
previous_error = error;
Serial.print(&quot;P-value: &quot;); Serial.println(P); // Serial monitor
Serial.print(&quot;I-value: &quot;); Serial.println(I);
Serial.print(&quot;D-value: &quot;); Serial.println(D);
Serial.print(&quot;PID-value: &quot;); Serial.println(PID_value);
}
'''

After feeding the sensors' data into the PID controller, we can feed the output of the PID controller into a function which controls the speed of the motor.
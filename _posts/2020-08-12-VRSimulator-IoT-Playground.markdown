---
layout: post
title:  "VRSimulator IoT Playground"
date:   2200-08-12 00:00:00 +0000
categories: VRSimulator posts
---
I have decided to move the development into another Unity project.

## Introducing IoT playground:

<iframe width="420" height="315" src="/files/20200811-VR_IoT_Playground-Demo.mp4" frameborder="0" allowfullscreen></iframe>

In the video: 
1. Door sensor - Shows whether door is opened / closed
2. Door opener - opens the door
3. Music turn off
4. Increase camera rotation angle

This is a Unity project I have written today.
Each of the devices classes is derived from iBaseiotClass interface, currently containing only one method, which called "Activate".
But on the other hand, it is easily scalable for more IoT devices.
Tomorrow I am going to add more methods and functions.

UPD 2020-08-12
<iframe width="420" height="315" src="/files/20200812-VR_IoT_Playground-Demo.mp4" frameborder="0" allowfullscreen></iframe>
Smart lamp added

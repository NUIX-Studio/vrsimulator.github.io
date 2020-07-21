---
layout: post
title:  "VRSimulator Architecture"
date:   2020-07-21 00:00:00 +0000
categories: VRSimulator posts
---

# Getting info from IoT devives
We use an open-source solution to get the data from IoT devices sensors, and which allows us to add our own code (for additional ways of interaction, made possible using VR).

# Server
Running OpenHab Server on the local machine.

# Connecting to Unity
Getting and sending the data to the server using REST API.

# Virtual Reality
Using a project in Unity to visualize and interact with IoT devices.

# Scheme

![](/files/20200713-Architecture.jpg)

# More detailed explanation of the architecture

The following scheme has been taken form [this source](https://community.openhab.org/t/lets-talk-about-oh-2-drawings/13096/8). The diagram itself seems a bit complex, but from what can see, VRSimulator diagram will be even bigger. In the picture below look at the top right corner: user interfaces (this is where the VR part is).

![](/files/20200721-openhabfeatures.png)
# User interfaces

(added after the fifth meeting)

Since researches can use the system and the room simultaneously, we need a server to store the states of the IoT VR devices (for example, location).
The fields which will already be in the basic class are:
 - location in real world / location in virtual world
 - hashnum / id of the thing
 - link to the openHAB twin and post/get commands for each service
 - type of the thing
 - link to the mesh of the thing (optional)
 - interaction api (touch, sound etc)


            
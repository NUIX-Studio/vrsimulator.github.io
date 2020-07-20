---
layout: post
title:  "VRSimulator Architecture"
date:   2020-07-20 00:00:00 +0000
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

Currently, there is no need to build the class diagram for the VR part. But one thing has to be noticed: VR part should include same items, channels and things as in the openHAB part. As you can see in this diagram, things are not connected to the REST API, so we will need to store the things states additionaly.


            
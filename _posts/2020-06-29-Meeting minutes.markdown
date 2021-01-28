---
layout: post
title:  "Meeting minutes"
date:   2021-01-25 00:00:00 +0000
categories: VRSimulator posts
---

## First meeting (2020.06.29)
_I didn’t take notes during the first meeting, so this time meeting minutes will just only show the point of the discussion._

1. Meetings every week (if possible);
2. Visualization of IoT devices, interacting with them and simulating their sensing in VR is **the main task**. Research of the devices -> understanding, which types of sensing **can be supported** and which types can not due to the limitations of Virtual Reality and computer simulation of physics laws;
3. Second task is recreating the area in VR and **updating the positions** of devices live. Even if the scan of the room is of a good quality, it only represents a solid place. For example, if chairs are moved, need to run the scanning again. For the first version of platform, just create the 3D Model manually;
4. [Article discussed](https://www.researchgate.net/publication/334998014_Real-Virtual_World_Device_Synchronization_in_a_Cloud-enabled_Social_Virtual_Reality_IoT_Network)

## Second meeting (2020.07.06)

This week:
1. Run through several Unity Tutorials, but could not run the Cardboard example project. No problem if we implement the Simulator without VR at first.
2. After some research, decided to use [OpenHab](https://www.openhab.org) to connect the IoT devices to the platform, because this software provides support for most IoT devices and overall it is easy to use for the first version of the platform. Already added a support of TV Control to it.

Next week: 
1. Test [Oculus Quest](https://www.oculus.com/quest/?locale=en_US) to better understand how to interact with the IoT devices.
2. Yukang is going to find similar researches. [Article](https://www.researchgate.net/publication/334998014_Real-Virtual_World_Device_Synchronization_in_a_Cloud-enabled_Social_Virtual_Reality_IoT_Network) from the previous week is not our competitor.

_Greetings to Jessy_

## Third meeting (2020.07.13)

This week:
1. (J) Created a Unity project with audio sound and controllers.

Next week:
1. Connect the Unity project and openHAB: it means that real devices could be controlled in Unity.
2. Continue on improving the Unity Project.

After developing the [prototype](/vrsimulator/posts/2020/07/12/VRSimulator-Architecture.html), ask professor's opinion and continue developing further (main parts, such as interaction services, location services and extending the number of supported commands (in VR) for IoT devices).

## Pre-fourth meeting (2020.07.21)

Discussed current status of the project

## Fourth meeting (2020.07.21)

This week:
1. Connected Unity project and openHAB, recorded a demo video.

What was mentioned / plans:
1. Add implementation of the thing: define different types of the things and how each of the types will be represented in VR.
2. Think about simultaneous using of the project, and also how to decrease latency (check 直面).
3. How to register the location of the user? (is [Oculus Quest](https://www.oculus.com/quest/?locale=en_US) enough?) Also locating IoT devices is not required (only for robots).
4. Can use two different VR headsets (and compare them).
5. How are the post / get requests are created in openHAB? How can we add our own code to the openHAB platform?

## Meeting 2021.01.25

1. Assumed that we need to implement a "layer" to hold most of the computations.
Architecture looks like this: _Real World Items <-> openHAB bindings <-> openHAB database storage <-> "layer" <-> REST API <-> Unity App <-> Virtual reality and virtual items interaction_;
2. Divided responsibilities;
3. The first things needed is the definition of the "layer" functionality and what API it is going to provide;
4. Current status: can create things and items inside openHAB (real and virtual) and sunchronize them into Unity:

![Current Status](/files/MeetingMinutes/Client-Items.png)
![Current Status](/files/MeetingMinutes/Server-Items.png)

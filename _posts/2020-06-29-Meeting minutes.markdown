---
layout: post
title:  "Meeting minutes"
date:   2020-07-13 08:40:00 +0300
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
1. Connect the Unity project and OpenHab: it means that real devices could be controlled in Unity.
2. Continue on improving the Unity Project.

After developing the [prototype](/vrsimulator/posts/2020/07/12/VRSimulator-Architecture.html), ask professor's opinion and continue developing further (main parts, such as interaction services, location services and extending the number of supported commands (in VR) for IoT devices).




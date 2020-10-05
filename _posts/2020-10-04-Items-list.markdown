---
layout: post
title:  "Items list"
date:   2020-10-05 00:00:00 +0300
categories: VRSimulator posts
---
As described in the [Location and Interaction Services part](https://vrsimulator.github.io/vrsimulator/posts/2020/09/24/Location-and-Interaction-services.html), same as in HCI in general, there are two ways to interact with IoT devices in VR:
1. Direct manipulation
2. Indirect manipulation

## Direct manipulation
> [Direct manipulation](http://www.hitl.washington.edu/projects/knowledge_base/virtual-worlds/EVE/I.D.2.c.DirectManipulation.html#:~:text=Direct%20manipulation%20is%20a%20style,an%20intermediary%20like%20a%20computer.) is a style of Human Machine Interaction (HMI) design which features a natural representation of task objects and actions  promoting the notion of people performing a task themselves (directly) not through an intermediary like a computer.

One of the existing solutions on providing touchable interfaces is MRTK - Microsoft Mixed reality Toolkit([main github](https://github.com/microsoft/MixedRealityToolkit-Unity), [MRTK Quest](https://github.com/provencher/MRTK-Quest)). 
Things in the platform can be based on the UX building blocks, see [documentation](https://github.com/microsoft/MixedRealityToolkit-Unity/blob/mrtk_development/README.md#ux-building-blocks).


## Indirect manipulation
> [Indirect Manipulation](https://medium.com/usable-or-not/direct-v-indirect-manipulation-in-vr-b7c5c4f09c55#:~:text=Indirect%20Manipulation%20refers%20to%20the,drag%20them%20to%20the%20trash.) refers to the manipulation of virtual objects by means of a proxy object or controller, like a mouse.

Teleportation or pointing to the object and moving it around the scene are examples of indirect manipulation. Although these manipulations can't be represented in real world, using them the experience with VR IoT platform becomes more comfortable ([link](https://github.com/microsoft/MixedRealityToolkit-Unity/blob/mrtk_development/Documentation/Input/Pointers.md)).
Example: [Moving objects around](https://vrsimulator.github.io/vrsimulator/posts/2020/10/02/Current-Status.html).

Another ways of indirect manipulation are:
1. Using a microphone (in development).
2. Using camera data, registering hand gestures (in development).


## Sensors and motors
Things are not only interactable, but by default they are created to provide some output to user, such as sensing data, light, sound or even change it's own location.

## Building a new Thing
When adding a new thing to the platform, researchers should follow the [design rules](https://vrsimulator.github.io/vrsimulator/posts/2020/09/14/VRSimulator-Architecture.html): combine things from items, like any item is a block. Interaction between items has to be defined by researcher inside the thing class. Some of the interactions are already defined.

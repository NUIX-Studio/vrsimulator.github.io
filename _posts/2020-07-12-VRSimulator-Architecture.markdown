---
layout: post
title:  "VRSimulator Architecture (Old version)"
date:   2020-09-14 00:00:00 +0000
categories: VRSimulator posts
---

# The architecture has changed, please see the updated version of the text

# Introduction

This document is about the design of the VR IoT Platform.

The Platform we develop is a complex product and it consists of several parts. First, have a look at the tree structure, from top to the bottom:

![](/files/20200914-Figure1.png)

_Figure 1. Tree structure of the platform_

Further, let&#39;s look deeper at the each of its branches.

# Server

It either runs locally on the device (VR Headset) or on the PC, and connects to the running instance on the VR headset.

Although currently it is implemented only locally, in the near future it will be possible for several users to control IoT devices in VR together, which will be achieved by running synchronized copies of the project with the main PC on the VR headsets.

If we look at Figure 1, we can see that the server consists of three parts:

1. Server parameters, such as package names, IP addresses, reserved memory and others;
2. Things Database: the main part of the platform. Stores the states of the things, provides interaction between them, counts the formulas and so on;
3. External Platforms: To connect the VR IoT Platform to the real world we can either write our own solution or use 3rd-party open source platforms. We use OpenHab as it has binding for a big variety of devices and provides REST API to communicate with the real world devices. For Unity we need to provide an interface to interpret the states of the devices from the Things database to the Unity project as well as provide an interface to connect these two environments.

The implementation can be found at [Client/Assets/Server](https://github.com/VRSimulator/VRSimulator-Prototype/tree/master/Client/Assets/Server). To have access, please contact Fedor to add you to the github project.

UPD 9.18: Since time is limited, Server will be running on Unity. Later all Unity-specific functionality will be moved to Unity integration platform. (for example, initialization of class' fields will be moved from Start() to constructors).

## Things Database

Things are the entities that can physically be added to a system and which can potentially provide many functionalities in one. It is important to note that Things do not have to be devices, but they can also represent a web service or any other manageable source of information and functionality. From a user perspective, they are relevant for the setup and configuration process, but not for the operation.

Items are the parts things consist of: for example, smart light in the room can consist of several lamps and a receiver – each of them as an item.

### Things Interaction Platform

To provide fast and easy communication between things i.e. sending data between them, we use a Things Interaction Platform.

The current realization is as follows:

To help things communicate between each other, we first create an instance of the commands stack for the needed pair of things. The key value may be the combination of the unique IDs of the things, the value – pointer to the stack.

_Then, the complexity of accessing this data will be O(log N) if we use SortedDictionary, where N is the number of things. This solution is not suitable when the number of the connections between things grows exponentially with the number of the things. But in real world this usually does not happen. Even in the full graph with n vertices, the number of edges is just n \* (n - 1) / 2. Even if n is 10000, the complexity of accessing the data will be ~ 26._

_If we use Dictionary, complexity is even O(1), but the adding of a new element can be O(n) in the worst case when the hashtable has to be enlarged. Either way, both solutions are good, but since we need to access elements much more frequently, better choose Dictionary._

Same is for the items, we use dictionary to store the pointers to the interaction stack for each pair of the items.

Command stack contains the data we send between the items / things. The commands / data are defined in the methods for each item.

### Things Dictionary

Thing Class should extend Basic Thing class.

It contains the specific values for the thing (such as location) and the corresponding items stored in the dictionary (key – unique item id, value – pointer to the item).

#### Items

Each item&#39;s class should extend the basic item class, which contains fields such as:

1. \_virtualLocation
2. \_realLocation
3. \_hasDigitalInstance
4. \_hasRealInstance
5. \_isDigitalHidden
6. \_isTurnedOff
7. \_isGrabbable
8. …

As mentioned above, to communicate between items we use Things Interaction Platform and Items Interaction Dictionary in particular.

To communicate with the real world, use Post/Get calls defined in the OpenHab Integration, [OpenHabIntegration Class](https://github.com/VRSimulator/VRSimulator-Prototype/blob/master/Client/Assets/Server/ExternalPlatforms/OpenHabIntegration.cs).

To synchronize with the Unity Project, use commands from Unity Integration, i.e. [UnityItem](https://github.com/VRSimulator/VRSimulator-Prototype/blob/master/Client/Assets/Server/Items%20Database/Core/UnityItem.cs).

# Client

Client runs on the VR headset and synchronizes the data from the Server. Current implementation runs on Oculus Quest as an APK file.

![](/files/20200914-Figure2.png)


_Figure 2. A copy of the real world room to test connection with real world IoT devices_

![](/files/20200914-Figure3.png)


_Figure 3. Example Items to test and build new Things from them_

Each of the Items in Unity has a connected corresponding Item Class, which synchronizes with the Server every frame or using the defined frequency.

![](/files/20200914-Figure4.png)


Interaction platform provides an interface to interact with the items.

Example 1. Adding a lamp item, lowering the light's intensity every frame:

![](/files/20200917-BrokenSmartLampItem.png)

1. Find the corresponding Item Class to derive from (SmartLampItem);
2. Implement the needed methods (Update);
3. Connect the new class to the item in Unity: 
![](/files/20200917-BrokenSamrtLampItem-Unity.png)

Example 2:

On the left of the Figure 3 there is a button and a lamp. By pressing the button, the lamp is moved to the right of the table. Also, the lamp can be grabbed and moved around the scene by virtual hands.

In this case, The Thing has two Items: SmartLampItem and Button Activator.

The mesh for the lamp is selected from the available meshes. Item is grabbable so it has a rigidBody enabled + Mesh Collider. SmartLampItem also uses the OpenHab Integration interface to send get requests to synchronize the current state of the lamp such as light intensity and RGB color (just add OpenHabIntegration as a class field).

![](/files/20200914-Figure5.png)
Second item is a button. The ButtonTrigger Script from the Interaction Platform is attached to it and runs the script OnButtonPressed. It uses the LocationService Singleton, method MoveThing. In the example, we define the direction of movement to the right.

## What's next
Before making a good implementation of this structure, first need to be sure that this structure is effective. After the confirmation I can continue with adding new items and interaction techniques.
<iframe width="420" height="315" src="/files/20200916-demo.mp4" frameborder="0" allowfullscreen></iframe>


            
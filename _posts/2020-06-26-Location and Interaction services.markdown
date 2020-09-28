---
layout: post
title:  "Location and interaction services"
date:   2020-09-25 00:00:00 +0300
categories: VRSimulator posts
---
# Interaction platform

# Tutorial

## How to add a thing

#### 1. Open Client as a project in Unity

#### 2. Select VRIoTPlayground Scene
![](/files/Tutorial/SceneSelection.png)

#### 3. Now let's add a new thing to the scene
Let this thing be an interactable speaker.

First, Add an Empty Gameobject.

![](/files/Tutorial/AddAnEmptyGameObject.png)

Name it and move it to the desired location.

![](/files/Tutorial/Creation.png)

Add a speaker mesh (stored in the ByFedor Folder)

![](/files/Tutorial/SpeakerMesh.png)

Next create an item for the Speaker. Navigate to the User folder:

![](/files/Tutorial/TutorialSpeakerClass.png)

Add a Gameobject instance as a child to store the Speaker Mesh, connect Audio Source and TutorialSpeaker.cs script to it

![](/files/Tutorial/AudioSource.png)

Double tap on the Script. The class for TutorialSpeaker should extend SpeakerItem class (available base classes for items see in the Items/Core folder). Our class will be not be using any extra functionality.

![](/files/Tutorial/CreateClass.png)

Navigate back to the editor and connect the audiosource to the item:

![](/files/Tutorial/ConnectAudioSource.png)

Make the speaker bigger

![](/files/Tutorial/BiggerSpeaker.png)

Let's add a button. Create an empty child of the thing, name it and connect the Button prefab to it:

![](/files/Tutorial/BasicButtonAdded.png)

Same as for the speaker, create a script for out tutorial button and derive it from BasicButton:

![](/files/Tutorial/TutorialButtonClass.png)

Connect it to the item:

![](/files/Tutorial/ConnectButtonScript.png)

When the button is pressed, the Basic Button is triggered, not the one we created, so in this case we need to trigger the Tutorial button by adding an action to it in the editor: Add TutorialButton.ButtonItemTriggered to the list of actions:

![](/files/Tutorial/BasicButtonAction.png)

Let's create a thing. Create a new script and derive it from BaseThing:

![](/files/Tutorial/CreateThingClass.png)

Start is called on the frame when a script is enabled just before any of the Update methods are called the first time. We add a listener for the Button, so when it is pressed, the method we define will be called. In this case, PlayPause methkd will be called.

![](/files/Tutorial/ThingClassFill.png)

Connect the script to the thing and don't forget to define the Thing in the editor:

![](/files/Tutorial/AddThingScript.png)

Build the app. You will be able to control as play/pause of audio by pressing the button.

<iframe width="420" height="315" src="/files/Tutorial/Trim.mp4" frameborder="0" allowfullscreen></iframe>

Sorry for the sound quality, had to record using the notebook's built-in one.



# List of items (brainstorming)

## Things we can interact with by touching
1. Button – press it: by using finger, distance – use a stick. Parameters: size, shape, height, force, 
2. Slider – like a button, move it around a line, fingers, stick, 
3. Touch Screen – precision is low. When interacting, because can’t see the surface, we can use some indicator like a lamp to show that user is already touching the screen, and doesn’t need to move the finger lower, or can move the screen together with the finger. Another way is using  a controller or stylus. Can also interact with a touchscreen connected to one of your hands with another hand, like in vrchat (\*).
4. Cube – touch 4 facing faces of the cube, each of them perform an action. Additional: can touch the edges with a virtual stick (\*), example: beatsaber, [mini beatsaber](https://vrscout.com/news/mini-beat-saber-oculus-quest-hand-tracking/)
5. Iron-man kind-of( transparent) touch screen (\*)
6. Switcher – on/off
7. Transparent button, just need to intersect with it, see example [here](https://medium.com/shopify-vr/expo-towards-rapid-vr-prototyping-15356d53ea71) (\*)

## Other ways to interact, not touch:
1. Microphone – just use the one inside VR headset. Can use voice commands
2. Speaker – Use Unity 3D sound, only according to the distance
3. Hand Gestures – connect two fingers, make a sign; i.e. [link](https://www.roadtovr.com/creative-uses-oculus-quest-hand-tracking-daniel-beauchamp/); hand walking(\*) - does not track correctly on Quest, the lower hand is not visible behind the upper hand; throwing hands(\*); 
4. 
5. 

## How to interact with distant objects:
1. Make your hand much longer, hand tracking still works, you can operate with distant objects (\*)
2. Use a virtual saber (\*)
3. Throw your hand (\*)
4. 
… Editing…

## Other Items
1. Lamps: light color, intensity, cookie, halo, flare
 
(\*): Can only be performed in VR environment and at least for now can't be applied to real world




            
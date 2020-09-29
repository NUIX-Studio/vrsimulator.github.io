---
layout: post
title:  "My First Mistake"
date:   2200-06-28 00:00:00 +0000
categories: IoT posts
---

Put this to 2200 because this article is not needed atm


In this post I will show you an example of companies greediness and how they try to lure users into their ecosystems.

I decided to start the automation from helping my grandmother who lives alone, and in her case smart home would play a very important role.

## Smart home for elderly
It's obvious that elderly people (80 y.+) don't need all the automation scenarios the companies provide for IoT devices. Moreover, the main requirement for Smart Home for elderly is to be unnoticable for them, to not make them feel uncomfortable by making them use all these new technologies, but at the same time, provide information to their children to know that everything is alright.

In this case, <strong>gas and water leak</strong> sensors need to be used. Sometimes, children want to be sure that their parents are safe and be notified if any frauds come inside the house (can be solved by buying a Wi-Fi camera). The price for these devices should be cheap with no controlling centers required and no crashing is also very important.

## My Configuration
For me another requirement was availability of these devices in my hometown. 

After all, the choice was given to company Rubetek. They buy the sensors in China and license them for Russian market putting their logo, same as any other Russian company selling IoT devices.


![](/files/20200628-Rubetek.jpg){:height="50%" width="50%"}


Door open and Gas Leak sensors connect to camera over the RF 433MHz protocol, camera connects to Wi-Fi. Then, it all can be controlled through the Cloud using my Phone. Sounds simple and good, solves all of the problems, but...

## Slavery
After downloading the Rubetek App and reading all of the how-to instructions in the boxes, I found out that scenarios can't be used with this configuration - need to buy a control center for $120.

![](/files/Screenshot_com.rubetek.client_1_LI.jpg){:height="30%" width="30%"}

The bigger problem was that I could receive the notifications from the sensors only in signaling mode (as was written in the how-to paper), but I somehow managed to overcome this requirement by switching the toggle several times:

![](/files/Screenshot_com.rubetek.client_4.jpg){:height="50%" width="50%"}

So now it works as before, I get notifications if there is a gas leak or the door is opened and can always go to the app and see the live translation from the camera.

## Experience
Tomorrow I will go to my grandmother's house to install the things, and, after some time, wil describe the experience in this post.
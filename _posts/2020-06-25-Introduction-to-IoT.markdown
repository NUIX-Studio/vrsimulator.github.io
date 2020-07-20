---
layout: post
title:  "Introduction to IoT"
date:   2020-06-25 18:08:25 +0300
categories: IoT posts
---
It takes quite a long time time to find information about what is popular in IoT world and what has already died. The IoT automation world changes so fast that even articles from the year 2013 look like from ancient times. In this article I will try to summarize the existing solutions I have found on the forums and articles and thus save you a couple of evenings by using one picture:
![My helpful screenshot](/files/IoT-World.jpg)
Good news is that the entry level to this world is quite low and not every part is necessary. User can start building Smart Home without even  buying a hub. For example some devices can work without hubs (such as Xiaomi Yeelight Wi-Fi-lamps).
In my case, I have ordered three devices: IP-Camera, gas leak sensor and door open sensor. IP-Camera has Wifi and ZigBee protocols supported. It connects to the Wifi router, and, at the same time, connects to the other two devices.

### Protocols
Four magic words to know today: Wi-Fi, Bluetooth, ZigBee and Z-Wave. Other protocols even if existed three years ago, have died already. But in the enterprice solutions protocols X10, OneWire and Lutron Connect still can be found.
#### ZigBee and Z-Wave
Adding Wi-Fi to every device is too expensive, while ZigBee and Z-Wave chips are very cheap (around 1$) and energy-effective. Both of them can combine a decentralized IoT net. Many devices can send signals to each other, and then there may not be need thinking about where to put a router in the apartment / building.
European manufacturers such as IKEA, Bosch, Philips, Siemens use ZigBee, while USA ones prefer Z-Wave. Chinese market seem to use ZigBee. Previously companies wrote their own code above the current protocols resulting impossibility to connect to the devices from other companies. But now it seems that if "HomeKit Compatible" is wrote on the box then devices using two protocols can work fine together.
#### Wi-Fi
It is much easier to create a smart home by using only Wi-Fi devices. Just connect them to the Phone / Tablet / any device that supports Wi-Fi and ... you have a smart home. No need to buy any hub. But there are disadvantages:
<ul>
    <li>Router goes crazy when the number of devices is high</li>
    <li>The signal area is much lower compared to ZigBee and Z-Wave</li>
    <li>Microwave interferes the signal</li>
    <li>The price of devices is 4-5 times higher</li>
</ul>
## Main tasks
Knowing protocols is good, but what about solving real-world problems?

<strong>Connecting devices</strong> It can be done either automatically by scanning the network, or it can be done by using QR- or Pin-code.

<strong>Creating scenarios</strong> Activate the devices' fucntions, change their parameters by writing down the sequencing and activating the needed scenes.

<strong>Grouping</strong> Divide the devices based on their location or functionality. By grouping, for exmaple, it's no problem to turn on the lamp in the kitchen by using only one command.
## APPS
There is a high variety of apps, but <em>their main task is to get you to the one brand's ecosystem.</em> It can be either Xiaomi Mi Home, IKEA, Philips, Bosch Smart Home - every of them has an APP, but they all support only limited amount of manufacturers. For a basic user Apple HomeKit can be a good choice though, but for more experienced users there are better APPs, which will be shown in the further articles.
<strong>Apple HomeKit</strong> Two problems:
<ul>
    <li>Support only Apple devices</li>
    <li>Works over Wifi</li>
</ul>
The first one can be solved by simply buying an Apple device (so painful for me as for a user of Huawei ecosystem). The second problem means that those cheap devices which work over ZigBee or Z-Wave protocols require installing a special hub to connect to Apple device. But if a user does it, then there will not be a problem to, for example, turn on the lamp from another part of the world (HomeKit App -> iCloud -> Hub -> Bingo!)

## Hubs
Hubs usually are not expensive ($30-60), but, for example, brand hubs support only limited number of manufacturers.
<ul>
    <li>IKEA TRADFRI - $30, but support only devices from IKEA and Philips</li>
    <li>Xiaomi Aqara - $30-60</li>
</ul>
Xiaomi Aqara: [limited support of devices](https://www.home-assistant.io/integrations/xiaomi_aqara/)

### Universal Hubs
These were made for the users who don't want to spend hours on programming DIY-solutions (such as based on Raspberry Pi), but want to have a support of a lot of protocols. 

[Samsung SmartThings](https://www.smartthings.com/): People say that Samsung stopped developing the product and currently only open-source compunity pushes updates to it.

Seems that these two are less popular: [Wink Hub](https://www.wink.com/products/wink-hub/), [Logitech Harmony Hub](https://www.logitech.com/en-us/product/harmony-hub).

### DIY Hubs
The pure Raspberry Pi can connect to Wi-Fi and Bluetooth devices. Then just only need to coonect modules for ZigBee and Z-Wave.
Then use one of the interfaces to connect the devices:

[<strong>OpenHab</strong>](https://www.openhab.org/) - Java, reliable

[<strong>Home Assistant</strong>](https://www.home-assistant.io/) - Python, easy and flexible

[<strong>Home Bridge</strong>](https://homebridge.io/) - Made for connecting devices to HomeKit

[<strong>Domoticz</strong>](https://www.domoticz.com/) - C/C++, probably died:(

In the research for VRSimulator, we will probably use DIY Hub.

## Smart Assistants

![Smart Assistants](/files/south-park-smart-home.jpg)
The main players on market nowadays are: [Xiaomi Xiaoai, Ali's Tmall Genie, Baidu smart speaker](https://medium.com/voiceui/price-wars-in-chinas-smart-speaker-market-b4cf4961940b), Amazon Echo, Google Home, Apple Homepod.
They all can run simple scenarios, but each of them lacks in some other fields, such as supporting limited number of platforms, bad sound and mic quality.
<strong>Big variety, but none is ideal.</strong>

## Devices

Overall, most of the IoT devices are dependable from the network. If Internet connection crashes, nothing is going to work. 

### Xiaomi

![Xiaomi devices](/files/Introduction-to-iot-xiaomi-devices.jpeg)
<ul>
    <li>Nice design</li>
    <li>Very cheap</li>
    <li>Can integrate with a lot of other devices</li>
</ul>
But they support a lot of protocols: sensors - ZigBee and require a hub, lamps work with Wi-Fi, the kettle uses BlueTooth. Another problem I found that international Xiaomi devices can't work properly with devices from Chinese market.

### IKEA

Very popular in Europe and USA, because the devices:
<ul>
    <li>Are cheap</li>
    <li>Can be found in every IKEA</li>
    <li>Use ZigBee</li>
</ul>
But IKEA devices require to buy a hub for using them as well.

### Old manufacturers: Philips, OSRAM, BOSCH, GE and others

<ul>
    <li>Good quality</li>
    <li>Many devices</li>
    <li>Good support of standarts</li>
</ul>

But they are expensive and same as IKEA, also require to use their ecosystems.

### Startup devices

Cool design, HomeKit-from-the-box, latest ideas... but very expensive, no DIY, only Apple and the quality is not good.

### Other devices
TBD








            
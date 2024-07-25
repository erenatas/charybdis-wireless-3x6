# Table of contents

- [Table of contents](#table-of-contents)
- [Introduction](#introduction)
- [Important disclaimer](#important-disclaimer)
- [Required Parts](#required-parts)
  - [Flexible PCBs](#flexible-pcbs)
  - [PMW3610 Breakout](#pmw3610-breakout)
  - [Nice!Nano Holder](#nicenano-holder)
  - [3D Prints](#3d-prints)
  - [Electronic components](#electronic-components)
    - [Notes](#notes)
  - [Helper Tools](#helper-tools)
- [Assembly](#assembly)
- [Software](#software)
- [Credit and thanks](#credit-and-thanks)
# Introduction

This guide is based on the [erenatas build guide](https://github.com/erenatas/charybdis-wireless-3x6).

The purpose of it is to outline how to build a Wireless (Bluetooth) Charybdis. It is focused on how to build a 3x6 Charybdis Mini specifically.

**Important notes:**
- As of writing this setup does not support RGB LEDs

# Important disclaimer 
**Follow at your own risk**, Bastard Keyboards and erenatas are not liable for anything that does not work. 

Please note, as it's not an official supported build you will get limited help on the BK discord server.

# Required Parts
## Flexible PCBs

The exact PCBs you need will depend on which keyboard you are building, refer to the [official list for that](https://github.com/Bastardkb/Charybdis/blob/main/electronics_bom.md).

Make sure to follow the recommendations for PCB thickness.

## PMW3610 Breakout
[Link to Void's repo](https://github.com/victorlucachi/charybdis-pmw3610-breakout/tree/nicenano/production)

For this PCB you will need to order it pre-assembled, and solder the PMW3610 sensor manually.

For the assembly, JLCPCB did not have `TCR2EF19` - but the part `TLV70018DDCR` is confirmed to work:
```
#(Old) TCR2EF19:
73dB@(1kHz) 200mA Fixed 1.9V Positive 5.5V SOT-23-5 Linear Voltage Regulators (LDO) ROHS


#(New) TLV70018DDCR:
68dB@(1kHz) 200mA Fixed 1.8V Positive 5.5V SOT-23-5 Linear Voltage Regulators (LDO) ROHS
```

## Nice!Nano Holder
[Link to olidacombe's repo](https://github.com/olidacombe/Elite-C-holder/tree/nicenano/adapter/production)

This PCB Design supports having a power switch that makes use of audio jack hole.

## 3D Prints

Depending on which model of Charybdis you are printing, refer to the [list of required 3d parts on the original repo](https://github.com/Bastardkb/Charybdis/tree/main?tab=readme-ov-file#3d-prints---cases).

For reverting the 3d files, you can do that directly in your slicer - or if you're using a print service, use Prusaslicer or Window's built-in 3d viewer app.

## Electronic components

In this section, we will go through each component that was used, and also give example links. Those are based on the original build from erenatas.

This list is based on the electronics BOM present on the Charybdis repo as of writing, so double-check there that you're not missing anything.

| Name                         | Count | Link                                                                                                                       |
| ---------------------------- | ----- | -------------------------------------------------------------------------------------------------------------------------- |
| Trackball                    | 1     | [Perixx Europe](https://eu.perixx.com/collections/accessory/products/18010)                                                |
| nice!nano microcontroller    | 2     | [Splitkb.com](https://splitkb.com/collections/keyboard-parts/products/nice-nano)                                           |
| (optional) mill max sockets  | 2     | [Splitkb.com](https://splitkb.com/collections/keyboard-parts/products/mill-max-low-profile-sockets?variant=31945995845709) |
| SOD123 Diodes                | 41    | [Splitkb.com](https://splitkb.com/collections/keyboard-parts/products/smd-diodes)                                          |
| Button, 4x4x1.5              | 2     | [Aliexpress](https://www.aliexpress.com/item/4001046134819.html)                                                           |
| PMW3610 module               | 1     | [Aliexpress](https://www.aliexpress.com/item/1005006208592770.html)                                                        |
| Mini Toggle Switch TS-6 SPDT | 2     | [Aliexpress](https://www.aliexpress.com/item/1005003684819561.html)                                                        |
| Batteries                    | 2     | [Aliexpress](https://nl.aliexpress.com/item/1005005348368664.html)                                                         |
| Ceramic Bearing Balls 2.5mm  | 3     | [Aliexpress](https://www.aliexpress.com/item/1005004239319689.html)                                                        |
| Flexstrip Jumper Cables*     | 2     | [Aliexpress](https://www.aliexpress.com/item/1005003498734969.html)                                                        |
| Key Switches                 | 41    | [Aliexpress](https://www.aliexpress.com/item/1005003761194503.html)                                                        |
| M3 5mm Brass Melt Nuts       |       | [Aliexpress](https://www.aliexpress.com/item/1005003582355741.html)                                                        |
| M4 5mm Brass Melt Nuts       |       | [Aliexpress](https://www.aliexpress.com/item/1005003582355741.html)                                                        |
| M3 8mm Torx Screws           |       | [Aliexpress](https://www.aliexpress.com/item/1005006115217679.html)                                                        |
| M4 8mm Torx Screws           |       | [Aliexpress](https://www.aliexpress.com/item/1005006115217679.html)                                                        |
| JST plug 2-pin               | 2     | [Aliexpress](https://www.aliexpress.com/item/1005006115217679.html)                                                        |


### Notes

**Flexstrip Jumper Cables (Ribbon cables)**:

You will need:

- 72mm or more for the nice!nano holder
- 80mm or more for the thumb plate 
- 100mm or more for the sensor PCB

If the cables snap or are hard to desolder, you can use 28AWG single-core wire instead.

**Batteries**:

One important part here is the battery. If you order a battery from Aliexpress to Europe, the order will be shipped with freight, meaning it will take ~2 months to arrive. 

Due to this reason, if you reside within EU, you should try to source a battery of your choice within EU. 

What needs to be considered before ordering any battery is to ensure that it is:

- 3.7V
- more than 80mAh
- if you want to squeeze the battery between nice!nano and and the holder PCB, then you need to be careful of its size. At [42keebs.eu](https://42keebs.eu/shop/parts/lithium-polymer-battery/?attribute_size=301230%20(80%20mAh)), it states that you can fit `350926`, `301230`, `401030` underneath the nice!nano microcontroller
- again, if you would like to fit a battery underneath nice!nano, you may want to buy [Mill Max Low Profile Sockets with Headers](https://splitkb.com/collections/keyboard-parts/products/mill-max-low-profile-sockets?variant=47060695646555) in order to create the gap in between

For this build specifically, a JST plug was used to be able to take out the batteries without the need of desoldering.

## Helper Tools

Some tools will make it easier to build your keyoard:

- solder Iron: It's strongly recommended to get a good quality solder iron where you can change the temperature. From my research I have found that Hakko solder irons are overwhelmingly popular, however they are expensive. If you are not planning to build keyboards for a living, you can cut some costs by a cheaper alternative. I myself bought a [GALLUNOPTIMAL GOSprint150](https://www.amazon.nl/dp/B091J6TB43). Others have had success with the Pinecil.
- solder: There are two types of solder that can be used, leaded and lead-free. While leaded solder melts easier and its easier to desolder, lead itself is toxic, therefore its important not to inhale it. You can put a fan in front of you and have good ventilation and possibly wear a mask. Lead-free solder is a safer choice, but it melts harder and is harder to desolder. Make sure to wash your hands after you are done! Using solder with a rosin core also makes it much easier to use.
- solder wick: Its a type of solder remover, can be handy during incidents. Adding flux to board also helps a lot
- solder brass: If solder tin gets stuck on the tip of your iron, this is your go to
- pliers: You will need them to cut flexstrip ribbon cables
- torx screw drivers: You need M3 and M4 screw drivers. You already may have one at home.
- tweezers: You are going to need them to hold pieces together, and also deal with small parts such as SOD123 diodes
- desoldering Pump: Can be handy in case of accidents
- solder flux: Optional, solder tins usually have tin inside nowadays, however it may be handy to have one
- solder Station silicon: Optional, to make sure not to damage the surface you are working on

# Assembly

Most of the steps are similar to building a Charybdis Nano. Below is an outline, with details on what needs to be done differently.

1. install the screw inserts: [BastardKB Docs](http://docs.bastardkb.com/bg_cnano/04screw_inserts.html)
1. solder the diodes: [BastardKB Docs](http://docs.bastardkb.com/bg_cnano/05diodes.html)
1. solder the PMW3610 to sensor board
    - There is a single orientation to solder it. You can take out the sensor cap while doing any soldering to prevent touching it with the soldering iron. Also make sure to remove the kapton tape.
2. solder the power switch to the nice!nano holder
3. solder the update button
4. solder the JST female plug
    - solder it in the same orientation as the button where I can also reach to it from the side. Assembling the nice!nano holder to the case becomes a bit tight but it barely fits without pressure
5. solder the nice!nano
    - [This video from Joe Scotto](https://youtu.be/l5kAx08Iom4) helped me a lot in this part. As it mentioned, temperature on nice!nano is important - do not go above 300 degrees Celsius!
    - **Important** If you run into issues with wiring and in need to do desoldering, make sure to take out the nice!nano first!
6. try connecting the battery and checking if the nice!nano works
7. install the ribbon cables (including sensor board): [BastardKB Docs](http://docs.bastardkb.com/bg_cnano/07ribbon_cables.html)
    - Make sure to cut off extending parts of the cables after soldering to keep the PCBs flat, it will make installing the switches much easier
8. power it on, grab a tweezer and check that each switch and sensor is working
    - you can use your finger to check that the sensor works correctly. If not you may have issues with wiring
9. install and solder switches, make sure to follow the order detailed in the official docs
10. install the sensor board

# Software

Connecting the nice!nano for the first time is its reset mode, all you need to do is to drag and drop the built image - which will flash the n!n. Right hand is the main controller which you can connect to via bluetooth, and the left hand connects automatically to the right.

- erenata's ZMK config: [https://github.com/erenatas/zmk-config-charybdis-mini-wireless](https://github.com/erenatas/zmk-config-charybdis-mini-wireless)
- EIGA's config: [[EIGA's config repo](https://github.com/erenatas/zmk-config)](https://github.com/erenatas/zmk-config)

Erenata added scroll support via forking [@grassfedreeve](https://github.com/grassfedreeve)'s config and adapted it to 3x6 mini. 

# Credit and thanks

This page is based on erenata's work, and all credit goes to him for the initial version of the document.

You can find the original repo here: [erenatas build guide](https://github.com/erenatas/charybdis-wireless-3x6).

Below is outlined the original "thanks" section from his repository.

I would like to thank and give my gratitude to following people that helped to make this project into a reality. I believe you have ignited a DIY flame within me!
- [EIGA](https://www.youtube.com/watch?v=Mks7QDxFreY) with his Youtube.
- [BastardKB](http://bastardkb.com/)
- [VOID](https://github.com/victorlucachi)
- [olidacombe](https://github.com/olidacombe)
- My dear friend and colleague [pbacterio](https://github.com/pbacterio)
- Sigvah who became my build buddy
- My wife for her support!

And finally thank you for all the supporters in BastardKB Discord channel. You have an amazing community!

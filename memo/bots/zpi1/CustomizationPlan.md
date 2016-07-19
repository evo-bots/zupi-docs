# Customization Plan

## The Goal

**MAKE LINUX RUN THE BRAIN OF THE ROBOT**

AND adding computer vision capability to the robot.

## Options

### Arduino Shields

It's easy to add remote connectivity to robot using Wifi/Bluetooth shields for
Arduino. But that doesn't help with the limited computing power of Arduino.
I don't want to build a purely remote-controlled robot with it's brain sitting
in an iPhone or Android. I have a plan to plugin a camera for computer vision,
Arduino can't help on this.

### Raspberry Pi

It sounds a good option. Raspberry Pi 2 or 3 is powerful enough to run Linux
programs on the robot. And it's cheap, compared to Arduino shields, only
a few bucks more.

The challenge is how to plug Raspberry Pi to Zumo. Google didn't tell me much
useful information (I need details!). Some projects make me fell confident down
to this road:

- [The voice controlled Zumo](https://utbrudd.bouvet.no/2015/02/20/unleash-the-potential-of-your-internet-of-things-project-by-combining-arduino-and-raspberry-pi/)
- [Raspberry Zumo Robot](https://www.pololu.com/blog/275/raspberry-zumo-robot)

## Requirements

Most of Raspberry Pi on Zumo projects connect Pi and Zumo using either:

- USB cable (may not work with Zumo for Arduino)
- [Arduberry](http://www.dexterindustries.com/arduberry/) or similar solutions

And the Pi is powered separately. You can find the funny pictures showing little
Zumo carrying big USB powerpack for Raspberry Pi.

I don't like a separate power supply. I want to use the single power source
from the batteries of the built-in Zumo chassis. I'm not quite sure 4 AA NiMH
batteries will be enough. I'm willing to find out.

Besides, I want to assemble these pieces of PCBs, camera supporting kit and camera
in a clean way (without too many wires flying around). It will make my life much
easier in future to build a shell for it.

## Detailed Plan

This is the plan to build **zpi1**:

- Based on Zumo for Arduino (with 75:1 motors)
- Use [Arduberry](http://www.dexterindustries.com/arduberry) to connect Raspberry Pi
- Use [5V Step-up/down Regulator](https://www.adafruit.com/products/2190) to power Pi and Servo HAT
- Add [Servo HAT](https://www.adafruit.com/products/2327) between Arduberry and Pi and use Pi to control camera Pan/Tilt kit
- Use [Pan/Tilt Kit](https://www.adafruit.com/products/1967) to hold camera
- Use [Pi Camera V2 NoIR](https://www.adafruit.com/products/3100) for video capture

The Zumo for Arduino base with 75:1 motors:

![[Zumo Shield Base]](images/zumo-shield-base.jpg)

For how this plan came out, please continue reading, starting from
[Power Supply](PowerSupply.md).

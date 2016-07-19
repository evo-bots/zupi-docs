# Project ZuPi Background

## Zumo

[Zumo Robot](https://www.pololu.com/category/129/zumo-robots-and-accessories) is
front-wheel-drive four-wheel robot with track, designed in low-profile. The
robot is equipped with two individual motors and sensors including gyro,
accelerometer, compass, proximity (Zumo 32U4 only), reflection etc.
It's a great robotic development platform with the potential capability of
doing a lot of fun things.

Zumo Robot has two versions:

- Zumo for Arduino: the main board is called Zumo Shield with all peripheral
  equipments/senors built-in, the only thing needed is an Arduino plug-in on top
  of it;
- Zumo 32U4: the improved version, highly integrated with ATmega32U4 micro
  controller which is built in the main board. So it can function out-of-box
  without extra Arduino. It's also improved with dual power source selection which
  allows USB connection when the robot is powered on from the batteries.

## Raspberry Pi

It's not necessary to introduce [Raspberry Pi](https://www.raspberrypi.org).
It so popular that you should know it before you continue reading.

## Why marry them together?

The original Zumo Robot is controlled by AVR micro controller on which it's
difficult to provide some advanced features like computer vision, due to
the limited computing power.
Raspberry Pi is a minimal hardware which can run full featured Linux and has
enough power to do complicated computing.
Putting them together brings the power of Raspberry Pi to the robot for doing
a lot more interesting things.

However Raspberry Pi can't replace micro controller completely. As it's running
Linux, it's a share-time operating system, which doesn't perform well with
real-time (timing sensitive) tasks. And this is the gap micro controller steps in
with the simplicity that is perfect for time-sensitive tasks.

An example demonstrating the gap is
[Johnny-five Piezo](http://johnny-five.io/api/piezo/) implementation. It uses
Node.js timer to control the buzzer. The sound is rough and unstable.
On the contrary, the Arduino based sample program drives the buzzer perfectly.

# First Meet Zumo

When I looked around Github, I found many interesting projects building software
platforms for robots, like

- [gobot](https://gobot.io) - I love Go programming language
- [johnny-five](http://johnny-five.io) - I'm also a fan of Node.js

And also on Amazon, the fun consumer robots make me excited!

As I dive deep into this robotic world, I feel like building one myself, starting
from a simple, cheap model but I can make a lot of fun things - at least I can
program using Go, Node.js or C++.

I asked Google, and Zumo easily grasped my attention. It's a small one, with
track (I love track from day 1, I don't know why, perhaps it makes climbing easier),
simple but with plenty of sensors. I found many projects built on top of Zumo,
proving it's a good platform for customization. And it's cheap, of course
very important to me (as a poor programmer).

I ordered two unassembled kits (Zumo for Arduino and Zumo 32U4), from
[pololu.com](https://pololu.com). My robot journey starts here.

## Assemble Zumo robots

Assembling Zumo robots is not as easy as assembling furnitures from IKEA, or
Lego-like toys by simply plugging components together. Zumo kit requires soldering.
Fortunately, entry-level soldering skill is good enough, and I do have that
experience before. A good solder iron and supporting facilities
(like [this one](https://www.amazon.com/gp/product/B000B61D22)) help a lot.
I recommend 60W solder iron, as the 25W one heats slowly and loses temperature
quickly.

If you don't want to do this dirty work, order the assembled versions.
Or if you don't have experience before, but want to give a try, watch a few Youtube
videos about soldering before you start.

Zumo robots use M2 screws, make sure you have the right screw drivers.

The whole assembling work is fairly easy, it took me less than an hour assembling
the first robot (Zumo for Arduino), and much less for the next one (Zumo 32U4).

Some practice needs to be noted which may help first-time assembly:

- (Zumo for Arduino) There's a mistake in the manual regarding the positive motor leads:

  ![[wrong position]](images/err-motor-positive.jpg)

  It's reversed, it should be:

  ![[right position]](images/fix-motor-positive.jpg)

  If already followed the manual, remember to reverse both the motors in program;

- (Zumo for Arduino) use the two-piece acrylic spacer plate between the chassis and
  Zumo shield. The bigger one-piece spacer plate is not needed here.
  Don't forget to put the spacer plate, otherwise the metal surface of the motor
  may cause shorts with tips of through-hole soldered components.

- Use long screws to mount the blades.

- (Zumo for Arduino) Don't plug-in USB cable when Zumo is powered on from batteries.
  Say in a different way: power off Zumo before plug-in the USB cable.

  It may cause short if plug-in USB cable when Zumo is powered on. I'm not sure
  about this. But from the schematic of Zumo shield, there's no protection.
  Probably, Arduino has power selector, anyway I never tried.

## Use Sample Programs

After assembled, upload sample programs using Arduino IDE. There're plenty of
documents from [pololu.com](https://pololu.com). I'm using the sample programs
to verify if everything is working fine.

To run Zumo for Arduino, I plugged a [Leonardo](https://www.pololu.com/product/2192).

## Next

I'm not very interested in programming for Arduino. The next step is
customizing the robot to be controlled by programs running on Linux.
And the program should have access to Wifi or Bluetooth connectivity.

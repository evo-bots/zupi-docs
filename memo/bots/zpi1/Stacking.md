# Stack Up

## The Stack

Here's the stack top-down:

- [Pi Camera V2 NoIR](https://www.adafruit.com/products/3100)
- [Pan/Tilt Kit](https://www.adafruit.com/products/1967)
- Raspberry Pi 2
- [Servo HAT](https://www.adafruit.com/products/2327)
- [Arduberry](http://www.dexterindustries.com/arduberry)
- Zumo Shield
- Zumo Chassis

## Preparation

To stack up things firmly, standoffs and acrylic plates are used. I bought some
nylon standoffs with screws and nuts from Amazon.com (nylon standoffs are not as
strong as brass, however it is more flexible with deviations in my hand-made
project):

- [M2/M3 spacer/screw/nut](https://www.amazon.com/gp/product/B00MMWDYI4)
- [M2.5 Female-Female spacer/screw/nut](https://www.amazon.com/gp/product/B014J2VCW4)
- [M2.5 Male-Female spacer/screw/nut](https://www.amazon.com/gp/product/B014J1ZLD6)

Different component uses different sizes:

- Zumo base uses M2 screws
- Raspberry Pi, Arduberry, HATs uses M2.5 screws
- Pan/Tilt Kit uses M2 screws
- Camera board uses M2 screws

## Cut acrylic plates

For acrylic plates, [HDPE](https://en.wikipedia.org/wiki/High-density_polyethylene)
is the best material. It's easy to get a 1/8" HDPE board from Amazon:

- [HDPE Sheet](https://www.amazon.com/gp/product/B000ILG0TQ)

Most woodmaking tools and skills can be applied to HDPE, sometimes easier than
wood.

To cut HDPE sheet, a high-teeth hacksaw is good enough. Cutting through wholes from a
HDPE board is a little tricky. I bought a wire saw from Amazon to do this work:

- [Wire saw](https://www.amazon.com/gp/product/B00JLS5HUK)

![[Wire saw]](images/wire-saw.jpg)

To cut a shape in the middle of the board, first drill 1/8 wholes at each corner of
the shape, and then put the wire saw blade (a wire) through the whole, install on
the frame. Now you can cut in the direction you want.

The last thing is sanding papers (I use 60 for fixing the edge and 150 for
finalizing). Sometimes a sharp knife works better than sanding papers.

The picture of a customized HDPE plate with standoffs:

![[Customized plate]](images/customized-power-cable.jpg)

And assembled pictures:

![[Power assembled]](images/power-assembled-front.jpg)
![[Power assembled back-top]](images/power-assembled-backtop.jpg)

## Stack Servo HAT

The [Servo HAT](https://www.adafruit.com/products/2327) is an extension board
(called HAT) for Raspberry Pi to control servos. It's used to control two servos
in [Pan/Tilt Kit](https://www.adafruit.com/products/1967) for camera.

To stack between Arduberry and Raspberry Pi, the packaged GPIO female header
is too short and can't be used.
[GPIO Stacking Headers](https://www.adafruit.com/products/2223) should be used.

And due to the limited space, [Right Angle Headers](https://www.adafruit.com/products/816)
should be used to connect servo cables on the side.

![[Servo HAT]](images/servo-hat.jpg)

It's a little tricky connecting the power. The packaged power connector is not
used because I prefer using jump cables. I soldered two pins and bent them a little
to save the space:

![[Power Servo HAT]](images/servo-hat-power.jpg)

The picture with servo HAT stacked:

![[Servo HAT stacked]](images/servo-hat-stacked.jpg)

## Raspberry Pi

![[Raspberry Pi]](images/raspberrypi.jpg)

Raspberry Pi lays on the top. If Raspberry Pi 2 is used, a USB Wifi Adapter is
needed (Raspberry Pi 3 has built-in Wifi).

![[Pi Stacked]](images/pi-stacked.jpg)
![[Pi Power]](images/pi-power.jpg)

## Pan/Tilt Kit with Camera

Mounting the Camera on the Pan/Tilt kit is not easy. I have to build a small frame
to mount the camera board and fit into the bracket of Pan/Tilt kit.
I cut a small piece of HDPE to fit into the bracket, luckily, the depth of the
bracket is 3/8". After I put 1/4" standoffs behind the 1/8" thick HDPE, the little
frame slides into the bracket perfectly.

![[Camera Mounted]](images/camera-mounted.jpg)

The flex cable shipped with camera board is too short. I ordered a 300mm one from
Adafruit.

![[Pan/Tilt Kit]](images/pan-tilt-kit.jpg)

## Next

The hardware part is completed. Write a simple Node.js with
[johnny-five](http://johnny-five.io) for a test drive.

![[zpi1]](images/zpi1-front-back.jpg)

The next step starts software part, stay tuned...

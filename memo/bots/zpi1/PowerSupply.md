# Power Supply

Using a single power source needs further knowledge about Zumo power supply.
Fortunately, I find out from the schematics. However, this is still the most
challenging but fun part of the project.

## Power Supply in Zumo

It's quite different how Zumo Shield (aka Zumo for Arduino) and Zumo 32U4 handle
the power. I focused on Zumo Shield because I will use it to build **zpi1**.

### Zumo Shield

Zumo Shield simply splits the battery power (`VBAT`) into following paths:

- `VM` input of the motor controller (no regulation, to drive motors)
- Regulated 7.45v to `VIN` pin in Arduino connector, to power Arduino
- One of the blue LEDs (the other two red and one blue LEDs are powered by `VIN`)

It's clear Zumo Shield only connect `VBAT` to motors and one of the blue LED.
The rest goes to Arduino through `VIN` pin. As Arduino may possibly access
external power from its own power jack,
that's why there's an alert in Zumo Shield Manual:

> Warning: When powering the Arduino from the Zumo Shield, you must never connect a different
> power supply to the Arduino’s VIN pin or plug a power supply into the Arduino’s power jack, as
> doing so will create a short between the shield’s power supply and the Arduino’s power supply that
> could permanently damage both the Arduino and the Zumo Shield.

Arduino is powered by 7.45v `VIN` from Zumo Shield, and it generates regulated
3.3v and 5v power back to Zumo Shield for all the peripheral, like buzzer, sensors,
and motor controller (the control logic), etc.

Simply speaking, Zumo Shield doesn't power peripherals on PCB, but powers Arduino
and uses Arduino's output 3.3v and 5v to power the peripherals. Only motors are
directly powered from batteries.

### Zumo 32U4

Zumo 32U4 handles the power in a completely different way, because micro controller
ATmega32U4 is integrated onboard.

Zumo 32U4 utilizes a power selector which allow power to be supplied both from
batteries and USB at the same time. It selects one automatically.

It may simplify the way integrating Raspberry Pi. As I'm not using Zumo 32U4 for
**zpi1**, I'm not digging the details here. I may come back when I start customizing
Zumo 32U4.

### Power Raspberry Pi

#### Connect with Arduberry

[Arduberry](http://www.dexterindustries.com/arduberry/) is actually an Arduino
(with ATmega328 onboard). By connecting it to Raspberry Pi, it allows Raspberry Pi
easily access the Arduino and the peripherals connected.

It provides a simple solution to put in Raspberry Pi where an Arduino is expected.

![[Arduberry]](images/arduberry.jpg)

I'm very happy with Arduberry as it plugs Raspberry Pi to Zumo Shield so easily.

![[Arduberry on Zumo]](images/arduberry-on-zumo.jpg)

However I was confused with one question:

> Raspberry Pi is powered externally, and Zumo Shield provides `VIN` to the
> connected Arduino, why it doesn't cause short?

I googled the projects plugin Raspberry Pi via Arduberry, none of them mentioned
the power issue. All worked out-of-box.

According to the [schematics of Arduberry](https://github.com/DexterInd/ArduBerry/blob/master/Hardware/ArduBerry%20V6_b.pdf),
`VIN` is not connected to Arduberry. That means, with Arduberry, the
power supply from Zumo Shield is completely ignored. That answers my question, and
I no longer worry about short. Though I have to find out a new path to wire the
power from batteries to Raspberry Pi.

#### The `VBAT` and `GND` pins on Zumo Shield

I was so excited when I found `VBAT` and `GND` pins on Zumo Shield PCB:

![[VBAT in PCB]](images/zumo-shield-pcb-vbat.jpg)

It's a considerate design. I can wire `VBAT` to another step-up/step-down
regulator to generate 5v power for Raspberry Pi.

I soldered two pins to connect wires to `VBAT` and `GND`:

![[Wire VBAT and GND]](images/wire-vbat.jpg)

#### The Step-up/down Regulator

The reason choosing Step-up/down regulator, not step-up, because I want to keep
the possibility of using 4 AA alkaline batteries which provides 6v power and has
to step-down to 5v.

I ordered [VERTER 5v boost/buck](https://www.adafruit.com/products/2190) from
Adafruit. Not sure if it can provide enough current. I can replace it if it's
not enough.

The good thing about VERTER is it provides 2 outputs, one to USB, the other to
the pins. I need exactly 2 outputs of regulated 5v, one for Raspberry Pi and
the other for [Servo HAT](https://www.adafruit.com/products/2327).

![[VERTER]](images/verter.jpg)
![[VERTER mounted]](images/verter-mounted.jpg)

It also provides a standard USB female port. I can use standard USB-A to
micro USB cable to connect Pi. However I customized the cable because it was
difficult to hide the standard cable.

![[Customized Power Cable]](images/customized-power-cable.jpg)

To verify the power supply, connect the micro USB to a
[USB breakout board](https://www.adafruit.com/products/1833), and use a multimeter
to check the voltage.

![[USB breakout board]](images/usb-breakout.jpg)
![[Verify power]](images/verify-power.jpg)

The assembled pictures:

![[Power assembled]](images/power-assembled-front.jpg)
![[Power assembled back-top]](images/power-assembled-backtop.jpg)

## Next

The rest of the work is much simpler. I need to customize some acrylic plates
to stack things up. Read [Stacking](Stacking.md) for details.

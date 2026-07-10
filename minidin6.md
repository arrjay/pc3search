What's On The Mini-DIN6?
========================

To better understand where the PC-LINK and i2c fit together, I made a cable so I could more easily splice test points in to the PC-LINK connector. I've included the colors and what pin they go to, per ![mini-din6 reference](/minidin6.webp)

0. Ground/Shield (Uninsulated)
1. Orange
2. Yellow
3. Brown
4. Green
5. Blue
6. Red

The connector shield (pin 0) is indicated by the arrow on my jumper headers.

To connect the jumper headers, connect it _flipped_ - one side should show the arrow, and the other is away from you.

The assembled cable I'm using: ![cable assembly](/debug_cable.webp)

![PC-LINK pinout](/pc-link-pinout.png) is from technical drawings here: https://github.com/4gra/pclk-mn10/issues/1

Continuity with USB Shield?
---------------------------

YES - shield is continuous with USB shield.

If device (the MN10) is _off_ - all pins are to ground/shield.

If device is _on_ - pins 2, 3 stay to ground. Pin 4 does a periodic return to ground....

How Many Volts is Power On?
---------------------------

Measuring Pin 6, Ext On while starting M-CREW shows we swing down to 0.011v. When the M-CREW is not running, this pin floats at 3.3v. The MD deck itself appears to float a 3.3v signal here!

How Many Volts is i2c Running At?
---------------------------------

Something like half a volt? .6? On Pin 5, and I saw a max of .343 On Pin 1. I may be limited by how quickly my multimeter can pick this up, so let's assume it's a 3.3v device given the other voltages present.

Interfacing a Bus Pirate (v3)
-----------------------------

The pins of interest are 1, 3, 5, 6 - I used https://learn.sparkfun.com/tutorials/bus-pirate-v36a-hookup-guide/all to go through the hookup and initial setup using a terminal. Pin 6 is connected to VPU for the pullup resistors. https://www.digitalpeer.com/blog/sniffing-i2c-traffic-with-a-bus-pirate better details the terminal setup, but I've included a session startup here. Bus Pirate should start in HiZ.

```
HiZ>m
1. HiZ
2. 1-WIRE
3. UART
4. I2C
5. SPI
6. 2WIRE
7. 3WIRE
8. LCD
9. DIO
x. exit(without change)

(1)>4
Set speed:
 1. ~5KHz
 2. ~50KHz
 3. ~100KHz
 4. ~400KHz

(1)>3
Ready
I2C>(2)
Sniffer
Any key to exit
```

This should then output any i2c traffic on the bus as sets of hex bits.

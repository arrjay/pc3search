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

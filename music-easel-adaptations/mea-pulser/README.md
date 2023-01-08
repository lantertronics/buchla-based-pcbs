# Adaptation of the Pulser & Inverter from the Music Easel

Clarification: This is not an official product of or associated with Buchla USA.

## Revision 1
Original circuit by Don Buchla; adapted by Aaron Lanterman. This is based on the pulser & inverter circuits on Board of the Music Easel. You should spend some time studying the original schematics.

## Demo
Note this video is of Version 0, so pay no attention to any mention I make of errors on the PCB; those comments are not relevant to Revision 1.

https://youtu.be/TJ0VuxR63E8

## Errors
* There are some errors in the schematic and the silkscreen. Fortunately these only involve incorrect names and values; addressing these issues does not require any trace cutting or jumpering. First note that the "R11" and "R22" labels on the PCB are accidentally swapped; the parts themselves are in the correct place. The resistor closer to the 2N1711 transistor should be labled "R22" and the one closer to the MC14016s should be labeled "R11." Thanks to Dave Brown for catching this error.
* If you look on my Eagle schematic around the 2N1711, you'll see R21, R22, and R28 are 6K8. This is a copy-and-paste error in the resistor values, since only one of them should be 6K8. R21 should be 6.8K, but R22 should be 2.2K (I think - it's hard to tell on the original Buchla schematic, it looks like it might be 22K?), and R28 should be 100R. Thanks to Dave Brown for catching these error; I never tried hooking an LED or light bulb up, so I never noticed this error before. Dave also noted that the 100R values for R28 may be specific to using an incandescent bulb.

## Notes
* **I am convinced that the 50K sliders marked on the original schematics should actually be 10K linear.** The 120K input and shaping resistors (R105, R106, R107, and R108) are off-board in the original Easel, but included on-board in this adaptation.
* The original Easel has a 13.5 V supply, created using an op amp and a transistor. If you have such a supply, you may hook it to the +13.5 pin and omit R103 and R104. Otherwise, leave the +13.5 pins unconnected and use R103 and R104, which create a "soft" +13.5 V supply. **I found it important to lower R103 to something like 3.3K to counteract loading, so I marked R103 as 3.3K on the PCB.** You may want to experiment with other values.
* The circuit has been tested with RC4558s, which was deemed to be electrically similar to the original RC4136s used in the Easel. Other op amps will probably work (many will probably work better!), but they have not been tried.
* D3-D6 are 1N457s. I suspect a 1N4148s or a 1N914 will work, but I have not tested them.

## Connections
Front panel connections usually have a square and round pad together in a white box. The round pad is the signal, and the square pad provides a convenient ground.

* PIC, PIO, FB - Pulse Input Common, Pulse Input One-Shot, and Feedback. You want to try to find a single-pole on-off-(on) switch, where the (on) indicates momentary operation. Hook PIC to the common switch terminal, hook PIO to the (on) terminal, and hook FB to the regular on terminal. This will let you do just one "pulse," or if you switch to the feedback mode quickly after doing one pulse, the pulser will drive itself and you will get repeated pulses. The middle position turns off the pulsing. If need be, you could just use a regular on-off-on switch here.
* PCVA, PCVB - Pulser CV outputs A and B. A is active when AEN is set high; B is active when BEN is set high.
* PPA, PPB - Pulser pulse outputs A and B. A is active when AEN is set high; B is active when BEN is set high.
* Y1, Y2 - terminal of an electronic switch; connection made when BEN is set high (untested).
* Z1, Z2 - terminals of an electronic switch; connection made when BEN is set high (untested).
* ANOT, BNOT - logical "not" of AEN and BEN
* AEN, BEN - A and B enables; see other connection instructions for details of what they enable. I plan to connect these to a switch that will let be switch between automatically-on (connect to +15 V) and connect to an external input. Most users will probably just want to tie AEN to +15 so the A outputs are always enabled. Some users may want to just ignore the B outputs entirely. Some might want to only use the "B" part of the circuit to control the Z1,Z2 and Y1,Y2 electronic switches, and ignore the pulser B outputs. Do whatever makes you happy.
* INVI, INVO - inverter input and output; takes 0-10 V CV and outputs 10-0 V CV. The inverter is independent of the rest of the pulser, so you can invert whatever CV signals you want.
* LED - on the Easel schematics, this is actually called "LAMP" and is shown going through a lamp-looking symbol to a +12 V supply. I haven't tried doing anything with this, since it's a low priority for me, but if someone can get something to light up I'd love to hear about it.

## Potentiometers
* LOS - Level (pulser rate) Offset
* LCV - Level (pulser rate) CV; controls amount of influence of the LIN input
* TRIM - Trims the pulser rate - set to personal taste

## Disclaimers
* These should be considered advanced projects, and should only be attempted by people with extensive knowledge and experience in electronics, particularly in terms of practical construction and debugging techniques. The boards are dense and the documentation is sparse. If you are just getting started with Synth DIY, I recommend starting with kits.
* If you try to build one of these projects, you must assume that you will be on your own, and be confident enough to tackle the project under those circumstances. I am interested in learning about people's experiences in building the boards, and will try to answer questions over e-mail, but I don't have time to do any hand holding.
* Any PCBs made available to the public are provided as-is, with no guarantees or warranties whatsoever. Similarly, no guarantees or warranties are made about the correctness or usefulness of the information on these webpages.
* Any electronic project may present a risk of injury or death, particularly when dealing with mains voltages. It is important to follow appropriate safety practices. The author of this post, Aaron Lanterman, disclaims any liability for injury, death, or other damage caused in using the PCBs or any of the information contained on these webpages.

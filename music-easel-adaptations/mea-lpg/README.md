# Adaptation of the Low Pass Gate from the Music Easel

## Revision 1
Original circuit by Don Buchla; adapted by Aaron Lanterman. This is based on the lowpass gate circuit on Board 10 and Board 11 of the Music Easel, which contains two identical LPG circuits. You should spend some time studying the original schematics.

## Notes
* The holes and traces on the Revision 1 PCBs are the same as on Version 0. The only changes I made were to the silkscreen. I forgot to put a "Rev 1" marking on the board. You can tell it is a "Rev 1" board if it says "BEAD" in the spots near the power connector; the older version said "2R2." 
* **I have not been able to get the LED to light. I do not know why.** (It appears that one of my beta testers has gotten an LED to light, though.)
* **I am convinced that the 50K sliders marked on the original schematics should actually be 10K linear.** The 120K input and shaping resistors (R105, R106, R107, and R108) are off-board in the original Easel, but included on-board in this adaptation.
* The original Easel has a 13.5 V supply, created using an op amp and a transistor. If you have such a supply, you may hook it to the +13.5 pin and omit R103 and R104. Otherwise, leave the +13.5 pin unconnected and use R103 and R104, which create a "soft" +13.5 V supply. In testing, this was found to droop to between 9 V and 11 V depending on pot settings, resulting in me being unable to open up the filter all the way using just the LOS pot. **I lowered R103 to 3.3K, and found that this helped counteract the droop and I got a reasonable full-range control, so I marked R103 as 3.3K on the board.** You may want to experiment with other values for R103. An alternative would be to keep the R103/R104 ratio the same but lower the overall values, such as reducing R103 to 1K and R104 to 9.1K. However, I have not tried this.
* **The area around the vactrols is tight; be sure to install R42 and R41 before installing the vactrols.** Also, the 910 pf silver mica caps are pretty big; to get them installed I had to leave them kind of floating above most of the other parts.
* Q2, the buffer JFET, is a 2N4340 in the original. I picked the J201 since it happened to come with the preinstalled Eagle libraries. I used an actual J201 in my build and it worked fine. Any JFET you have previously successfully used as an audio buffer should work fine here.
* The need for R100, the 68K input resistor, was gleaned by studying other parts of the original Easel schematics.
* The circuit has been tested with RC4558s. Other op amps will probably work (many will probably work better!), but they have not been tried.
* The regular diode in the original is a 1N457. I suspect a 1N4148s or a 1N914 will work, but I have not tested them.
* Dr. Mabuse has run into a problem with excessive current draw cooking parts. I personally haven't been able to reproduce whatever the problem is. I would be very interested to see if other people do (or don't) run into this problem.
* Dr. Mabuse reports that a 0.001 uf cap (i.e. 1 nf) works fine in place of the 910 pf cap around the LED-driving 2N1711 transistor; this lets you save 910 pf micas for more critical audio path applications.
* Dr. Mabuse writes: "Another sub that I decided against but still yielded useful and interesting results was swapping a single VTL5C3/2 for two VTL5C3s. It works both as a filter and as a VCA but the response curve is noticeably different (not as even and smooth) and the VCA mode didn't attenuate quite as much. In a pinch it think it could be used though."

## Connections
Front panel connections usually have a square and round pad together in a white box. The round pad is the signal, and the square pad provides a convenient ground.

* LIN - Level CV Input; amount of influnce controlled by setting of LCV pot
* AIN - Audio input
* AO - Audio output
* LED - Hooks to the cathode (straight line part of symbol, shorter leg of actual device) of an LED; the anode (triangle part of symbol, longer leg of actual device) of the LED is hooked to +5 V.
* SWV, SWC, and SWL - Connections for the mode switch. Use a SPDT on-off-on switch. Connect SWC to the common connection, SWV to the lower connection, and SWL to the upper connection. Switching to connect SWC to SWL puts the filter in lowpass mode; switching to connect SWC to SWV puts it in VCA mode, and switching it to the "off" position puts it in "combo" mode.
* CIN - Control input. CV input for mode control; amount of influence is controlled by the CCV pot. If +13.5 V is input here, then the resistance of CCV corresponds to the resistor setting on an Easel programming card, but you can put in all sorts of varying voltages here. I have not tried to puzzle out exactly what effect this has, i.e. how many volts at a given pot setting is required to change modes, etc., but I have made it switch modes. This input piles "on top of" the switch setting, so its influence will change with switch settings.
* B10P1 - Analogous to Pin 1 on Board 10; maybe useful if you are using this to replace an original Easel board. Most users will not need this.
* B10P9 - Analogous to Pin 9 on Board 10; maybe useful if you are using this to replace an original Easel board. Most users will not need this.

## Potentiometers
* LOS - Level Offset
* LCV - Level CV; controls amount of influence of the LIN input
* CCV - Control CV; controls amount of influence of CCV. I specified 300K here, but I largely pulled that number out of a hat. I would suggest a linear pot, but I'm really not sure if a log or linear pot would be best. If +13.5 V is put into CIN, then CCV corresponds to the resistor setting on an Easel programming card, but you can put in all sorts of changing voltages for CIN.

## Disclaimer
* These should be considered advanced projects, and should only be attempted by people with extensive knowledge and experience in electronics, particularly in terms of practical construction and debugging techniques. The boards are dense and the documentation is sparse. If you are just getting started with Synth DIY, I recommend starting with kits.
* If you try to build one of these projects, you must assume that you will be on your own, and be confident enough to tackle the project under those circumstances. I am interested in learning about people's experiences in building the boards, and will try to answer questions over e-mail, but I don't have time to do any hand holding.
* Any PCBs made available to the public are provided as-is, with no guarantees or warranties whatsoever. Similarly, no guarantees or warranties are made about the correctness or usefulness of the information on these webpages.
* Any electronic project may present a risk of injury or death, particularly when dealing with mains voltages. It is important to follow appropriate safety practices. The author of this post, Aaron Lanterman, disclaims any liability for injury, death, or other damage caused in using the PCBs or any of the information contained on these webpages.

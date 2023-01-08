
# Adaptation of the Balanced Modulator from the Music Easel

## Revision 2
Original circuit by Don Buchla (used with his kind permission); adapted by Aaron Lanterman. This is based on the balanced modulator circuit on Board 5 of the Music Easel. You should spend some time studying the original schematics. Warning: This board is designed to be highly flexible; it can be configured in many different ways. Please read the notes below carefully and decide what options you want before building.

## Demos
Note this is a demo of Version 0. Revision 2 doesn't require all of those horrible kludges seen in the video.

https://youtu.be/UKisZpQu2Dk

https://youtu.be/v0InHm5aHvE

## Notes
**I am convinced that the 50K sliders marked on the original schematics should actually be 10K linear.** The 120K input and shaping resistors (R117, R118, R119, R120) are off-board in the original Easel, but included on-board in this adaptation.
The original Easel has a 13.5 V supply, created using an op amp and a transistor. If you have such a supply, you may hook it to the +13.5 pin and omit R115 and R116. Otherwise, leave the +13.5 pins unconnected and use R115 and R116, which create a "soft" +13.5 V supply. You may want to experiment with changing these settings a bit, for instance lowering R115 and R116, to counteract loading. **I found that lowering R115 from 10K to 3.3K is seemed to work well.**
If you want to use the FO fuzz output, **you should add a 0.1 microfarad DC blocking cap, like the FOA and FOB outputs have.** It should be pretty easy to add this somewhere on the way between the board and the FO jack.
The circuit has been tested with RC4558s. Other op amps will probably work (many will probably work better!), but they have not been tried.

## Connections

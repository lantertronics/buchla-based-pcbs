# Adaptation of the Envelope Generator from the Music Easel

Clarification: This is not an official product of or associated with Buchla USA.

## Revsion 1

Original circuit by Don Buchla; adapted by Aaron Lanterman. This is based on the envelope generator circuit of Board 3 of the Music Easel. You should spend some time studying the original schematics.

## Demo

https://youtu.be/BBpSuDe31xM

## Notes
* The holes and traces on the Revision 1 PCBs are the same as on Version 0. The only changes I made were to the silkscreen.
* **I am convinced that the 50K sliders marked on the original schematics should actually be 10K linear.** The 120K input and shaping resistors (R117 through R128) are off-board in the original Easel, but included on-board in this adaptation.
* The circuit has been tested with RC4558s, which was deemed to be electrically similar to the original RC4136s used in the Easel. Other op amps will probably work (many will probably work better!), but they have not been tried.
* Buchla went to the effort to specify 1N457 in one instance and 1N457A in another instance, so I'd be nervious about changing what dioes are used. I'd be curious if to know if other diodes, such as 1N4148s or 1N914s, will work.
* Bjorn wrote: "I am not sure whether a solution to get the transient function of the envelope generator with a regular gate signal has been proposed yet. Anyways, I have been able to get this functionality by replacing R101 with a 10nf cap."

## Connections
* Front panel connections usually have a square and round pad together in a white box. The round pad is the signal, and the square pad provides a convenient ground.
* ATIN, DURIN, DECIN - attack, duration, and decay CV inputs; influence is controlled by ATCV, DURCV, and DECCV settings, respectively
* PIN - pulse input
* B3P6 - corresponds to original Easel Board 3, Pin 6
* TRAN, SUS - connect TRANS and SUS to the extremes of a single-pole on-none-on switch, and connect B3P6 to the common terminal of this switch. This lets the user switch been "transient" and "sustained" modes. (Note I only tested the transient functionality.)
* POUT - pulse output
* ENVOUT - envelope output
* LED - on the Easel schematics, this is actually called "LAMP" and is shown going through a lamp-looking symbol to a +12 V supply. I haven't tried doing anything with this, since it's a low priority for me, but if someone can get something to light up I'd love to hear about it.
* +13.5 V - a supply created using a buffer op amp (most users will not need this)

## Potentiometers
* ATOS, DUROS, DECOS - attack, duration, and decay offsets
* ATCV, DURCV, DECCV - attack, duration, and decay CV controls; control influence of ATIN, DURIN, and DECIN inputs, respectively

## Disclaimer
* These should be considered advanced projects, and should only be attempted by people with extensive knowledge and experience in electronics, particularly in terms of practical construction and debugging techniques. The boards are dense and the documentation is sparse. If you are just getting started with Synth DIY, I recommend starting with kits.
* If you try to build one of these projects, you must assume that you will be on your own, and be confident enough to tackle the project under those circumstances. I am interested in learning about people's experiences in building the boards, and will try to answer questions over e-mail, but I don't have time to do any hand holding.
* Any PCBs made available to the public are provided as-is, with no guarantees or warranties whatsoever. Similarly, no guarantees or warranties are made about the correctness or usefulness of the information on these webpages.
* Any electronic project may present a risk of injury or death, particularly when dealing with mains voltages. It is important to follow appropriate safety practices. The author of this post, Aaron Lanterman, disclaims any liability for injury, death, or other damage caused in using the PCBs or any of the information contained on these webpages.

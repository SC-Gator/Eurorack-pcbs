# Eurorack-pcbs
A collection of easy to solder DIY eurorack PCB's. All IC's are SOIC or DIP, passives are 1206 or THT for ease of soldering. There are also faceplate drill templates and graphics that can be used for toner transfer. Some utility modules are set up as 1u pcb's so you can mix and match 3 at a time in a standard 3u panel with only 1 eurorack power connector needed. 

![modules](https://i.imgur.com/BY2SObw.jpg)

# PCB status summary:
VCA: ready to build, digikey bom provided

VCO: ready to build, digikey bom provided, minor rework needed for V1.0, V2.0 ok. 

Mult: ready to build, see interactive BOM for parts list, there's only like 3

Mixer:
Update 2019-04-28: prototypes built. I reversed the supply rails on the TL072 in the kicad schematic lol. That means I need to flip the power header, and change some silk around. I should have this one released in a week or so.

Update 2019-05-15: prototypes are working. I gotta put the revision together to fix the reversed supply issue, but my job is kicking my ass right now, so it could be a month or more before I get around to it. If you're desperate for a cheap mixer, shoot me an email and I'll send you V1 files. Rework of V1 consists of flipping the euro power header and bypass caps 180 deg from the silk on the PCB layout. 

~1u LFO: ready to build, minor rework needed for V1.0 !!There's a stalling issue at low frequency I can't figure out!! see the issues page for details~ You probably don't want to use this. I'm too dumb to figure out the stalling issue, so these are only good for 50hz-->audio rate modulation. I did a layout of David Haillant's LFO with SMD components, but I haven't asked permission to share the files yet. Watch this space. 

3->1 averager/mixer: Prototypes tested and working. Doing cleanup for release (bypass caps intefere with plugging the damn thing in)

1u 1->3 mult: schematic finished, pcb layout in queue

VCF: low priority for now--> maybe I'll make a tranisitor ladder VCF. 

VCS: PCB's are in, waiting on circuit designer permission and prototype build to post files


# General Notes

**IMPORTANT:** Do not plug these in backwards. First of all, they don't have any reverse polarity protection so it will probably kill the module. Second of all, I have no idea (and can't be responsible for) what will happen to the rest of the modules in your system if/when you do upend the power rails. Maybe I'll get around to adding rpp eventually, but for now I'm living dangerously by relying on shrouded headers. 

Most of these are not my circuit designs. I simply put them in kicad and did PCB layout for eurorack format. I'm a mechanical engineer, not an electrical one, so there may be minor (major lol) mistakes or violations of standard practice. I have tested all for functionality though. I can provide very limited support via email, but when it comes to troubleshooting, you're likely on your own. 

Pots and jacks aren't included in any digikey or mouser carts. You want these ones if you're in the US: 

https://modularaddict.com/parts/synth-diy-parts/9mm-potentiometers

https://modularaddict.com/parts/jacks/pj301m12-jacks

Or similar from Thonk if you're in Europe.

Switches can be hard to find. I've had a great experience with taiway switches from these people: 

https://lovemyswitches.com/categories/switches/toggle-switches/mini-toggle-switches.html

Plus they have switches with adorable little stubby levers. ~PCB's will accomodate "PCB mount" or "solder lug" style.~ Get PCB mount style for the moment. The current (2/2019) toggle switch footprint through holes are slightly narrow, so solder lug style switches require a little sand paper-ing of the terminals to fit.  

Faceplates: 2mm aluminum works perfectly. Regular drill bits will work, and you can cut it with woodworking tools if you're super careful. If you can't get ahold of that, go to a hobby or art store and get some 1/8" aircraft birch ply. It's thin but strong. I have been using toner transfer to print graphics and labelling onto the panels. It works for aluminum or wood and results in a distressed look that I kinda like. You can find a tutorial at instructables (https://www.instructables.com/id/Transfer-PHOTOS-to-METAL/) but here's the bullet points: 

1) Buy *water* based poly from the wood finish section of a hardware store. Paint a thin layer on the faceplate. 

2) Print out your design on a laser printer in reverse and stick it on the *wet* poly. 

3) Let it dry. I stick it in a warm oven to speed up the process.

4) Wet the paper, and gently rub it off. You don't need to get it all in 1 shot. You should repeat the drying and wetting/rubbing cycle 2 or 3 times to get the paper off without removing too much toner.

5) Hit it with another layer of poly for protection. 

PCB fab houses: I really like Aisler, but they are kind of expensive and shipping takes 2 weeks to the US. They can definetly handle all of the features in these PCB's. I have also used oshpark with good results. JLCPCB is a cheaper option, even with 3 day DHL shipping to the US. All three can handle the plated slots for the jack and switch footprints with no problem.  

# Dual log/lin VCA: 

![VCA](https://i.imgur.com/jjCLWQ9.jpg)

Design: Ray Wilson (please visit http://musicfromouterspace.com/)

Design alterations: None

Tested working 2019-02

Required kludges: The screw holes on the drill template are in a nonstandard spot. Adjust accordingly if you care

Notes: This one is super easy and goes together in less than an hour. It's a 2 board pannelized design. Make sure your PCB fab house can handle internal slots for the switch footprint and pannelization. (oshpark and aisler did it without issue.) I may revise this to a one board design in the future to reduce PCB costs. 

# VCO: 

![VCO](https://i.imgur.com/5RcPoAI.jpg)

Design: Ray Wilson (please visit http://musicfromouterspace.com/)

Design alterations: None

Tested working 2019-02

Required kludges: 

V2.0: Eurorack pwr connector interferes with pot feet on front of board. Simply bend one of the pot feet out of the way so it doesn't       contact the -12V side of the pwr connector. This is unlikely to be fixed in the near future unless someone else wants to reroute around a new power connector location. 

~V1.0 outer potentiometer leads for RV1 and RV2 are reversed and need to be jumpered (X style) to the correct holes.~

~Silk showing polarity for C12 is reversed (+ side of C12 should be at GND).~

~Eurorack pwr connector interferes with pot feet on front of board. Simply bend one of the pot feet out of the way so it doesn't       contact the -12V side of the pwr connector.~

Notes: U2 is really far away from U4. Use lots of flux and make sure that U1-U4 are soldered really nicely, otherwise it won't work. U5 has several pins that are not connected (specifically 2, 9, 10, 12, 15, 16). Depending on the PCB fab you use, they might instantly delaminate. Don't freak out, it's not a problem. There are some trimpot through holes that intersect jack footprints, so make sure you solder the jacks last, and clip the trimpot leads flush with the board.

# Mixer: 

Design: I guess this one is my own, but heavily influenced by information from Ray Wilson (please visit http://musicfromouterspace.com/)

Tested working 2019-02 (breadboard only)

Required kludges: N/A

Notes: PCB layout is incomplete as of 2019-02. This is a DC coupled (CV capable) 4 into 2 or 8 into 1 mixer. It's based off of Ray's mixers, but is simplified in that the switchable high gain channel has been replaced by a normal one. I have one of these running in my system right now that's just dead-bugged to the back of the faceplate. PCB layout is nearly completed, 

# Utility LFO (8K LFO)

![Util_LFO](https://i.imgur.com/B9UOJxG.png)

(disregard the tht resistors, I ran out of smd ones, so I just bodged some on there.)

Design: Tim Parkhurst: Magic Smoke Electronics (http://electro-music.com/wiki/pmwiki.php?n=Schematics.MagicSmokeLFODesignByTimServo)

Design alterations: None

Tested working 2019-02

Required kludges: 
V2.0: Stalling may still be an issue at low freq. I'm working on that, see issue #14 if you can help. 

~V1.0:Coarse pot leads (RV11) are reversed. Swap them with jumpers. You also need to bend one of each pot support legs up under the pot to avoid the power chain pads. This circuit is stalling out at slow settings right now. See issue #14 if you can help explain why.~

Notes: This is shrunk down to be a 1u module. There are power chain jumpers so that you can put 3 of them in a standard 3u tall panel with only one eurorack pwr connector,  or you could build 1 and put it in a 1u tile. Pots are super close together, so the max knob size you can put on them is 13mm diameter. Davies 1900H clones from thonk or modular addict (or wherever) will be ok. 

# Buffered Mult

![mult](https://i.imgur.com/NJwEe1J.jpg)

Design: Michael Barton (http://www.bartonmusicalcircuits.com) 

Design alterations: None

Tested working 2019-02

Required kludges: None

Notes: This one is actually THT. It's a super simple but emminently useful utility module. The only tip here is to make sure you place J10 and J13 before the power header if you use a shrouded connector. Otherwise the plastic shroud will cover up the tip connections. Provided with permission from Michael Barton. 
    

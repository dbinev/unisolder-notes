# unisolder-notes
Just a set of notes for anyone who is trying to build his unisolder controller.
It is intented to be a personal recap of the original topic on dangerousprototypes.com forum.  
If you are reading this after i finished my project (so you are in the future, WOAH!), probably i'm not updating this document anymore. If it was useful to you, please help to keep it updated, by modifying the document and making a Pull Request. The community will thank you.  
**I'm currently building this project, and this page is a work in progress, so the info may not be 100% accurate and tested. No warranty is given.**

## General notes

### Soldering and mounting
No hot air or reflow oven si required, it can be soldered by hand and soldering iron.  
Sparkybg reccomends BGA no-clean flux.

### Configuration resistors
There are some configuration resistors, please make sure to pick the correct values for your application. Those are listed in the *Equivalent parts in bom* section of this document.

### Power supply
The controller can be powered anywere from 9V to 24V, AC or DC. However, since the current is limited to 6Arms, more voltage means more power to the iron.  
A **toroidal** transformer is recommended: **24V 120VA.**  
Although this is not fully recommended you can use a 24V DC supply, because of grounding difficulties in switching PSUs. There are two power input ports on the *"back"* pcb. One is for AC, the other is for DC.

### OLED display configuration
The project is capable of using either a 7 segment display or an oled display.  
If you want to use the oled display, there are some components that you can remove from the BOM and some pads to short.
* Ensure to get a SSD1306 128x64 oled. 
* Q15, Q17 and UL2003N are not needed.
* Ra to Rg are shorted 
* Ja to Jg are shorted  
* Short, on the back side of the front pcb, the pins that have some soldermask free pads arround, with the pads.

## Equivalent parts in bom
Some parts are not really easy to find. Some of them can be substituted easily

### Rs1 shunt resistor, R37, R42
0.003 or 0.004 ohm resistor can be used as a shunt.  
If you use **0.003** ohm shunt, R37 and R42 have to be both **1.5k** 0.1%.  
If you use **0.004** ohm shunt, R37 and R42 have to be both **2.0k** 0.1%.  

### 3v and 3.0v zener diodes
Despite the different name in the BOM, the same part can be used for both.

### Rgnd1
This resistor is in a 2512 format, 10M, it is there to prevent huge electrical potentials between the computer's ground and the station's ground.  
You can use any value between 1M and 10M, or leave it disconnected if you feel safe, anyway this isn't recommended.

### Q10, Q11: IPD053N08
If you want to change this part, pick a part which has same: package, Rds(on), Vds, and gate threshold voltage.

### Rc2 Bourns trimmer
In BOM it's indicated as Bourns 3362, this part is a THT trimmer from a previous version, correct part number is Bourns 3364X-1-202E.  
I've ordered 3314J-1-202E, not mounted yet. It seems it can fit, but i'm not sure yet. 

### J5 RJ11v
This is just an RJ11 vertical connector. I found that Molex 95522-2667 fits perfectly. 

### SOD123 diodes
SOD123 diodes can be used also in miniMELF packages. Check in the document to see which parameters are important, to find a substitute.  
If you can't find the part you are looking for, just ask in the thread and please open an issue/pull request to update the document. 

### SOT223 
Footprints for the SOT223 components are also compatible with DPAK packages.

### SR580 
SR580 means "Schottky rectifier, 5A, 80V". There's nothing special about these diodes. Just use 5A 80V Schottky.


~~Currently i'm on page 9 of the topic. This is just a reminder for myself, ignore it~~
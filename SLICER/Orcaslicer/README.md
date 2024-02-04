Everything I used to setup Orcaslicer with my BIQU B1. Used with OrcaSlicer v1.9.0

Orcaslicer has a nice built-in preset for this printer but I wanted to optimize it.

(printer)
I updated the printer to marlin 2 so I modified the following in the default config:
- gocde flavor (marlin 1 -> marlin 2)
- nozzle type (undefined -> brass)
- gcode optimization (see below)
- removed gcode speed limits (so firmware will be the limiter instead as the printer will use the lower value of the 2 -- firmware vs slicer)

(filament)
I only print in PLA so I created a PLA profile from the default one and changed:
- nozzle temp (220C -> 215C)
- cooling overhang threshold, hoping to get better overhangs (50% -> 25%)

(profiles)
I think all the stock profiles are fine for now, need to do some fine tuning but I changed:
- enabled "avoid crossing walls" to get better surface quality
- enabled "precise wall" for better accuracy
- disabled skirts
- disabled brims
- changed output gcode to include layer height used

(gcode optimzations)
Decided to have temps warm up in parallel vs sequentially. Results in a faster start up time at the expense of higher peak current draw in the beginning. Was worth it to me and I wanted to optimize it more. I only print PLA so the gcode temperatures reflect that, change the temps for your filament of choice. 

I found that the hotend heats up way faster than the bed so the bed starts then the hotend starts after the bed reaches 40C. Doing this allows them to reach optimal temperature almost at the same time, reducing downtime before a print and electricity wasted while waiting idly.
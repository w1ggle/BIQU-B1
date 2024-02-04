Everything I used to setup Prusaslicer with my BIQU B1

Bed model:
https://www.thingiverse.com/thing:4822571/files

I only print PLA so the gcode temperatures reflect that, change the temps for your filament of choice. I found that the hotend heats up way faster than the bed so the bed starts then the hotend starts after a delay. Doing this allows them to reach optimal temperature almost at the same time, reducing downtime before a print and electricity wasted while waiting idly.

Slicer profile i just went through manually but did not touch machine limits (this will be limited by the marlin firmware as the printer will use the lower value of the 2 -- firmware vs slicer)

Used with Prusaslicer v2.5.0 - v2.7.1
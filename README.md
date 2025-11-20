# MC14529 Replacement #

This repository contains the design for a CPLD based
replacement for the long obsolete MC14529 analog
multiplexer. The design is intended only to act as a
substitute in the Dragon 32/64 computers.

![render of pcb](./Next4529.png)

## Limitations ##

The current implementation is functionally complete but
there is an idiosyncracy of the controlling CPLD that
needs to be noted. At startup all control outputs are
floating until each ones goes into a high (on) state,
the result is that the route of any switch will non-
deterministic until positively switched.

## Design ##

The design is based around the Renesas SLG46824 CPLD.
This is a 3mm x 2mm device (about the size of a 1/4W
leaded resistor). The CPLD reproduces the truth table
of the original device.

The actual multiplexing is performed by an array of
LS74LVC1G3157 analog SPDT switches. These are available
in very small (1mm x 1mm) packages allowing eight of them 
to be fitted in the available space.

The output inhibit is performed by two more SPST
switches.

The board design retains the footprint of a DIP-16
component. To necessitate compliance with the available
space the PCB is 6-layer and utilises minimum sized vias
and routing. This may limit signal fidelity. Where possible
signal routing is increased in width and is kept separate 
from control routing.

## License ##

This project is licensed under creative commons CC-BY-SA 4.0

Artillery Sidewinder X4 Plus screen service for Klipper

From Tortillery firmware for Artillery Sidewinder X4 Pro/Plus (also S1) 3D printers this is the standalone KlipperLCD service.

Unzip the archive into the user directory used for Klipper.

Copy KlipperLCD.service into directory /etc/systemd/system
and activate it with command: 

sudo systemctl enable KlipperLCD.service

Copy firmware file 800_480.tft into a microSD <=32GB formatted in FAT32 file system,

remove the display from printer, open it removing the 4 screws, put the card into the microSD slot connect the display to power on and will flash this firmware.

Disconnect the display and remove the microSD. Close display connect and switch off/on the printer.

Check the various function.

For gantry light to work from display you need two macros with following names:

[gcode_macro GANTRY_LIGHT_ON]
description: Turn on Hotend LEDs
gcode:
   SET_PIN PIN=lightbar VALUE=1

[gcode_macro GANTRY_LIGHT_OFF]
description: Turn off Hotend LEDs
gcode:
   SET_PIN PIN=lightbar VALUE=0

The screen menu has the Screw Tilt Calculate command, but you need to add into yout printer.cfg the following lines for X4 Plus and Plus S1. For X4 Pro remove 2 middle screws and set the 4 corner screews changing values.

[screws_tilt_adjust]
screw1: 40, 3
screw1_name: front left screw
screw2: 290, 3
screw2_name: front right screw
screw3: 40, 135
screw3_name: middle left screw
screw4: 290, 135
screw4_name: middle right screw
screw5: 40, 265
screw5_name: rear left screw
screw6: 290, 265
screw6_name: rear right screw
horizontal_move_z: 10.
speed: 90.
screw_thread: CW-M4

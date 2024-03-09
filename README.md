# 9 Pin Joystick to USB Adapter
Firmware for the 9 Pin Joystick to USB Adapter https://monsterjoysticks.com/9-pin-joystick-to-usb-adapter

I was getting constant UP UP UP pressed contantly without no controllers attached with Stella on Linux arm64 on a Raspberry Pi5.

This PCB worked about 20% of the time for me.

I removed the auto detect and turned on all bits. 

UP UP UP issue was resolved. 

Atari 2600 controller works as expected. I don't know why the original just didn't turn on all the bits for the DB9 port. Original code seems be overly complicated / over engineered.

Only the db9.c file was patched. 

References:
https://github.com/qmk/qmk_firmware/blob/master/docs/flashing_bootloadhid.md

db9 pcb from UK:
https://monsterjoysticks.com/9-pin-joystick-to-usb-adapter

BootloadHID website:
https://www.obdev.at/products/vusb/bootloadhid.html

The coolest part, HID Example projects:
https://www.obdev.at/products/vusb/projects.html

You can use the adapter to connect any of the following devices via USB
* Mini Monster Retro Gaming Joystick
* Atari 2600 Joysticks
* Atari ST Compatible Joysticks
* Amiga Compatible Joysticks
* Commodore 64 Compatible Joysticks
* SEGA Master System Controllers
* SEGA MegaDrive/Genesis Controllers (3 & 6 Button variants)
* Amiga CD32 (Hold up when connecting USB to enable CD32 Compatibility) [This may not work with this fork]

The adapter is detected as a USB HID joystick and is compatible with the following;
* Windows
* MacOS
* Ubuntu on Intel and RaspberryPi5 arm64.

# Updating the Firmware

Once you have compiled the firmware hex file you can use the BootloadHID <https://www.obdev.at/products/vusb/bootloadhid.html> command line utility to flash the file to the device via USB. 

You will just need to change the position of the small switch on the device so that it is closer to the 9 pin connector and then connect the device to your computer via USB. once connected the bootloadhid software should be able to flash the device, you can then return the switch to it's original position and reconnect the USB cable.

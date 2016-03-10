# Raspberry Pi troubleshooting
==============================
The RuneAudio Player is designed to run "headless", but under some circumstances, connecting an HDMI monitor and USB keyboard can be helpful.
##Raspberry Pi not booting
The causes may include a poor power supply, SD card problems, physical connection problems, software issues, USB devices, and other hardware more-or-less in that order. 
###Power supply and power LED
When the power supply turns on and reaches 5V, the red LED turns on and stays on.  If the LED does not turn on, blinks, or dimms, there is a problem with power.

###Boot sequence failures
Unlike a PC, the Raspberry Pi does not have a BIOS, so without a working software image, it is stone-cold-dead.  Without a working OS, and if the power supply works, the only thing guaranteed to happen is that the red power LED turns on.  If an image at least starts to boot, then looking at the status LEDs and the HDMI monitor can provide some indication of where the boot process failed.

###Bad or missing SD card
Using a Raspberry Pi 2 as an example, if there is no activity on the monitor and if the red and green status LEDs stay lit and un-blinking after power up, the SD card may not be fully inserted, not detected properly, not flashed or not formatted correctly.

###Normal boot sequence
If the SD card is working, the RuneOS loads within a few seconds after power up, much faster than a typical PC or Android device.  A class 10 SD card loads about twice as fast as a class 4, and 50% faster than class 6.

While loading the operating system, a blinking green ACT LED indicates SD card activity. Assuming the SD card has been flashed correctly with the OS, a Raspberry Pi 2 boot sequence looks something like this:

1) Red Power LED and green ACT (Activity) LED turn on

2) Red LED stays on, green LED turns off

3) A rainbow splash screen appears on the monitor (if connected)

4) Rainbow screen turns off, text scrolls on the monitor, green SD card activity LED flashes rapidly

5) Linux login prompt appears on the monitor

6) Green LED continues to flash a few seconds while software is loading from the SD card

7) Rune UI can now be invoked in a browser

###Rainbow screen
The rainbow flash screen only appears for about a second.  If the boot process halts with the rainbow screen on the monitor, there may be a power supply issue, or a kernel software problem.

###USB power management
The Raspberry Pi has very good power management.  Power consumption increases gradually over a few seconds as peripherals and USB devices are powered on in steps.  This is a good thing, because a power hungry or defective USB device can't kill the boot process completely.  If the red LED starts to slowly blink or dims during or after boot, there is a power supply issue. The normal power allowance is 150mA (0.15A) per USB port (much less than a normal PC).

On a Pi B+ and Pi 2, this can be increased (using a parameter in the /boot/config.txt file) to about 300mA per USB port, or 1.2A total.  As a practical result, the Pi B+, Pi 2 and later models can better support WiFi dongles, wireless keyboards, mice, etc.

###Kernel panic
The text scrolling on the screen shows various parts of the OS being loaded.  If the boot process halts with text on the screen (other than a login prompt), it may indicate a problem such as a corrupt SD card, a failed software update, power failure during SD card write, etc.  This is also known as Kernel Panic, the Linux equivalent of a BSOD (Blue Screen of Death) on Windows computers.

###Activity LED
The green LED flashes intermittently during normal operation.  If there is no music playing and no access from the Rune UI, it stays off.

##Enabling I2S DACs and digital output boards

TBD

##USB keyboards

TBD

## WiFi dongles

TBD

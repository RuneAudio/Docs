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

1. Red Power LED and green ACT (Activity) LED turn on
2. Red LED stays on, green LED turns off
3. A rainbow splash screen appears on the monitor (if connected)
4. Rainbow screen turns off, text scrolls on the monitor, green SD card activity LED flashes rapidly
5. Linux login prompt appears on the monitor
6. Green LED continues to flash a few seconds while software is loading from the SD card
7. Rune UI can now be invoked in a browser

###Rainbow screen
The rainbow flash screen should only appear for about a second (good).  If the boot process halts with the rainbow screen on the monitor (bad), there may be a power supply issue, or a kernel software problem.

###USB power management
The Raspberry Pi has very good power management.  Power consumption increases incrementally over a few seconds as peripherals and USB devices are powered up in steps.  This is a good thing, because a power hungry or defective USB device can't kill the boot process completely.  If the red LED starts to slowly blink or dims during or after boot, there is a power supply issue. The default power allowance is 150mA (0.15A) per USB port (much less than a normal PC).

On a Pi B+ and Pi 2, this can be increased (using a parameter in the /boot/config.txt file) to about 300mA per USB port, or 1.2A total.  As a practical result, the Pi B+, Pi 2 and later models can better support WiFi dongles, wireless keyboards, mice, etc.

    # setting the max usb current to 1200mA
    max_usb_current=1

###Kernel panic
The text scrolling on the screen shows various parts of the OS being loaded.  If the boot process halts with text on the screen (other than at a login prompt), it may indicate a problem such as a corrupt SD card, a failed software update, power failure during SD card write, etc.  This is also known as Kernel Panic, the Linux equivalent of a BSOD (Blue Screen of Death) on Windows computers.

###Activity LED
The green LED indicates SD card access. It flashes intermittently during normal operation.  If there is no music playing and no access from the Rune UI, it stays off.

##Config.txt settings

The Raspberry Pi does not detect all possible hardware options on its own.  Some hardware settings are in /boot/config.txt, which can be edited on the same PC used to flash the SD card before the card is installed in a Pi. Starting with the Pi 2, the method used to identify and configure added hardware is called a Device Tree, and the hardware setting found in config.txt is called "device_tree_overlay".

The file /boot/config.txt can also be edited on the Pi, from a local console or a remote terminal interface (ssh on Linux, or PuTTY on Windows).  Example:

        # nano /boot/config.txt

For detailed information on other config.txt settings, such as setting HDMI monitor format, please read the official Raspberry Pi documentation:

>[Raspberry Pi config.txt](https://www.raspberrypi.org/documentation/configuration/config-txt.md)
>
>[Raspberry Pi Device Trees](https://www.raspberrypi.org/documentation/configuration/device-tree.md)

##Enabling I2S DACs and digital output boards

A section in /boot/config.txt already includes device tree settings for supported boards, each line preceded by the comment symbol "#". When an I2S dac or an S/PDIF output board is installed, the corresponding device tree overlay has to be enabled by removing the "#" symbol from the corresponding line.  Without this step, the OS kernel does not detect the board. 

Example, enabling a HiFiBerry DAC+:

        # Uncomment one of these lines to enable an audio interface
        #device_tree_overlay=hifiberry-dac
        device_tree_overlay=hifiberry-dacplus
        #device_tree_overlay=hifiberry-digi
        #device_tree_overlay=hifiberry-amp
        #device_tree_overlay=iqaudio-dac
        #device_tree_overlay=iqaudio-dacplus 

When a DAC or or digital audio output board is installed, the native analog output can be disabled by editing /etc/modules-load.d/raspberrypi.conf.  Example:

        # nano /etc/modules-load.d/raspberrypi.conf

Place a comment symbol "#" before "snd-bcm2835" in the second line:

        #snd-bcm2835
        
After making the above changes, the Pi should be rebooted with all hardware installed.

When the Pi boots with a DAC board and the correct device tree overlay setting, the output device can be selected in the Rune UI, from a drop down list in Menu > MPD Configuration > Audio Output.  The next steps are usually to configure the volume control and other MPD music options.

##Keyboard layout

If a USB wired or wireless keyboard is used with the Pi, some keyboard symbols and some letters may not be where expected.  In that case the default mapping of the keys has to be changed. RuneOS is based on Arch Linux and not on Debian, so the keymap setting is not located where expected on a Raspberry Pi.  From the Arch Wiki: 

>A persistent keymap can be set in /etc/vconsole.conf, which is read by systemd on start-up. The KEYMAP variable is used for specifying the keymap. If the variable is empty or not set, the us keymap is used as default value.

On initial use, it may look something like this:  `KEYMAP=de-latin1-nodeadkeys`, while the desired setting may be something like `KEYMAP=cz` or `fr`, `uk`, `us` etc.

The available keymaps can be listed using this command: `localectl list-keymaps`

##WiFi configuration

Wireless media streaming has several advantages, but setting up a WiFi connection in the Rune UI from a browser requires some extra steps.  

Initial configuration requires starting with default network settings and a wired network connection.  Wired ethernet can be unplugged after Wifi configuration is complete.

Typical WiFi configuration steps:

- connect both an ethernet cable AND a  USB WiFi dongle to the Pi
- connect power and wait for the Pi to boot
- using a PC connected to the same network, start the Rune UI
  (open a browser and go to `http://runeaudio`, or `http://runeaudio.local`)
- navigate to MENU > Network and select the wlan0 interface
- wait for all available WiFi networks to be found
- select the WiFi network from the list by its SSID
- enter WiFi settings including security, password, and select DHCP or static IP assignment
- save the WiFi profile (IMPORTANT!)
- wait for a WiFi connection to be established
- write down the wlan0 IP address for future use
- shutdown the Pi from the Rune UI via MENU > Turnoff
- disconnect the ethernet cable
- reboot the Pi by turning power off and back on

Tbd:

###Rune UI does not open with default ethernet settings

###No WiFi networks found

###Local WiFi network not found

###No WiFi connection

###Rune UI does not open after WiFi configuration

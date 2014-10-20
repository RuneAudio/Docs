# RuneAudio documentation

## Quick start guide

<div class="alert alert-warning">WORK IN PROGRESS &#8211; This guide is under construction and the information in it could be incomplete. We apologize for the inconvenience.</div>

[Want to help us?](http://www.runeaudio.com/forum/improve-the-docs-t332.html "RuneAudio Forum")

This guide assumes that you already own [a certified device](http://www.runeaudio.com/certified-devices/ "Certified devices") on which to run RuneAudio, and an SD card (at least 4GB) on which to write the image file.

### Download and extract

Download the latest RuneAudio image released for your device.

[[Go to the download page]](http://www.runeaudio.com/download/ "Download")

Once the download is completed, extract the contents of the .zip file with a compressed file manipulation utility (e.g.: [7-Zip](http://www.7-zip.org/download.html) on Windows, [Zipeg](http://www.zipeg.com/) on Mac, [Unzip](http://linux.about.com/od/commands/l/blcmdl1_unzip.htm) on Linux). You will now have an **.img** (raw disk image) file.

### Prepare the SD card

Write the extracted .img file to your SD card, following the instruction in one of the following guides (these are Raspberry Pi specific guides, but the SD write process is the same for all platforms):

*   [(Windows) HowTo](http://elinux.org/RPi_Easy_SD_Card_Setup#Using_the_Win32DiskImager_program)
*   [(Mac) HowTo](http://elinux.org/RPi_Easy_SD_Card_Setup#Run_an_App_.28Only_with_graphical_interface.29)
*   [(Linux) HowTo](http://elinux.org/RPi_Easy_SD_Card_Setup#Using_ImageWriter_.28graphical_interface.29)

When the write process has finished, safely unmount the SD card and plug it into your device.

**Make sure your SD card is not [write protected](http://kb.sandisk.com/app/answers/detail/a_id/1102/~/memory-card-is-write-protected-or-locked) before writing the image to it, and before plugging it into your device.**

### Prepare the device

1.  If you have a USB DAC plug it into a USB port, otherwise just plug in the analog jack;
2.  If you have a USB storage device, plug it into a USB port. If you intend to use a USB hard drive the use of an external power supply (if available), or at least a USB powered hub, is highly recommended;
3.  Plug in your ethernet connector;
4.  Plug the PSU to the device;
5.  Power the device on.

RuneAudio will now boot on your device for the first time, acquiring an IP address (with enabled DHCP on your LAN).

## Player setup

### The web interface &#8211; RuneUI

RuneAudio comes with its web interface, **[RuneUI](http://www.runeaudio.com/about/#runeui "RuneUI")**, which permits you to browse your music library, control the playback and to configure the player. It works on any device and virtually any platform. It is designed to be easy to use and intuitive.

### Accessing the RuneUI

You can connect to the RuneUI in several ways:

*   (Windows) open the following address in your browser: [http://runeaudio](http://runeaudio) or [http://runeaudio.](http://runeaudio.) (works if an [Avahi](http://en.wikipedia.org/wiki/Avahi_%28software%29 "Avahi")/[Bonjour](http://en.wikipedia.org/wiki/Bonjour_%28software%29 "Bonjour") client is installed)
 (OSX / Linux / Android) open the following address in your browser: [http://runeaudio.local](http://runeaudio.local)
*   If you cannot connect using the abovementioned addresses, look up the IP address of your device (check your routers DHCP list) and point your browser to it (e.g. [http://192.168.1.xxx](http://192.168.1.xxx/))
*   (Windows) you should find a new icon under _My Network Places_, called _RuneAudio_: double click it to open you the RuneUI in your default browser, or place a shortcut to the RuneUI on your desktop, which can then be double clicked to open the RuneUI.

### Database configuration

    MENU > Database

RuneAudio scans your digital music library and stores all information in an internal database.
Before it can do this, you need to tell it where your digital music is located.

Local USB storage drives are automatically detected. If you connect an USB drive and nothing happens, manually update the DB clicking on **UPDATE MPD DATABASE** button.

Network attached storages (NAS) can be added via Samba/NFS. To add a network source, click on the **ADD NEW MOUNT** button and fill in the form in the next screen. After saving the mount, it will be displayed in the configured network mounts list. A green check will appear on it if the source is successfully mounted.

## Advanced users

**Make sure you are completely confident and that you know what you are doing before fiddling about, as you could mess things up. Alteration of the configuration might result in you having to reimage your SD card and start again.**

Due to the integrated nature of the system (and the strong interaction between RuneUI and RuneOS), the manual editing of the system configuration files is not recommended, as they are periodically written by the RuneUI PHP worker. Please understand this behaviour before complaining about any malfunctions which may occur as a result of any manual modification.

If you have confidence in your skills, these are the root credentials for advanced users who want command line access are:

    user: root
    password: rune

## More help

Didn&#8217;t find here the information you were looking for here?
 Feel free to browse through the forum for answers, and to post in the forum to ask for help if you cannot find a solution:

[[Go to the forum]](http://www.runeaudio.com/forum/ "RuneAudio Forum")
Flashing the SD Card using Windows
==================================

Intro
-----

The SD card will be the home for your unit's Operating System. This installation will flash the RuneOS onto the card, along with formatting the card to a bootable state. This is different than copying the image onto the drive, but similar and almost as easy.

Materials
---------

To begin this procedure, you will require several things.
1. A Micro SD card of 4GB capacity or greater. 

> [INFO] Raspberry Pi and Raspberry Pi B require regular SD cards. Make sure they are not write protected before starting.

2. A card reader that can connect your SD card to your computer. USB types are cheap and work well.
3. The appropriate RuneAudio image file for your system. Find them on the [Downloads Page](http://www.runeaudio.com/download/).
4. An unzipped copy of [USB Image Tool](http://www.alexpage.de/usb-image-tool/download/). Alternately, an installed copy of [Win32DiskImager.](http://sourceforge.net/projects/win32diskimager/) 

Procedure using USB Image Tool
------------------------------

 - Insert your card into the card reader, (and the card reader into your USB port) and check which drive letter it has been assigned.

> [INFO] You are encouraged to remove all other USB devices at this time
> to avoid confusion during flashing.

 - Run USB Image Tool. (your computer may ask you to agree to run the program - click 'yes')
 - From the top left pull-down menu, choose 'Device' Mode.

 ![enter image description here](https://lh3.googleusercontent.com/-MFlqKBod9rM/VEX_SUPsXFI/AAAAAAAAAFQ/rgyxVuaB7z0/s0/usbit.gif "usbit.gif")
 
 - In the left panel choose your SD card. 

> [WARNING] <i class="fa fa-exclamation sx"></i> Double-check your card's drive letter! Choosing the wrong drive will likely result in data loss or even worse harm to your computer.

 - Choose the 'Favorites' Tab.
 - Click the 'Add' Button and browse to the RuneAudio image file. You may also choose to use the still-compressed file. Simply click the drop down menu near the bottom of the browse screen, choose 'Compressed (gzip) image files' or 'All Files' and choose which image you wish to flash.
 - In the 'Favorites' screen, click to highlight the image you wish to flash and then click 'Restore.' The write may take upwards of twenty minutes depending on the speed of your system.
 - When write has completed, close the image writer, and **take the time to properly eject your drive.** 

> [INFO] Pulling the drive hot often corrupts the SD card's data, requiring an annoying re-flash.

 - You are now ready to plug your (suddenly now incredibly more awesome) SD card into your device. Easy, right?
  
Procedure using Win32DiskWriter
-------------------------------

 - If not already done, decompress the RuneOS image file. (E.g. RuneAudio_rpi_0.2-beta.img.gz, or similar) with an unzip program like [7-Zip](http://sourceforge.net/projects/sevenzip/). A successful unzip will give you a copy of an image file with an '.img' file type. Unlike USB Image Writer, Win32DiskWriter requires an unzipped image to work from.
 - Insert your card into the card reader, (and the card reader into your USB port) and check which drive letter it has been assigned.

> [INFO] You are encouraged to remove all other USB devices at this time to avoid confusion during flashing.

 - Run Win32DiskWriter (your computer may ask you to agree to run the program - click 'yes')
 - Click the file icon and browse to your decompressed RuneOS image file.  

![enter image description here](https://lh5.googleusercontent.com/-GnGpJcdFTLc/VEsuN89OkOI/AAAAAAAAAGA/-n57YFMH7EU/s0/W32DI.png "W32DI.png")

 - Under 'device' choose your SD card from the drop-down menu. 

> [WARNING] **Double-check your card's drive letter.** Choosing the wrong drive will likely result in data loss or even worse harm to your computer.

 - Click 'Write'. The write may take upwards of twenty minutes depending on the speed of your system.
 - When write has completed, close the image writer, and **take the time to properly eject your drive.** 

> [INFO] Pulling the drive hot often corrupts the SD card's data, requiring an annoying re-flash.

 - You are now ready to plug your (suddenly now terrifyingly more awesome) SD card into your device. Easy, right?

***

Ready to get listening? Let's [plug stuff in!](http://www.runeaudio.com/documentation/quick-start/quick-start-guide/#prepare-the-device)

Having Issues? Head on over to [Troubleshooting](http://www.runeaudio.com/documentation/troubleshooting/common-troubleshooting/) for some help.


Notes
-----

Larger cards, once written, will only show ~2GB worth of space, taken up by the file system. This is simply because RuneAudio, operates on a file format not visible in Windows. See the [forum](http://www.runeaudio.com/forum/) for using extra space on large SD cards for storage. (*Better link, anyone?*)

When purchasing an SD card for your Raspberry Pi, consider a card with high read speeds, such as a Class 6 or even Class 10. Cards with read speeds of 40MB/s and better will make for a noticeably snappier and more responsive interface. 


Flashing the SD Card using Windows
==================================

Intro
-----
The SD card will be the home for your unit's Operating System. This installation will flash the RuneOS onto the card, along with formatting the card to a bootable state. This is different than copying the image onto the drive, but similar and almost as easy.

Materials
---------

To begin this procedure, you will require several things.
1. A Micro SD card of 4Gb capacity or greater. (Regular SD for Raspberry Pi and Raspberry Pi B)
2. A card reader that can connect your SD card to your computer. USB types are cheap and work well.
3. The appropriate RuneAudio image file for your system. Find them on the [Downloads Page](http://www.runeaudio.com/download/).
4. An installed copy of [USB Image Tool](http://www.alexpage.de/usb-image-tool/download/).
Procedure
---------

 - If not already done, decompress the RuneOS image file. (E.g. RuneAudio_rpi_0.2-beta.img.gz, or similar) with an unzip program like [7-Zip](http://sourceforge.net/projects/sevenzip/). A successful unzip will give you a copy of an image file with an '.img' file type.
 - Insert your card into the card reader, (and the card reader into your USB port) and check which drive letter it has been assigned.
 - Run USB Image Tool.
 - From the top left pull-down menu, choose 'Device' Mode.
 
 ![enter image description here](https://lh3.googleusercontent.com/-MFlqKBod9rM/VEX_SUPsXFI/AAAAAAAAAFQ/rgyxVuaB7z0/s0/usbit.gif "usbit.gif")
 
 - In the left panel choose your SD card. **Double-check your card's drive letter.** Choosing the wrong drive will likely result in data loss or even worse harm to your computer.
 - Choose the 'Favorites' Tab.
 - Click the 'Add' Button and browse to the RuneAudio image file.
 - Click 'Restore.' The write may take upwards of twenty minutes depending on the speed of your system.
 - When write has completed, close the image writer, and **take the time to properly eject your drive.** Pulling the drive hot often corrupts the SD card's data, requiring an annoying re-flash.
 - You are now ready to plug your (suddenly now incredibly more awesome) SD card into your device. 
	
	Easy, right?
  
   

Common Issues
--------------

 - Corrupted OS. Make certain you 'eject' your SD card properly. If you corrupt your SD card, just reflash the image file over the top of the old one. USB Image Tool will automatically take care of the erasing/formatting.
 - Wrong OS. Make certain you've chosen the correct OS for your system. As above, the old OS can be overwritten by re-flashing the new OS over the top.
 - Poor card connection. Some devices (notably the Raspberry Pi and Pi B) have touchy card slots. Make certain the card is bottomed out in the socket.
 - Weirdly low card space. Totally normal. Once flashed, much of the space on the card is no longer visible in windows, as RuneAudio operates on a File Format that is not visible in Windows. The space still exists, and much (how much?) is used by the operating system. See forums (or advanced help?) for using large SD cards for storage. 


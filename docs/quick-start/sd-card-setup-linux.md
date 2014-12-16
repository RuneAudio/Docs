# Flashing the SD Card using Linux

> [INFO] This part of the guide assumes that you already have [downloaded and extracted](../quick-start/quick-start-guide.md#download-and-extract) the image file

Flashing the SD Card using Linux
==================================

Intro
-----

The SD card will be the home for your unit's Operating System. This installation will flash the RuneOS onto the card, along with formatting the card to a bootable state. This is different than copying the image onto the drive, but similar and almost as easy.

Materials
---------

To begin this procedure, you will require several things.
1. A Micro SD card of 4GB capacity or greater. 

> [INFO] Raspberry Pi and Raspberry Pi B require regular SD cards. Make sure they are not write protected before starting.

2. A card reader that can connect your SD card to your computer.
3. The appropriate RuneAudio image file for your system. Find them on the [Downloads Page](http://www.runeaudio.com/download/).

Procedure using ImageWriter (graphical interface)
-------------------------------

> [INFO] You are encouraged to remove all other USB devices at this time to avoid confusion during flashing.

 - If not already done, decompress the RuneOS image file. (E.g. *RuneAudio_rpi_0.2-beta.img.gz*, or similar). A successful unzip will give you a copy of an image file with an *.img* file type.
 - Install the ImageWriter tool (from *Ubuntu Software Center*, *apt-get*, etc.)
 - Insert your card into the card reader, and the card reader into your USB port.
 - Launch the ImageWriter tool (it needs your administrative password) and select the image file.
 - Select the target device to write the image to (your device will be something like */dev/mmcblk0* or */dev/sdc*).

> [WARNING] **Double-check your card's name!** Choosing the wrong drive will likely result in data loss or even worse harm to your computer.

> [INFO] If you're not sure then check it through *df -h* command (see below) or through GParted

 - Click the "Write to device" button and wait for the process to finish and then insert the SD card in the Raspberry Pi
 - When write has completed, close the program, and **take the time to properly eject your drive.** 

> [INFO] Pulling the drive hot often corrupts the SD card's data, requiring an annoying re-flash.

 - You are now ready to plug your (suddenly now incredibly more awesome) SD card into your device. Easy, right?
  
Procedure using the command line
-------------------------------

> [INFO] You are encouraged to remove all other USB devices at this time to avoid confusion during flashing.

 - If not already done, decompress the RuneOS image file. (E.g. *RuneAudio_rpi_0.2-beta.img.gz*, or similar). A successful unzip will give you a copy of an image file with an *.img* file type.
 - Run *df -h* command to see what devices are currently mounted.
 - Insert your card into the card reader, and the card reader into your USB port. Make sure that it's mounted; the easiest way to do that is to open it with your file manager.
 - Run *df -h* again. The device that wasn't there last time is your SD card. The left column gives the device name of your SD card. It will be listed as something like */dev/mmcblk0p1* or */dev/sdd1*. The last part (*p1* or *1* respectively) is the partition number, but you want to write to the whole SD card, not just one partition, so you need to remove that part from the name (getting for example */dev/mmcblk0* or */dev/sdd*) as the device for the whole SD card.

> [INFO] You can also check it through GParted

> [WARNING] **Double-check your card's name!** Choosing the wrong drive will likely result in data loss or even worse harm to your computer.

 - Unmount the card with *umount /dev/[sd_name]*, where */dev/[sd_name]* is the name you got from the previous step.
 - Write the image to the card with this command *sudo dcfldd bs=1M if=[img_file_path] of=/dev/[sd_name]*.

> [INFO] Make sure you replace the input file **if=** argument with the path to your *.img* file, and the */dev/sdd* in the output file **of=** argument with the right device name (**this is very important:** you will lose all data on the hard drive on your computer if you get the wrong device name). Make sure the device name is the name of the whole SD card as described above, not just a partition of it (for example, sdd, not sdds1 or sddp1, or mmcblk0 not mmcblk0p1)

 - When write has completed, run command *sudo sync* (this will ensure the write cache is flushed and that it is safe to unmount your SD card) and unmount the card (either through the file manager or with *umount /dev/[sd_name]*).

> [INFO] Pulling the drive hot often corrupts the SD card's data, requiring an annoying re-flash.

 - You are now ready to plug your (suddenly now terrifyingly more awesome) SD card into your device. Easy, right?

***

Ready to get listening? Let's [plug stuff in!](http://www.runeaudio.com/documentation/quick-start/quick-start-guide/#prepare-the-device)

Having Issues? Head on over to [Troubleshooting](http://www.runeaudio.com/documentation/troubleshooting/common-troubleshooting/) for some help.


Notes
-----

When purchasing an SD card for your Raspberry Pi, consider a card with high read speeds, such as a Class 6 or even Class 10. Cards with read speeds of 40MB/s and better will make for a noticeably snappier and more responsive interface. 

# Flashing the SD Card using Windows

> [INFO] This part of the guide assumes that you already done the first part of the [Quick start guide](quick-start-guide.md).

## Intro

The SD card will be the home for your unit's Operating System. This installation will flash the RuneOS onto the card, along with formatting the card to a bootable state. This is different than copying the image onto the drive, but similar and almost as easy.

> [INFO] You are encouraged to remove all other USB devices at this time to avoid confusion during flashing.

## Procedure using USB Image Tool

 - Download and install the latest version of [USB Image Tool](http://www.alexpage.de/usb-image-tool/download/).
 - Insert your card into the card reader, the card reader into your USB port, and check which drive letter it has been assigned.
 - Run USB Image Tool (your computer may ask you to agree to run the program - click *Yes*).
 - From the top left pull-down menu, choose *Device* mode.

 ![USB Image Tool](https://lh3.googleusercontent.com/-MFlqKBod9rM/VEX_SUPsXFI/AAAAAAAAAFQ/rgyxVuaB7z0/s0/usbit.gif "usbit.gif")
 
 - In the left panel choose your SD card. 

> [WARNING] **Double-check your card's drive letter!** Choosing the wrong drive will likely result in data loss or even worse harm to your computer.

 - Choose the *Favorites* tab.
 - Click the *Add* button and browse to the RuneAudio image file. You may also choose to use the still-compressed file. Simply click the drop down menu near the bottom of the browse screen, choose *Compressed (gzip) image files* or *All Files* and choose which image you wish to flash.
 - In the *Favorites* screen, click to highlight the image you wish to flash and then click *Restore*. The write may take a while, so don't panic.
 - When write has completed, close the program, and **properly eject your drive.** 
 - You are now ready to plug your SD card into your device. Easy, right?
  
## Procedure using Win32DiskWriter

 - Download and install the latest version of [Win32DiskImager](http://sourceforge.net/projects/win32diskimager/).
 - Insert your card into the card reader, the card reader into your USB port, and check which drive letter it has been assigned.
 - Run Win32DiskWriter (your computer may ask you to agree to run the program - click *Yes*).
 - Click the file icon and browse to your RuneOS image file.  

 ![Win32DiskWriter](https://lh5.googleusercontent.com/-GnGpJcdFTLc/VEsuN89OkOI/AAAAAAAAAGA/-n57YFMH7EU/s0/W32DI.png "W32DI.png")

 - Under *Device* choose your SD card from the drop-down menu. 

> [WARNING] **Double-check your card's drive letter!** Choosing the wrong drive will likely result in data loss or even worse harm to your computer.

 - Click *Write*. The write may take a while, so don't panic.
 - When write has completed, close the program, and **properly eject your drive.** 
 - You are now ready to plug your SD card into your device. Easy, right

***

Ready to get listening? Let's [plug stuff in!](http://www.runeaudio.com/documentation/quick-start/quick-start-guide/#prepare-the-device)

Having Issues? Head on over to [Troubleshooting](http://www.runeaudio.com/documentation/troubleshooting/common-troubleshooting/) for some help.

## Notes

Larger cards, once written, will only show ~2GB worth of space, taken up by the file system. This is simply because RuneAudio, operates on a file format not visible in Windows.

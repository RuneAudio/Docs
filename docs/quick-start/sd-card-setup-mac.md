# Flashing the SD Card using Mac

> [INFO] This part of the guide assumes that you have already [downloaded and extracted](../quick-start/quick-start-guide.md#download-and-extract) the image file

First of all, make sure your SD card is inserted in one of the slots of your Mac (in an USB card reader or directly in the integrated SD card reader slot, if your device has one).

Next step is to launch a *terminal* window on your Mac and enter the following command:

`diskutil list`

which will list all the disks that are attached to your MAC.  
The resulting output will look something like this:

    /dev/disk0
       #:                       TYPE NAME                    SIZE       IDENTIFIER
       0:      GUID_partition_scheme                        *500.3 GB   disk0
       1:                        EFI EFI                     209.7 MB   disk0s1
       2:          Apple_CoreStorage                         499.4 GB   disk0s2
       3:                 Apple_Boot Boot OS X               134.2 MB   disk0s3
    /dev/disk1
       #:                       TYPE NAME                    SIZE       IDENTIFIER
       0:                  Apple_HFS Macintosh HD           *499.1 GB   disk1
    /dev/disk2
       #:                       TYPE NAME                    SIZE       IDENTIFIER
       0:     FDisk_partition_scheme                        *7.9 GB     disk2
       1:                 DOS_FAT_32 CANAKIT                 7.9 GB     disk2s1

Find the unit name that corresponds to your SD card (looking at the sizes of the drives will help you identify the right one). 
In the previous example, it's `/dev/disk2`.

Before proceeding with the flash of the SD card, you should unmount it first. To do that, launch the **Disk Utility** tool and unmount the SD Card.
Do NOT eject it, simply unmount it with a right-click.  
Alternatively, you can also unmount the disk manually, by typing the following in the terminal window:

`diskutil unmount /dev/disk2`

> [WARNING] **Double-check your card's drive letter!** Choosing the wrong drive will likely result in data loss or even worse harm to your computer.

To write the image to the SD card, the command syntax is:

`dd if=[source] of=[destination]`

so a real example of the command is:

`dd if=/Users/antonypa/Desktop/RuneAudio_rpi_0.3-beta_20141029_2GB.img of=/dev/disk2`

if you get the following message (very likely):

`dd: /dev/disk2: Permission denied`

just add *sudo* in front of the command, which will prompt for your password.
 
`sudo dd if=/Users/antonypa/Desktop/RuneAudio_rpi_0.3-beta_20141029_2GB.img of=/dev/disk2`

After launching the command you should wait for the flashing process to complete. It can take several minutes, and you'll know that it has completed when the prompt comes back with no errors.

***

Ready to get listening? Let's [plug stuff in!](http://www.runeaudio.com/documentation/quick-start/quick-start-guide/#prepare-the-device)

Having Issues? Head on over to [Troubleshooting](http://www.runeaudio.com/documentation/troubleshooting/common-troubleshooting/) for some help.

*This guide has been greatly (if not almost entirely) inspired by the "Installing OpenELEC Help" guide.*
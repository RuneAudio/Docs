# Flashing the SD Card using Linux

> [INFO] This part of the guide assumes that you already followed the first part of the [Quick start guide](quick-start-guide.md).

## Intro

The SD card will be the home for your unit's Operating System. This installation will flash the RuneOS onto the card, along with formatting the card to a bootable state. This is different than copying the image onto the drive, but similar and almost as easy.

> [INFO] We recommend removing all other USB devices at this time to avoid confusion during flashing.

## Procedure using ImageWriter (graphical interface)

 - Install the ImageWriter tool (via *Ubuntu Software Center*, via command line with `apt-get ...`, etc.)
 - Insert your card into the card reader, and the card reader into your USB port.
 - Launch the ImageWriter tool (it needs your administrative password) and select the image file.
 - Select the target device to write the image to (your device will be something like `/dev/mmcblk0` or `/dev/sdc`). If you're not sure what to choose, then check it through `df -h` command (see below) or GParted.

> [WARNING] **Double-check your card's name!** Choosing the wrong drive will likely result in data loss or even worse harm to your computer.

 - Click the *Write to device* button. The write may take a while, so don't panic.
 - When write has completed, close the program, and **properly eject your drive.** 
 - You are now ready to plug your SD card into your device. Easy, right?
  
## Procedure using the command line

 - Run `df -h` command to see what devices are currently mounted.
 - Insert your card into the card reader, and the card reader into your USB port.
 - Make sure that the device is mounted; the easiest way to do that is to open it with your file manager.
 - Run `df -h` again. The device that wasn't there last time is your SD card. The left column gives the device name of your SD card. It will be listed as something like `/dev/mmcblk0p1` or `/dev/sdd1`. The last part (`p1` or `1` respectively) is the partition number, but you want to write to the whole SD card, not just one partition, so you need to remove that part from the name (getting for example `/dev/mmcblk0` or `/dev/sdd`) as the device for the whole SD card.
 - Unmount the card with `umount /dev/[sd_name]` command, where `[sd_name]` is the name you got from the previous step.

> [INFO] You can also check device name through [GParted](http://gparted.org/).

 - Write the image to the card with command `sudo dcfldd bs=1M if=[img_file_path] of=/dev/[sd_name]`, replacing `if=` argument with the path to your **.img** file, and the `of=` argument with the right device name. The write may take a while, so don't panic.

> [WARNING] **Double-check your card's name!** Choosing the wrong drive will likely result in data loss or even worse harm to your computer.

 - When write has completed, run command `sudo sync` (this will ensure the write cache is flushed and that it is safe to unmount your SD card) and **properly eject your drive.** 
 - You are now ready to plug your SD card into your device. Easy, right?

***

Ready to get listening? Let's [plug stuff in!](http://www.runeaudio.com/documentation/quick-start/quick-start-guide/#prepare-the-device)

Having Issues? Head on over to [Troubleshooting](http://www.runeaudio.com/documentation/troubleshooting/common-troubleshooting/) for some help.

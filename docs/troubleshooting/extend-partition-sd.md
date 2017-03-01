# Extend a partition

RuneAudio is commonly distributed in system images which will fit on 2GB SD cards. The default partition sizes are limited to that total amount, so if you are using a bigger SD card you will probably want to take advantage of all the space available.  

## Make use of unused space on a SD card

A command which may be of interest to make use of unused space on the SD card is **resize2fs**. 
This resizes the filesystem, and can be used while the filesystem is online (i.e. no need to unmount it).

First you have to use **fdisk** to resize the partition to fill the whole SD card. You can do this by doing:
    
    fdisk /dev/mmcblk0
    
 1. Press "**p**" to show the current partitions and note down the details of the main one that RuneOS is on.
 2. Delete it, pressing "**d**" and choosing the relevant partition number.
 3. Press "**n**" to make a new partition, and "**p**" to select a primary partition. Enter the same start block that you wrote down above, and allow it to use the default end block (the last block available on the device).
 4. Press "**t**" and enter the value "83" to mark it as a Linux partition. 
 5. Press "**w**" to write changes and exit. You may have to reboot after this for changes to be registered. This has resized the partition, but not yet the filesystem.

or use **sfdisk**  

    root=$( mount | sed -n '/on \/ type/p' | awk '{print $1}' ); echo ',+' | sfdisk -f -N ${root:-1} ${root:0:12} --no-reread

Next, use the **resize2fs** command in this way:

    resize2fs /dev/mmcblk0p0

(or `/dev/mmcblk0p1` if the main RuneOS partition was `mmcblk0p1`).  
This will resize the filesystem to fill the whole partition, and you will have a lot more space available for stuff.

# Flashing the SD Card using Mac

> [INFO] This part of the guide assumes that you already have [downloaded and extracted](../quick-start/quick-start-guide.md#download-and-extract) the image file

Make sure your SD card is inserted in on of the slot of your MAC (through USB or directly in the SD slot if you have one)
Then launch a *terminal* window on your Mac and enter the following command:
<pre>diskutil list</pre>
this command will list all the disks that are attached to your MAC. The outpu will look something like this:
<pre>
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
   </pre>
<p>Find the one that corresponds to your SD card. In the previous example, it's /dev/disk2. Hint: you can look at the sizes.. 
<p>Now we cannot flash the card without unmounting it first. To do tha launch the *Disk Utility* tool and unmount the SD Card. Do NOT eject it, simply unmount it with a right-click. You can also unmount the disk manually on the prompt by typing:
<pre>diskutil unmount /dev/disk2</pre>
<p>Now we will image the SD but be VERY CAREFUL, the *dd* command can scratch your main disk entirely if you put the wrong number, so check twice!!
<p><pre>dd if=/Users/antonypa/Desktop/RuneAudio_rpi_0.3-beta_20141029_2GB.img of=/dev/disk2</pre>
<p>if you get the following message (very likely)
<pre>dd: /dev/disk2: Permission denied</pre>
<p>just add *sudo* in front of the command which will prompt for your machine's password. 
<p><pre>sudo dd if=/Users/antonypa/Desktop/RuneAudio_rpi_0.3-beta_20141029_2GB.img of=/dev/disk2</pre>
<p>then wait.. nothing will happen for a while. Be patient.. The flashing IS happening.
<p>patience..
<p>patience..
<p>go get a coffee or something. It can take several minutes.
<p>When the prompt comes back it should be done.
<p>It is possible that you get the following error:
<p>
<p>This help has been greatly (f not almot entirely) inspired by the Installing OpenElec Help guide.

*Take inspiration from [this resource](http://elinux.org/RPi_Easy_SD_Card_Setup#Flashing_the_SD_card_using_Mac_OSX) for the contents.*

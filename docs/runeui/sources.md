# Sources

#### Menu > Sources

The Local Sources screen allows you to configure the locally connected data sources containing your audio files. Both Network Attached Storage (NAS) and USB storage can be configured on this screen.

The "Rebuild MPD Library" button refreshes the content of your MPD music library by reading again the contents of your Network and USB Mounts.

## Network Mounts

This section lists all Network Attached Storage (NAS) configured for your device.

Clicking "Add new mount" allows you to configure a new Network Mount. When adding a new mount, complete the following fields:

#### Source name

This is the name you want to give to this source. It will appear in your Library with this name.

#### File-share protocol

The following options are available for the type of file-share to which you are connecting:

- SMB/CIFS: select this for connecting to a Windows file share
- SMB/CIFS (OS X): select this for connecting to an OS X file share
- NFS: select this option for connecting to a unix file share

#### IP address

Enter the IP Address (or name) of the NAS device to which you wish to connect.

#### Remote directory

Specify the directory name of the shared folder on the NAS where your music files are stored. (NOTE: the directory name is case sensitive)

#### Guest access

Guest access allows you to connect to a shared folder without a username / password. If your NAS requires you to use login credentials, disable guest access (set it to "Off") and enter the Username and Password.


#### Advanced Options

This setting toggels the visibility of the advanced mount options.

## Advanced Options

When enabled, additional settings are available for configuring your connection to your NAS device.

#### Charset

Change this settings if you experience problems with character encoding.

#### Rsize

Change this settings if you experience problems with music playback (e.g. pops or clips).

#### Wsize

Change this settings if you experience problems with music playback (e.g. pops or clips).

#### Mount flags

You can configure advanced mount flags here. However, we suggest you don't use this field if you don't know what you are doing.


## USB


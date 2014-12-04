# Settings

> [MENU] Menu > Settings

The Settings screen provides a means of managing the settings for your Rune device.

## Environment

####  Check system status

The "show status" button allows you to see information regarding the system and its status, such as the actively running kernel, system time, uptime, hardware platform and the player ID.

#### Player hostname

This allows you to set the name of your device, which is how you will reach the RuneUI running on it. For example, naming your device "MyDevice" (without the quotes) would allow you to control it at the following URL: http://MyDevice

#### NTP server
This allows you to set a reference time sync server (NTP server). The default, *pool.ntp.org*, is a publicly maintained time server and should be adequate.

#### Timezone
This allows you to set the system time zone.


## RuneOS kernel settings

#### Linux Kernel

You can choose from a list of available Linux Kernels to run. You need to reboot the system after chaning this selection in order to run the newly chosen kernel.

#### I²S kernel modules

You can enable I²S output by selecting one of the available items in the list. Doing so loads a pre-set collection of modules, specific for each hardware. Once set, the output interface will appear in the MPD (mpd.md) configuration menu. These modules will also auto-load on future reboots.

#### Sound Signature (optimization profiles)
Each of the profiles includes a set of performance tweaks that act on specific system kernel parameters. They *are not* enabling Digital Signal Processing (DSP) nor any other sound effect - the output remains untouched (bit perfect). By applying settings that act on kernel latency parameters (and probably on the amount of overall jitter), we have found that each of these profiles introduces an audible impact on the overall sound quality.

The actual sonic results vary depending on the other equipment in use in your system, as well as teh acoustic properties of the room itself. So, we invite you to experiment and ultimately choose a profile according to your personal taste. (If you can't hear any differences... don't worry, they are subtle. You are safe to stick to the default settings.)

## Features management
You can Enable/Disable optional modules to best suit your needs. Disabling unused features will free system resources and might improve the overall performance. Enabling them allows you to use them. The choice is yours.

#### AirPlay

The AirPlay setting allows you to toggle the capability of receiving wireless streaming of audio via the AirPlay protocol.

- When enabled, you must configure the AirPlay name for this device.

#### Spotify

The Spotify setting allows you to enable the built-in Spotify client [EXPERIMENTAL]. You must have a Spotify PREMIUM account to use this feature.

- When enabled, you must provide your Spotify Username and Password.

#### UPnP / DLNA

The UPnP / DLNA setting allows you to toggle the capability of receiving wireless streaming of audio via the UPnP / DLNA protocol.

- When enabled, you must configure the UPnP / DLNA name for this device.


#### USB Automount

The USB Automount setting allows you to toggle the feature to automatically detect and mount connected USB Drives.

#### Last.fm

The Last.fm setting allows you to send information to Last.fm about the music you are listening to (requires a Last.fm account).

- When enabled, you must provide your Last.fm Username and Password.

## Compatibility fixes
Some receivers and DACs use CMedia components that suffer from audible glitches (noise, crackling) when changing between tracks with different sample rates and/or bit depth.

This setting allows you to toggle the application of a fix for the *CM6631 receiver* related issues. It is not recommended to use this fix if you do not experience issues with this setting turned off.

## Backup / Restore configuration

The Backup feature makes a copy of your current settings. The restore feature allows you to easily apply those saved setting by either transferring them between multiple RuneAudio installations, or applying them to a new/upgrade installation.

NOTE: restore feature will come in 0.4 release.


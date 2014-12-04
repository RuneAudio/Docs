# MPD

> [MENU] Menu > MPD

The MPD screen is the main configuration page for the Music Player Daemon (MPD), the system responsible for audio playback. A link ("reset to default") is provided at the top of this screen to reset everything to the default settings.

## Audio output

The first option is for selecting the Audio Output Interface. The choices here will change depending upon the various "sound cards" you have available to your system. Typically, this list will contain all of the output devices native to your hardware, as well as any USB DACs you have connected. In some cases, namely when you configure an I2S DAC Driver on the Settings screen, an I2S Output will be available for selection.

## Volume control

There are 3 options available for volume control.

- The "disabled" option disables the volume control on the Playback tab, meaning you will need to use a pre-amp or other external volume control. This often provides the best sonic performance.
- The "enabled – software" option enables an internal software mixer that allows you to adjust the playback volume on the Playback tab. Doing so alters the bits being sent to your DAC (or the internal DAC chip if you have selected an internal sound card for playback). Altering the bits means the music you are listening to is no longer "bit perfect." Software algorithms for volume control use dithering, a way of "guessing" at the data which can be quite accurate. What this means is that software volume control can sound quite good, especially compared to a poorly implemented analogue volume control.
- The "enabled – hardware" allows for changing the volume through the actual soundcard's driver, if this feature is implemented by your chosen Audio Output Interface.

## General music daemon options

#### Port

The default port for MPD is 6600. If you want to use a third-party device or software to control playback, you will need to connect to MPD on your Rune device using this port.

#### Daemon user : group

You can choose which user account on your device you would like to run MPD as using the Daemon user : group selection.

#### Log level

Log level allows you to control how much data is logged while running MPD. This can be useful for debugging and tracking down playback issues. This setting controls the type of information which is logged. Available setting arguments are "disabled", "default", "secure" or "verbose". The "verbose" setting argument is recommended for troubleshooting, though can quickly stretch available resources on limited hardware storage.

#### State file

State file specifies if a state file is used. If the state file is active, the state of MPD will be saved when MPD is terminated by a TERM signal or by the "kill" command. When MPD is restarted, it will read the state file and restore the state of MPD (including the playlist).

#### FFmpeg decoder plugin

The FFmpeg decoder setting should be set to enabled if you require AAC / ALAC support. Doing so may slow down the performance of an MPD database refresh.

#### FFmpeg decoder plugin

Gapless MP3 playback allows you to enable gapless mode while playing MP3s. However, if you have problems with your MP3s ending abruptly, it is recommended that you set this argument to "disabled" to attempt to fix the problem. [NOTE: If this solves the problem, it is highly recommended to fix the MP3 files with vbrfix (available as vbrfix in the debian archive), at which point gapless MP3 playback can be enabled.]

#### FFmpeg decoder plugin

DSD Support enables and disables support for playing DSD Audio.

#### Volume normalization

Volume normalization is a feature that instructs MPD to attempt to play back all audio files at a consistent volume level. This is great for parties or other situations where your music serves as background. With it off, some tracks may play substantially louder than others. NOTE: Enabling this feature means your audio will no longer be bit perfect.

#### Audio buffer size

Audio buffer size manages the size of the playback buffer. The default is 2048, large enough for nearly 12 seconds of CD-quality audio. Lower values can produce sonic benefits, but can also introduce skips and pops.

#### Buffer before play

Buffer before play specifies how much of the audio buffer should be filled before playing a song. Try increasing this setting if you hear skipping when manually changing songs. The default is 10%, a little over 1 second of CD-quality audio with the default buffer size.

#### Auto update

Auto update controls MPD automatically updating the music database when files in the music directory are changed.

After making changes on this screen, press "Save and apply" to save the changes.


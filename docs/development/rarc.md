#RARC - RuneAudio Remote Control

![RuneAudio for Android](http://www.runeaudio.com/media/docs/runeaudio-android-mockup.png "runeaudio-android-mockup.png")

[![Get the app on Google Play](http://www.runeaudio.com/media/docs/google-play-badge.png "google-play-badge.png")](https://play.google.com/store/apps/details?id=org.xbmc.kore)

**RARC - RuneAudio Remote Control** makes even easier to control one or more RuneAudio music players from your Android™ device.

## Main features

- **Player discovery** - scan the local network for connected RuneAudio compatible players
- **Fullscreen UI** - RuneUI is displayed in true fullscreen, with no additional browser bars
- **Volume control** - adjust the volume with the physical buttons on your phone

## Support

To get support or to discuss about the app development, join us the dedicated thread on the forum.   
[[RuneAudio Remote Control - RuneAudio Forum]](http://www.runeaudio.com/forum/)

## FAQ

###RuneUI only shows a spinning wheel   
If the app finds your player and connects to it but RuneUI only shows a spinning wheel, it means that your Android device is not compatible. RuneUI uses websockets to communicate with the browser in real time, and websockets are not fully supported in the default browser on Android versions older than 4.4 KitKat.

###The app cannot find my player
Check if your player is up to date with the [latest version of RuneAudio](../troubleshooting/updating.md).   
If the file `/etc/avahi/services/runeaudio.service` doesn't exist or is empty, create it with the following content:   
```
<?xml version="1.0" standalone='no'?>
<!DOCTYPE service-group SYSTEM "avahi-service.dtd">
<service-group>
  <name replace-wildcards="yes">RuneAudio [device_name] [xx:xx:xx:xx:xx:xx]</name>
  <service>
    <type>_http._tcp</type>
    <port>80</port>
  </service>
</service-group>
```
Replace the following values with the desired ones:

- `device_name` is the name of the device you want to be shown in the UI (i.e.: Raspberry Pi 2);
- `xx:xx:xx:xx:xx:xx` is the MAC address of the network adapter (LAN or WiFi) the player is using to connect to the local network (check it with the `ifconfig` command).

## Credits

- **[Elliot Nathanson](https://www.linkedin.com/in/elliot-nathanson-7815151)** - main developer
- **[Andrea Coiutti](http://www.runeaudio.com/team/)** - design
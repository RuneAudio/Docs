#RuneAudio Remote Control

![RuneAudio for Android](http://www.runeaudio.com/media/docs/runeaudio-android-mockup.png "runeaudio-android-mockup.png")

[![Get the app on Google Play](http://www.runeaudio.com/media/docs/google-play-badge.png "google-play-badge.png")](https://play.google.com/store/apps/details?id=org.xbmc.kore)

**RuneAudio Remote Control** makes even easier to control one or more RuneAudio music players from your Android™ device.

## Main features

- **Player discovery** - scan the local network for connected RuneAudio compatible players
- **Fullscreen UI** - RuneUI is displayed in true fullscreen, with no additional browser bars
- **Volume control** - adjust the volume with the physical buttons on your phone

## FAQ

### How does it work?
[RuneUI](../runeui/runeui.md) is a web interface and is normally accessed by pointing a web browser to [http://runeaudio](http://runeaudio) or [http://runeaudio.local](http://runeaudio.local) or the IP address of the player.
RuneAudio Remote Control skips this step: it scans the local network and automatically shows all the connected RuneAudio players, allowing you to control them from the same place.
It also displays the RuneUI in a true full screen, with no browsers bars and weird scroll behaviours.

The app uses the [avahi protocol](https://en.wikipedia.org/wiki/Avahi_%28software%29) to scan the local network. 
It detects the connected RuneAudio players which expose the avahi service and lists them, showing also their IP and MAC addresses.

###The app does not find my player
The player could not expose the required service properly. Check the [compatibility chapter](#compatibility) below.

###RuneUI only shows a spinning wheel   
If the app finds your player and connects to it but RuneUI only shows a spinning wheel, your Android device could not be compatible. Check the [compatibility chapter](#compatibility) below.

## Compatibility

### Android version

RuneAudio Remote Control uses the **default stock browser** to embed the webview in full screen. 
Unfortunatly, **websockets** are not fully supported in the default browser on most Android devices before 4.4 KitKat version. 
Since RuneUI uses websockets to communicate with the browser in real time, it won't work properly on older device, showing a spinning wheel (unable to connect).

### RuneAudio version

Check if your player is up to date with the [latest nightly build of RuneAudio](../troubleshooting/updating.md#nightly-builds).   
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


## Support

To get support or to discuss about the app development, join us the dedicated thread on the forum.   
[[RuneAudio Remote Control - RuneAudio Forum]](http://www.runeaudio.com/forum/)

## Credits

- **[Elliot Nathanson](https://www.linkedin.com/in/elliot-nathanson-7815151)** - main developer
- **[Andrea Coiutti](http://www.runeaudio.com/team/)** - design
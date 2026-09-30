# TV Apps

Scholarium apps for masjid TV displays. **Download them from the
[latest release](https://github.com/alimul-khan/TV-apps/releases/latest).**

| App | Install on | File |
| --- | --- | --- |
| **Prayer Display** | Android TV | `PrayerDisplay-TV-<version>.apk` |
| **Display Controller** | Android phone | `DisplayController-Phone-<version>.apk` |

Both need Android 6.0 or newer. The phone and the TV must be on the same Wi-Fi.

## Prayer Display (TV)

Shows the prayer times full screen: clock, Gregorian and Hijri date, sunrise and
sunset, Azan and Iqamah times, Jumu'ah, rotating notices (images, images with text,
moving messages) and a scrolling message. It works in landscape and on a TV
mounted on its side (portrait). It replaces the TV's home screen, so it starts
whenever the TV turns on.

To install, enable developer options and network debugging on the TV, connect with
[adb](https://developer.android.com/tools/adb), then:

```bash
adb install PrayerDisplay-TV-v1.0.apk
```

```bash
adb shell cmd package set-home-activity com.scholarium.prayerdisplay/.KioskActivity
```

```bash
adb shell pm disable-user --user 0 com.google.android.tvlauncher
```

On Google TV, the last command uses `com.google.android.apps.tv.launcherx`. Then
restart the TV.

Hold the remote's **Back** button on the display to see its address and to open the
TV's Wi-Fi and Date & time settings.

To undo, turn the TV's own launcher back on, then uninstall:

```bash
adb shell pm enable com.google.android.tvlauncher
```

```bash
adb uninstall com.scholarium.prayerdisplay
```

## Display Controller (phone)

Open `DisplayController-Phone-v1.0.apk` on the phone and allow installing from the
app that opened it when Android asks. The app finds the display on the Wi-Fi, or you
can type the address shown on the TV. From it you set the location, prayer settings,
iqamah delays, Jumu'ah times, notices, theme and screen orientation.

Anyone on the same Wi-Fi who has the app can change the display's settings.

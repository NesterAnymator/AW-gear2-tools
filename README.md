> I'm new here, so please don't be mean to me.)

# Gear 2 Manager [ROOT]
This application tries to expand the functionality of Android Wear down to standard Android *(in this case, phone)* using system resources such as AppOps, PM, Settings, third-party tweaks, etc.

Initially, it was intended and tested to be used on Samsung Gear 2 Neo watches with custom firmware Android Wear 1.4.0.2633150 (based on Android 6.0.1, build number MEC23U), so some points are explained specifically for them, in the future I will move them.
 
## Application features
• Configure application permissions via AppOps (in the future I will add via PM)

• Delete applications

• Stop applications

• Change screen density

• Change screen resolution 

• Change screen brightness

• Clear RAM (may not work)

• Reboot the device into different boot modes (Recovery, Download (for Odin, Samsung Kies) or kill Android server)
• Changing the name of the watch in Bluetooth (receiving the name is broken, I will fix it in the future)

• Select the keyboard layout (or rather, call the hidden activity from the standard settings)

• Install Root (drop the SuperSU archive into /sdcard)

• Tweaks (for now these are: Sound when receiving a notification and Pop-up button to hide the keyboard)


## App Installation

#### 1. Download the latest version of the app from the [Releases](https://github.com/NesterAnymator/AW-gear2-tools/releases) tab

#### 2. **(For Windows PC)** Download [Minimal ADB & FastBoot](https://androidfilehost.com/?fid=746010030569952951) and run the desktop shortcut (or open command prompt in the program's directory)

**(For Android phone)** Download [Termux](https://f-droid.org/ru/packages/com.termux) from F-Droid, install it and run the command:
```bash
   pkg update && pkg upgrade && pkg install android-tools
```
#### 3. [Connecting to ADB](...)
#### 4. And finally the app installation itself:
```ADB
adb install [path/to/file.apk]
```


*This application was made using a neuro-network*

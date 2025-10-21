# Watch connection methods:

*Before this, you need to enable **Developer options** in the watch settings (tap **Build number** 7 times in About device section, then return to settings home screen), and enable **ADB debugging** there, then proceed with the following steps*

• Via USB connection - connect your watch using a USB cable with data transfer support (for PC) and allow authorization

• Via Wi-Fi connection - *not familiar with these watches yet, sorry*

• Via Bluetooth connection *(not recommended - slow)* - on the watch, in **Developer options** enable **Bluetooth debugging**, then on your phone go to Wear OS/Advanced settings app and enable **Bluetooth debugging**, enable **ADB debugging** in **Developer options** and (if you want remote connection or don't have a PC) **Wi-Fi debugging**, then, if you have wired connection - proceed to the next step, if not - go to **Wi-Fi debugging (Wireless connection settings)** and split screen with Termux, in settings tap **Pair device with pairing code** and enter in Termux:
```ADB
adb pair [your_code]
```
After that in Termux enter: 
```ADB
adb connect [IP:Port]
adb forward tcp:4444 localabstract:/adb-hub
adb connect localhost:4444
```

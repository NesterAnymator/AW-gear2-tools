> I'm new here, so please don't be mean to me.)

# Gear 2 Manager [ROOT]
This application tries to expand the functionality of Android Wear down to standard Android *(in this case, phone)* using system resources such as AppOps, PM, Settings, third-party tweaks, etc.

Приложение изначально предназначалось и тестировалось на часах Samsung Gear 2 Neo с кастомной прошивкой Android Wear 1.4.0.2633150 (на базе Android 6.0.1, номер сборки MEC23U), поэтому некоторые пункты предназначены именно для них, в будущем я их перемещу
 
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


## Установка приложения
1. Загрузите последнюю версию приложения из вкладки [Releases](https://github.com/NesterAnymator/AW-gear2-tools/releases)
 
2. (Для ПК на Windows) Загрузите [Minimal ADB & FastBoot](https://androidfilehost.com/?fid=746010030569952951) и запустите ярлык с рабочего стола Windows (или командную строку в директорию, где установлена программа)

• (Для телефона на Android) Загрузите [Termux](https://f-droid.org/ru/packages/com.termux) из F-Droid, установите и выполните команду:
```Termux
pkg update && pkg upgrade && pkg install android-tools
```
3. Способы подключения часов:

*Перед этим необходимо активировать пункт **Для разработчиков** в настройках часов (в пункте Об устройстве нажать 7 раз по **Номеру сборки**, затем перейти на главный экран), и в нём активировать **Отладку по ADB**, а дальше по следующим пунктам*

• Через USB-подключение - подключите ваши часы по проводу USB с поддержкой передачи данных (для ПК) и разрешите авторизацию

• Через Wi-Fi-подключение - *пока не знаю, дела не имел с такими часами, извините*

• Через Bluetooth-подключение *(не рекомендую - медленно)* - на часах, в пункте **Для разработчиков** включите **Отладку по Bluetooth**, далее на телефоне зайдите в приложение Wear OS/Расширенные настройки и включите **Отладку по Bluetooth**, включите в пункте **Для разработчиков** **Отладку по ADB** и (если хотите удалённое подключение или у вас нет ПК) **Отладку по Wi-Fi**, далее, если у вас проводное подключение - приступайте к следующему пункту, если нет - зайдите в раздел **Отладки по Wi-Fi (Параметры беспроводного подключения)** и сделайте разделение экрана с Termux, в настройках нажмите **Pair device with pairing code** и введите в Termux
```ADB
adb pair [your_code]
```
после в Termux введите 
```ADB
adb connect [IP:Port]
adb forward tcp:4444 localabstract:/adb-hub
adb connect localhost:4444
```
4. И наконец сама установка приложения:
```ADB
adb install [path/to/file.apk]




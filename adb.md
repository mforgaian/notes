# adb userful commands

## Saya Box Details
Saya box (android): 
MAC address: FC:D5:D9:09:96:AE
IP Address: 192.168.25.118

## Get IP with MAC
* arp | grep -i FC:D5:D9:09:96:AE
* -i option will grep for case insensitive results.

## Useful Commands
* connect to device through IP
```
adb connect <ip>
```
* list all attached devices
```
adb devices
```
* Connect to shell on device
```
adb shell
```
* to connect to a particular device
```
adb -s <device-io:port> shell
```

* Launch Chrome App
```
am start -n com.android.chrome/com.google.android.apps.chrome.Main
```
* Home Screen
```
am start -a android.intent.action.MAIN -c android.intent.category.HOME
```
* Launch default browser app
```
am start -a android.intent.action.VIEW -d http://192.168.29.39:8000
```
* stop default browser app
```
am force-stop android.intent.action.VIEW
```
* Get size of the device
```
wm size
```
* Get the density
```
wm density
```
* list all packages
```
pm list packages -f
```
* model name 
```
getprop ro.svp.modelname
```
### Power off and Restart
* Restart
```
reboot
```
* Power off
```
reboot -p
```

### Orientation
*  0 is portrait and 1 is landscape
* turn off automatic rotation
```
content insert --uri content://settings/system --bind name:s:accelerometer_rotation --bind value:i:0
```
* landscape
```
content insert --uri content://settings/system --bind name:s:user_rotation --bind value:i:1
```
* portrait
```
content insert --uri content://settings/system --bind name:s:user_rotation --bind value:i:0
```

## SAYA
* start SAYA app
```
am start com.gaian.saya.android/.BrowserActivity
```
* stop SAYA app
```
am force-stop com.gaian.saya.android
```
```
pm clear com.gaian.saya.android
```

## dumpsys
* dumpsys | grep "DUMP OF SERVICE"
* dumpsys battery
* dumpsys wifi
* dumpsys cpuinfo
* dumpsys meminfo



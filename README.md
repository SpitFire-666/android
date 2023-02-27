# Android

## Recommended Apps


| Function | App | Comments | Free/Open Source? | 
|-|-|-|-|
| Web Browser | [Firefox](https://play.google.com/store/apps/details?id=org.mozilla.firefox) | |
| Audio Book Player | Simple ABP Free | 
| Podcast App | AntennaPod |
| QR reader | BinaryEye |
| Image Searcher | [ImageSearchMan](https://play.google.com/store/apps/details?id=sansunsen3.imagesearcher) |
| Gallery app | Simple Gallery | 
| File Explorer | Solid Explorer | 
| Barcode/Wallet app | Anycode Wallet |
| Weather | Weatherzone
| To do/tasks | Microsoft ToDo
| Network Scanner | Fing (old version/apk) |
| YouTube client | NewPipe | 
| Calculator | |
| Instagram client | Barinsta
| Screen on toggle | Coffee
| Contacts | | 
| App Store | F-Droid |
| Music Player | Phonograph |
| PDF reader | |
| Spotify | Spotify Lite |
| Facebook Lite |
| VNC Viewer |
| Compass | 
| Unit Converter | |
| Remote Desktop (RDP) |  |
| Email | |
| Calendar | |
| Cast photos/videos/audio to DLNA (TV) | XCast |


## SMB Server

## Webcam Server

## VNC Server

## ADB Stuff

### Get Started
- Ensure ```USB debugging``` and ```Unknown Sources``` are enabled on the android phone 

```
adb devices 
```

![image](https://user-images.githubusercontent.com/38451588/221343145-190e7560-c416-4226-9694-8fb86de8f42a.png)


### Disable installed apps (no root required) 

- Use [Application Inspector](https://play.google.com/store/apps/details?id=com.ubqsoft.sec01) to help identify package names

- List enabled apps
```
adb shell pm list packages -e
```
- Disable the app: 
```
adb shell pm disable-user --user 0 <package_to_disable>
```
``` 
.\adb shell pm disable-user --user 0 com.google.android.feedback
.\adb shell pm disable-user --user 0 com.google.android.printservice.recommendation
.\adb shell pm disable-user --user 0 com.google.android.googlequicksearchbox # Google 
.\adb shell pm disable-user --user 0 com.google.android.music # Google Play Music
.\adb shell pm disable-user --user 0 com.google.android.apps.docs # Google Drive
.\adb shell pm disable-user --user 0 com.google.android.videos
.\adb shell pm disable-user --user 0 com.android.printspooler
.\adb shell pm disable-user --user 0 com.google.android.marvin.talkback # Android Accessibility Suite
.\adb shell pm disable-user --user 0 com.microsoft.skydrive # Microsoft Skydrive
.\adb shell pm disable-user --user 0 com.microsoft.office.officehubrow # Microsoft Office
.\adb shell pm disable-user --user 0 com.android.chrome # Chrome
.\adb shell pm disable-user --user 0 com.google.android.youtube
.\adb shell pm disable-user --user 0 com.google.android.tts # Google Text-to-speech Engine
.\adb shell pm disable-user --user 0 com.google.android.apps.turbo # Device Health Services
.\adb shell pm disable-user --user 0 com.google.android.gm #gmail
.\adb shell pm disable-user --user 0 com.google.android.apps.tachyon #Google Duo
```

## Copy files to Android in recovery mode
```
adb push "C:\NEXUS\Lineage\lineage-14.1-20171106-nightly-bullhead-signed.zip" /sdcard/ 
```

![image](https://user-images.githubusercontent.com/38451588/221347116-cceaec8a-6a42-47b6-877d-ab7285b705f7.png)

 
## Flash recovery (eg TWRP) 

- Boot into bootloader (fastboot) 
- Connect via USB 
- Open CMD/PowerShell 

```
fastboot flash recovery twrp.img 
fastboot reboot
```


ADB over WIFI 

Install app (easier than DIY) - ROOT access required! 

https://play.google.com/store/apps/details?id=com.ttxapps.wifiadb&hl=en 

 

Download ADB/Fastboot 

https://dl.google.com/android/repository/platform-tools-latest-windows.zip 

 

Connect to the IP:Port on PC 

.\adb.exe connect 192.168.1.31:5555 

 ![image](https://user-images.githubusercontent.com/38451588/221443969-00b604c2-2d90-473f-8165-e954f6380aaf.png)


Check the screen and allow any authentication requests 


ADB over USB 

ADB commands 

adb install "ES file explorer com.estrongs.android.old.apk" 

adb reboot recovery 

adb backup -all -f /backup/location/file.ab 

.\adb.exe shell pm list packages | select-string "fing" 

Backup an app and app data (ROOT required) 

 

# search for the app (eg fing) 

$test = .\adb.exe shell pm list packages | select-string "fing" 

# Grab the package name 

$test=($test.ToString()).trimstart("package");$test = $test.TrimStart(":") 

 

.\adb backup -f c:\temp\$test -apk $test 

.\adb.exe backup -f c:\temp\$test -apk $test 

$test=($test.ToString()).trimstart("package");$test = $test.TrimStart(":") 

 

 ## Re-enable app
 ```
 pm enable -–user 0 PackageName
 adb shell cmd package install-existing <package name>

```


 

$apkpath = .\adb.exe shell pm path $test 

$apkpath=($apkpath.ToString()).trimstart("package");$apkpath = $apkpath.TrimStart(":") 

 

 

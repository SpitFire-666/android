# Android

## Recommended Apps


| Function | App | Backup/Restore from App? | Free/Open Source? | 
|-|-|-|-|
| Web Browser | [Firefox](https://play.google.com/store/apps/details?id=org.mozilla.firefox) | Sync using firefox account, note that extension data does not get backed up! |
| Audio Book Player | Moises | No backup options exist | 
| Podcast App | AntennaPod | ✅  |
| QR reader | BinaryEye | N | 
| Image Searcher | ? |
| Gallery app | Simple Gallery | 
| File Explorer | Solid Explorer | 
| Barcode/Wallet app | Catima | ✅ |
| Weather | Weatherzone
| To do/tasks | Microsoft ToDo |
| Network Scanner | Fing (old version/apk) |
| YouTube client | NewPipe | ✅ |
| Calculator | |
| Instagram client | Barinsta 
| Screen on toggle | Coffee 
| Contacts | | 
| App Store | F-Droid/Aurora |
| Music Player | Phonograph Plus |
| PDF reader | FastPDFReader |
| Spotify | Spotify Lite |
| Facebook Lite |
| VNC Viewer |
| Compass | 
| Unit Converter | |
| Email | |
| Calendar | |
| Cast photos/videos/audio to DLNA (TV) | XCast |
| | TUFFS | 
| Metronome | Tempo | | 


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


### Uninstall apps

$packages = (.\adb.exe shell pm list packages -e) -replace("package:","") | ogv -PassThru
.\adb.exe uninstall --user 0 $packages


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

 
### Install (Sideload) an .apk

Ensure USB debugging and Unknown Sources are enabled on the android phone

adb install "ES file explorer com.estrongs.android.old.apk" 

![image](https://user-images.githubusercontent.com/38451588/223316757-7dcd22f7-1bbd-4867-906e-a5ab94745129.png)


### PowerShell bulk .APK installation 
```powershell
$apks = ls *.apk -path c:\nexus\apps | select -ExpandProperty FullName 
Foreach($apk in $apks){.\adb.exe install $apk 
Write-host "installing $apk" -foregroundcolor yellow 
}
```

![image](https://user-images.githubusercontent.com/38451588/223316836-e96147a9-677b-414d-bca8-980235f28729.png)


 ### Backup .APK files/installers from device (Solid Explorer)

1. Menu
2. Applications
3. User Apps
4. Select All
5. Copy
6. Paste somewhere



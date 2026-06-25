# 📱 Android

## Recommended Apps

| Function | App | Backup/Restore from App? | Free/Open Source? | 
|-|-|-|-|
| 🌎 Web Browser | [Firefox](https://play.google.com/store/apps/details?id=org.mozilla.firefox) | Sync using firefox account, note that extension data does not get backed up! |
| Audio Book Player | [Voice](https://github.com/PaulWoitaschek/Voice/releases/download/25.9.19-5309019/app-github-release.apk) | No backup options exist | 
| 📞 Phone | [Fossify Phone](https://github.com/FossifyOrg/Phone/releases/download/1.7.1/phone-14-foss-release.apk) | 
| SMS/Messages | [Fossify Messages](https://github.com/FossifyOrg/Messages/releases/download/1.3.0/messages-15-foss-release.apk)
| Podcast App | [AntennaPod](https://f-droid.org/repo/de.danoeh.antennapod_3090095.apk) | ✅ | ✅ |
| QR reader | [BinaryEye](https://f-droid.org/repo/de.markusfisch.android.binaryeye_150.apk) | N | 
| 📷 Camera |  |
| ⌨ Keyboard | [FUTO Keyboard](https://github.com/futo-org/android-keyboard/releases/download/0.1.25/keyboard-0.1.25.apk) | ✅ | ✅ |
| Image Searcher | ? |
| 🖼 Gallery app | [Fossify Gallery](https://github.com/FossifyOrg/Gallery/releases/download/1.5.2/gallery-17-foss-release.apk) | | ✅ |
| File Explorer | Solid Explorer | 
| Barcode/Wallet app | [Catima](https://github.com/CatimaLoyalty/Android/releases/download/v2.38.0/app-foss-release.apk) | ✅ |
| Weather | Weatherzone |
| To do/tasks | Microsoft ToDo |
| Network Scanner | Fing (old version/apk) |
| 📺 YouTube client | [NewPipe](https://github.com/TeamNewPipe/NewPipe/releases/download/v0.28.0/NewPipe_v0.28.0.apk) | ✅ | ✅ | 
| Calculator | |
| Screen on toggle | Coffee |
| 📖 Contacts | Fossify Contacts | ✅ | ✅ |
| App Store | F-Droid/Aurora store |
| 🎶 Music Player | [Phonograph Plus](https://github.com/chr56/Phonograph_Plus/releases/download/v1.11.0/PhonographPlus_1.11.0_ModernStableRelease.apk) |
| PDF reader | FastPDFReader |
| Compass | 
| Unit Converter | |
| 🗓 Calendar | [Fossify Calendar](https://github.com/FossifyOrg/Calendar/releases/download/1.6.1/calendar-11-foss-release.apk) |
| Cast photos/videos/audio to DLNA (TV) | XCast |
| | TUFFS |


### Get Started
- Ensure ```USB debugging``` and ```Unknown Sources``` are enabled on the android phone 

```
adb devices
```

![image](https://user-images.githubusercontent.com/38451588/221343145-190e7560-c416-4226-9694-8fb86de8f42a.png)

## Uninstall apps - no root required!

```powershell
$bloatware = @(
"com.google.android.feedback"
"com.google.android.printservice.recommendation"
"com.google.android.googlequicksearchbox" # Google 
"com.google.android.music" # Google Play Music
"com.google.android.apps.docs" # Google Drive
"com.google.android.videos"
"com.microsoft.skydrive" # Microsoft OneDrive/Skydrive
"com.microsoft.office.officehubrow" # Microsoft Office
"com.google.android.apps.turbo" # Device Health Services
"com.google.android.gm" #gmail
"com.google.android.apps.tachyon" #Google Duo
"com.samsung.android.bixby.wakeup" # Bixby
"com.samsung.android.bixby.agent" # Bixby
"com.samsung.android.visionintelligence" # Bixby Vision
"com.facebook.katana" # facebook
"com.samsung.android.app.tips" # Samsung Tips
"com.samsung.android.game.gamehome" # Gaming hub
"com.samsung.android.app.camera.sticker.facearavatar.preload"  # Avatar Stickers
"com.sec.android.mimage.avatarstickers"
"com.google.android.adservices.api" # Ad privacy
"com.google.android.healthconnect.controller" # Health Connect
"com.instagram.android" # Instagram
"com.google.android.apps.bard" # Google Gemini
"com.android.hotwordenrollment.okgoogle" # Hey Google hotword
"com.sec.android.app.vepreload" # Studio/Samsung video editor
"com.samsung.android.samsungpassautofill" # Autofill with samsung pass
"com.google.audio.hearing.visualization.accessibility.scribe" # Live Transcribe and SOund notifications
"com.sec.android.app.samsungapps" # Samsung galaxy store
"com.google.android.youtube" # youtube
"com.google.android.gm" # gmail
"com.android.chrome" # Chrome
"au.com.vodafone.mobile.gss" # My Vodafone - forced install
"com.amazon.mShop.android.shopping" # Amazon Shopping
"com.amazon.appmanager" # Amazon Mobile Device Information Provider
"com.samsung.android.vtcamerasettings" # Samsung video call effects
"com.samsung.SMT" # Samsung text-to-speech engine
"com.samsung.android.ardrawing" # Samsung AR Drawing
"com.netflix.partner.activation" # Netflix
"com.sec.android.easyMover.Agent" # Samsung Smart Switch - device migration tool
"com.sec.android.easyMover" # Samsung Smart Switch
"com.samsung.android.calendar" # Samsung Calendar
"com.samsung.android.app.reminder" # Samsung Reminder
"com.osp.app.signin" # Samsung Account
"com.samsung.android.scloud" # Samsung CLoud
"com.samsung.android.mapsagent" # Application recommendations
"com.samsung.android.app.omcagent" # Recommended apps
"com.samsung.android.app.camera.sticker.facearavatar.preload" # Crocro and friends
"com.samsung.android.themestore" # Galaxy themes
"com.samsung.android.themecenter" # Galaxy themes Service
"com.samsung.android.messaging" # Samsung Messages
"com.google.android.apps.messaging" # Google Messaging
"com.samsung.android.dbsc" # Galaxy setup
"com.sec.android.app.SecSetupWizard" #Samsung Setup Wizard
"com.sec.phone" # Samsung phone - warning!
"com.sec.android.app.setupwizard" #Setup Wizard
"com.samsung.android.app.routines" # Modes and routines
# gallery
# contacts 
"com.samsung.android.dialer" # Samsung PHone
)
$bloatware | % {
# .\adb shell pm disable-user --user 0 $_ # Optional: disable instead of uninstall
.\adb.exe uninstall --user 0 $_
}
```

List packages

```powershell
adb.exe shell pm list packages -e
```

Interactive uninstaller/en-masse

```powershell
$packages = (.\adb.exe shell pm list packages -e) -replace("package:","") | ogv -PassThru
.\adb.exe uninstall --user 0 $packages
```

### Copy files from PC to Phone
```powershell
C:\Android\ADB+Fastboot\adb push "C:\Android\file.zip" /sdcard/Download/
```

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


# Lock / Unlock bootloader
- Can be done with or without computer

## Computer via USB
1. Boot phone into Fastboot mode (reboot while holding Vol Down key)
2. 

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

 

### Download ADB/Fastboot 

https://dl.google.com/android/repository/platform-tools-latest-windows.zip 

 

Connect to the IP:Port on PC 

```powershell
.\adb.exe connect 192.168.1.31:5555 
```
 ![image](https://user-images.githubusercontent.com/38451588/221443969-00b604c2-2d90-473f-8165-e954f6380aaf.png)

Check the screen and allow any authentication requests 

ADB over USB 

ADB commands 
```
adb install "ES file explorer com.estrongs.android.old.apk" 
```
```
adb reboot recovery 
```
```
adb backup -all -f /backup/location/file.ab 
```

```powershell
.\adb.exe shell pm list packages | select-string "fing" 
```

### Backup an app and app data (ROOT required) 
```
# search for the app (eg fing) 
$test = .\adb.exe shell pm list packages | select-string "fing" 

# Grab the package name 

$test=($test.ToString()).trimstart("package");$test = $test.TrimStart(":") 

.\adb backup -f c:\temp\$test -apk $test 

.\adb.exe backup -f c:\temp\$test -apk $test 

$test=($test.ToString()).trimstart("package");$test = $test.TrimStart(":") 

``` 

 ## Re-enable an app
```
pm enable -–user 0 PackageName
adb shell cmd package install-existing <package name>
```

```
$apkpath = .\adb.exe shell pm path $test 
$apkpath=($apkpath.ToString()).trimstart("package");$apkpath = $apkpath.TrimStart(":") 
```
 
### Install (Sideload) an .apk

- Ensure USB debugging and Unknown Sources are enabled on the android phone

```
adb install "ES file explorer com.estrongs.android.old.apk" 
```
![image](https://user-images.githubusercontent.com/38451588/223316757-7dcd22f7-1bbd-4867-906e-a5ab94745129.png)


### PowerShell bulk .APK installation 
```powershell
$apks = (ls *.apk -path 'C:\APKs\').fullname | ogv -PassThru -Title "Choose apps to install"
Foreach($apk in $apks){
Write-Progress -Activity "Installing $apk"
.\adb.exe install --bypass-low-target-sdk-block $apk  
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


## Theming

- Icons: Use wrestool to extract icons from Windows .exe and .dll files
- Convert .ico to .png using imagemagick
- For Nova launcher, theme icons in the app drawer (NOT the home screen)
- Tile wallpaper using imagemagick

Nova launcher wallpaper
- Use Gallery (instead of Nova launcher) to set the wallpaper
- ..., Set as, Gallery Wallpaper, tap the 4 arrows, resize, apply


## SMB Server

## Webcam Server

## VNC Server

## ADB Stuff

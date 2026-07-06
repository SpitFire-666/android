# 📱 Android

## Recommended Apps

| Function | App | Backup/Restore from App? | Free/Open Source? | 
|-|-|-|-|
| 🌎 Web Browser | [Firefox](https://play.google.com/store/apps/details?id=org.mozilla.firefox) | Sync using firefox account, note that extension data does not get backed up! |
| Audio Book Player | [Voice](https://github.com/PaulWoitaschek/Voice/releases/download/25.9.19-5309019/app-github-release.apk) | No backup options exist | 
| 📞 Phone | [Fossify Phone](https://github.com/FossifyOrg/Phone/releases/download/1.7.1/phone-14-foss-release.apk) | 
| SMS/Messages | [Fossify Messages](https://github.com/FossifyOrg/Messages/releases/download/1.3.0/messages-15-foss-release.apk) | [Do the backup from v1.7 as there's a bug in newer versions](https://github.com/FossifyOrg/Messages/issues/713) | |
| Podcast App | [AntennaPod](https://f-droid.org/repo/de.danoeh.antennapod_3090095.apk) | ✅ | ✅ |
| QR reader | [BinaryEye](https://f-droid.org/repo/de.markusfisch.android.binaryeye_150.apk) | N | 
| 📷 Camera |  |
| ⌨ Keyboard | [FUTO Keyboard](https://github.com/futo-org/android-keyboard/releases/download/0.1.25/keyboard-0.1.25.apk) | ✅ | ✅ |
| Image Searcher | ? |
| 🖼 Gallery app | [Fossify Gallery](https://github.com/FossifyOrg/Gallery/releases/download/1.5.2/gallery-17-foss-release.apk) | | ✅ |
| File Explorer | Solid Explorer | 
| Barcode/Wallet app | [Catima](https://github.com/CatimaLoyalty/Android/releases/download/v2.38.0/app-foss-release.apk) | ✅ |
| Weather | ?? |
| To do/tasks | ?? |
| Network Scanner | Fing (old version/apk) | Note - I think newer Android versions have crippled useful network tools |
| 📺 YouTube client | [NewPipe](https://github.com/TeamNewPipe/NewPipe/releases/download/v0.28.0/NewPipe_v0.28.0.apk) | ✅ | ✅ | 
| Calculator | |
| Screen on toggle | [Coffee](https://f-droid.org/packages/com.github.muellerma.coffee/) | |
| 📖 Contacts | Fossify Contacts | ✅ | ✅ |
| App Store | F-Droid/Aurora store |
| 🎶 Music Player | [Phonograph Plus](https://github.com/chr56/Phonograph_Plus/releases/download/v1.11.0/PhonographPlus_1.11.0_ModernStableRelease.apk) |
| PDF reader | [FastPDFReader](https://play.google.com/store/apps/details?id=yeolee.co.kr.fastpdfreader) |
| Compass | 
| Unit Converter | |
| 🗓 Calendar | [Fossify Calendar](https://github.com/FossifyOrg/Calendar/releases/download/1.6.1/calendar-11-foss-release.apk) |
| Cast photos/videos/audio to DLNA (TV) | XCast |
| |  |


# De-Bloat (Uninstall/Disable apps - no root required!)

1. Ensure ```USB debugging``` and ```Unknown Sources``` are enabled on the android phone 
2. List packages
```powershell
(.\adb.exe shell pm list packages -e) -replace("package:")
```
- Use [Application Inspector](https://play.google.com/store/apps/details?id=com.ubqsoft.sec01) to identify package names

3. De-bloat!
```powershell
$bloatware = @(
"au.com.vodafone.mobile.gss" # My Vodafone - forced install
"com.amazon.appmanager" # Amazon Mobile Device Information Provider
"com.amazon.mShop.android.shopping" # Amazon Shopping
"com.android.chrome" # Google Chrome | warning, BYO browser
"com.android.hotwordenrollment.okgoogle" # Hey Google hotword
"com.asurion.android.verizon.vms" # Verizon
"com.audible.application" # Audible
"com.blurb.checkout"
"com.cequint.ecid"
"com.enhance.gameservice" # SAMSUNG GAME LAUNCHER 
"com.facebook.appmanager" # Facebook
"com.facebook.katana" # Facebook
"com.facebook.services" # Facebook
"com.facebook.system" # Facebook
"com.google.android.adservices.api" # Ad privacy
"com.google.android.apps.bard" # Google Gemini
"com.google.android.apps.docs" # Google Drive
"com.google.android.apps.messaging" # Google Messaging
"com.google.android.apps.tachyon" #Google Duo
"com.google.android.apps.turbo" # Device Health Services
"com.google.android.feedback"
"com.google.android.gm" # gmail app
"com.google.android.googlequicksearchbox" # Google search - FYI this comes back when using Android Auto
"com.google.android.health.connect.backuprestore"  # Google health
"com.google.android.healthconnect.controller" # Google health
"com.google.android.music" # Google Play Music
"com.google.android.overlay.modules.healthfitness.forframework"  # Google health
"com.google.android.printservice.recommendation"
"com.google.android.safetycore" # scans your device for naughty content https://allaboutcookies.org/what-is-android-system-safetycore
"com.google.android.videos"
"com.google.android.youtube" # youtube
"com.google.androidglasses.core" # Glasses Core
"com.google.ar.core" # Google Play services for AR (augmented reality)
"com.google.audio.hearing.visualization.accessibility.scribe" # Live Transcribe and SOund notifications
"com.google.mainline.adservices" 
"com.google.mainline.telemetry"
"com.google.vr.vrcore" # Virtual reality
"com.gotv.nflgamecenter.us.lite" # NFL Game center
"com.hancom.office.editor.hidden"
"com.imdb.mobile" # IMDB app
"com.infraware.polarisoffice5"
"com.instagram.android" # Instagram
"com.microsoft.office.excel" # Microsoft Excel
"com.microsoft.office.officehubrow" # Microsoft Office
"com.microsoft.office.powerpoint" # Microsoft 
"com.microsoft.office.word" # Microsoft 
"com.microsoft.skydrive" # Microsoft OneDrive/Skydrive
"com.microsoft.skydrive" # Microsoft skydrive/onedrive
"com.mobitv.client.tmobiletvhd" # T-Mobile
"com.motricity.verizon.ssodownloadable" # Verizon
"com.netflix.partner.activation" # Netflix
"com.nuance.swype.input" # Swype keyboard
"com.osp.app.signin" # Samsung Account
"com.samsung.android.app.camera.sticker.facearavatar.preload"  # Avatar Stickers/Crocro and friends
"com.samsung.android.app.contacts" # Samsung contacts - you'll need a replacement!
"com.samsung.android.app.interpreter" # Samsung translation/interpreter
"com.samsung.android.app.omcagent" # Samsung Recommended apps
"com.samsung.android.app.parentalcare" # Parental controls
"com.samsung.android.app.reminder" # Samsung Reminder
"com.samsung.android.app.routines" # Samsung Modes and routines
"com.samsung.android.app.sbrowseredge" # SAMSUNG browser
"com.samsung.android.app.storyalbumwidget"
"com.samsung.android.app.tips" # Samsung Tips
"com.samsung.android.app.vrsetupwizardstub" # Virtual reality
"com.samsung.android.app.watchmanagerstub" # Wearable Manager Installer
"com.samsung.android.ardrawing" # Samsung AR Drawing
"com.samsung.android.bixby.agent" # Samsung Bixby
"com.samsung.android.bixby.wakeup" # Samsung Bixby
"com.samsung.android.bixbyvision.framework" # Bixby
"com.samsung.android.calendar" # Samsung Calendar
"com.samsung.android.dbsc" # Galaxy setup
"com.samsung.android.dialer" # Samsung Phone | Warning - You'll need a replacement!
"com.samsung.android.email.provider" # SAMSUNG email
"com.samsung.android.forest" # digital wellbeing
"com.samsung.android.game.gamehome" # SAMSUNG GAME LAUNCHER
"com.samsung.android.game.gametools" # SAMSUNG GAME LAUNCHER
"com.samsung.android.hmt.vrshell" # Virtual reality
"com.samsung.android.hmt.vrsvc" # Virtual reality
"com.samsung.android.intellivoiceservice" # Samsung Intelligence Voice Service is the system for connecting to the LLM server and Galaxy Advanced Intelligence services in Samsung Native Applications
"com.samsung.android.kidsinstaller" # Samsung kids profile
"com.samsung.android.knox.analytics.uploader"
"com.samsung.android.mapsagent" # Application recommendations
"com.samsung.android.messaging" # Samsung Messages
"com.samsung.android.samsungpassautofill" # Autofill with samsung pass
"com.samsung.android.scloud" # Samsung CLoud
"com.samsung.android.smartsuggestions" # Samsung smart suggestions | recommends apps/actions based on usage | https://www.xda-developers.com/how-to-use-smart-suggestions-on-samsung-device/
"com.samsung.android.themecenter" # Galaxy themes Service
"com.samsung.android.themestore" # Galaxy themes
"com.samsung.android.visionintelligence"
"com.samsung.android.visionintelligence" # Bixby Vision
"com.samsung.android.vtcamerasettings" # Samsung video call effects
"com.samsung.android.widgetapp.yahooedge.finance"
"com.samsung.android.widgetapp.yahooedge.sport"
"com.samsung.petservice" # Samsung pet care
"com.samsung.SMT" # Samsung text-to-speech engine
"com.samsung.SMT.lang_es_es_f00"
"com.samsung.SMT.lang_es_mx_f00"
"com.samsung.SMT.lang_es_us_f00"
"com.samsung.SMT.lang_fr_fr_f00"
"com.samsung.SMT.lang_hi_in_f00"
"com.samsung.SMT.lang_id_id_f00"
"com.samsung.SMT.lang_it_it_f00"
"com.samsung.SMT.lang_pl_pl_f00"
"com.samsung.SMT.lang_pt_br_f00"
"com.samsung.SMT.lang_ru_ru_f00"
"com.samsung.SMT.lang_th_th_f00"
"com.samsung.SMT.lang_vi_vn_f00"
"com.samsung.vmmhux" # Verizon
"com.samsung.vvm" # Verizon
"com.sec.android.app.chromecustomizations"
"com.sec.android.app.samsungapps" # Samsung galaxy store
"com.sec.android.app.sbrowser" # SAMSUNG browser
"com.sec.android.app.SecSetupWizard" #Samsung Setup Wizard
"com.sec.android.app.setupwizard" #Setup Wizard
"com.sec.android.app.vepreload" # Studio/Samsung video editor
"com.sec.android.easyMover" # Samsung Smart Switch
"com.sec.android.easyMover.Agent" # Samsung Smart Switch - device migration tool
"com.sec.android.mimage.avatarstickers"
"com.sec.phone" # Samsung phone - warning!
"com.sec.svoice.lang.de_DE" # German
"com.sec.svoice.lang.es_ES" # Spanish
"com.sec.svoice.lang.fr_FR" # French
"com.sec.svoice.lang.it_IT" # italian
"com.skype.raider" # Microsoft 
"com.swiftkey.swiftkeyconfigurator"
"com.touchtype.swiftkey"
"com.tripadvisor.tripadvisor"
"com.vcast.mediamanager" # Verizon
"com.vzw.hs.android.modlite" # Verizon
"com.vzw.hss.myverizon" # Verizon
"com.wsomacp" # SAMSUNG email
"flipboard.app"
"flipboard.boxer.app"
"us.com.dt.iq.appsource.tmobile" # T-Mobile
# gallery
# interpreter /Galaxy AI
# Samsung audio broadcast/auracast | for sharing audio
# Samsung digital wellbeing / Weekly report
#"com.google.android.partnersetup" # best to leave as is
#"com.qti.qcc" # Qualcomm - could be important
#"com.sec.svoice.lang.en_GB" 
#"com.sec.svoice.lang.en_US"
)
$bloatware | % {
# .\adb shell pm disable-user --user 0 $_ # Optional: disable instead of uninstall
.\adb.exe uninstall --user 0 $_ # Uninstall
}
```

### Re-enable an app
```
pm enable -–user 0 PackageName
adb shell cmd package install-existing <package name>
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

### Copy files to Android in recovery mode
```
adb push "C:\NEXUS\Lineage\lineage-14.1-20171106-nightly-bullhead-signed.zip" /sdcard/ 
```

![image](https://user-images.githubusercontent.com/38451588/221347116-cceaec8a-6a42-47b6-877d-ab7285b705f7.png)


#### Lock / Unlock bootloader
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

### ADB over WIFI (ROOT required)

Install app (easier than DIY) - ROOT access required! 

https://play.google.com/store/apps/details?id=com.ttxapps.wifiadb&hl=en 


### Download ADB/Fastboot tools

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

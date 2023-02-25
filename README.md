# Android

## App Recommendations


| Function | App | Comments | Free/Open Source? | 
|-|-|-|-|
| Web Browser | [Firefox](https://play.google.com/store/apps/details?id=org.mozilla.firefox) | |
| Audio Book Player:  |
| Podcast App | AntennaPod |
| QR reader | BinaryEye
| Image Searcher | [ImageSearchMan](https://play.google.com/store/apps/details?id=sansunsen3.imagesearcher) |
| Gallery app | Simple Gallery | 
| File Explorer | Solid Explorer | 
| Barcode/Wallet app | Anycode Wallet
| Weather | Weatherzone
| To do/tasks | Microsoft ToDo
| Network Scanner | Fing (old version/apk)
| Calculator | 
| Instagram alternative | Barinsta
| Screen on | Coffee
| Contacts| | 
| App Store | F-Droid |
| Music Player | Phonograph |
| PDF reader | 
| Spotify | Spotify Lite |
| Facebook Lite |
| VNC Viewer |
| Compass | 
| Unit Converter | 
| Remote Desktop (RDP) | 
| Email |
| Calendar | 


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

- List enabled apps 
```
adb shell pm list packages -e  
```
- Disable the app: 
```
adb shell pm disable-user --user 0 <package_to_disable> 
```
 

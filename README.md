# wearos-adb
This is an installation the application and setup guide for a Galaxy Watch 4, running WearOS. I will be sharing my use of the Galaxy Watch 4 device, with a version of WearOS in standalone mode.

## init config
The first thing to do is start the device in standalone mode. When we are in standalone mode, we are limited in terms of many functions by not having a mobile device, precisely because we cannot download applications via play store or start some services such as Google, where a device is required to log in.

There are some applications on Android that allow us to install applications on the Smart Watch, such as Easy Fire Tools, Wear Installer 2, Bugjaeger. These mentioned apps can be installed through Play Store. I tested those applications directly when I installed the ChromeOS and FydeOS systems. They work but in this case it doesn't make sense to me because I don't have an Android device.

## Content
- Links of interest.
- Applications required for installation.
- Pair and connect via ADB.
- What applications are compatible?
- Install and uninstall applications.
- Change DPI.
- Installation guide for WhatsApp.
- Installation guide for Spotify(Not Mod).
- Delete non-functional apps.

### Links of interest.
https://xdaforums.com/t/official-list-of-sideloaded-apps-and-workarounds-for-wear-os-tested-on-galaxy-watch.4379825/
https://xdaforums.com/t/debloat-galaxy-watch-4.4324147/
https://docs.google.com/spreadsheets/d/1ZTABVVW4VJPFn9Pcib_JBg-foceF5B8wR8HkSphmbfQ/edit?pli=1#gid=1255061357&fvid=741828337

## Applications required for installation
- ADB (Android Debug Bridge) - https://developer.android.com/studio/releases/platform-tools

## Command to connect via ADB
```bash
adb pair <ip>:<port>
```
Enter the code that appears on the screen of the Smart Watch,
later we can connect with the command:

```bash
adb connect <ip>:<port>
```

## What applications are compatible?
It is here that we have to be careful, the architecture of the Smart Watch is armeabi-v7a, the apps build in arm64-v8a not work.

## Install and uninstall applications
To install an application, we must have the .apk file, we can install it with the command:
```bash
adb -e install <file.apk>
```
The parameter -e used the connection later with the command adb connect, if you have problems with the connection with emulator, you can use the parameter -s <ip>:<port>.

To uninstall an application, we must know the package name, but using an command we can list all the installed applications:
```bash
adb shell pm list packages
```

```bash
adb shell pm uninstall -k --user 0 <package
```
The parameter -k is to keep the data and cache, --user 0 is to uninstall the application for all users.

## Change DPI
To change the DPI of the Smart Watch, we can use the command:
```bash
adb shell wm density <dpi> #(density reset)
```
The default DPI is 320, I recommend using 240.


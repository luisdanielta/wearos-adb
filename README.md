# wearos-adb
This is an installation the application and setup guide for a Galaxy Watch 4, running WearOS. I will be sharing my use of the Galaxy Watch 4 device, with a version of WearOS in standalone mode.

In my case I did not have an Android device, since there is no direct compatibility with iPhone devices. I tried using the android studio emulator, I directly installed a version of androidx86, I tried with chromeOS through Brunch Framework, FydeOS, virtual machine with virtual box and with none of these solutions I could get good results. The objective was to install the Wacth Manager application and start with the Google account and obtain all the benefits using the bt driver of my laptop, which in all cases was fully compatible with the installation of the system, successfully connecting with other devices on the setting section. (Not in the app) On chromeOS and fydeOS with the results I had some hope because the app recognized the Smart Watch and connected successfully with the app, but it turns out that this is not the main app (Watch Manager) that app installs another app called Wacth4 Plugin in my case, the problem is there, it does not start the application and from there it stops, it does not open the application. In some forums and solutions to this problem they talk about uninstalling the application, emptying the cache, some about disabling specific system notifications, but none of that gave results.

Therefore, you can follow all the steps in that guide on a computer with any operating system. All installations will depend entirely on your operating system, so it is necessary to have basic knowledge of your own system.

## init config
The first thing to do is start the device in standalone mode. When we are in standalone mode, we are limited in terms of many functions by not having a mobile device, precisely because we cannot download applications via play store or start some services such as Google, where a device is required to log in.

There are some applications on Android that allow us to install applications on the Smart Watch, such as Easy Fire Tools, Wear Installer 2, Bugjaeger. These mentioned apps can be installed through Play Store. I tested those applications directly when I installed the ChromeOS and FydeOS systems. They work but in this case it doesn't make sense to me because I don't have an Android device.

## Content
- Links of interest.
- Applications required for installation.
- Pair and connect via ADB.
- What applications are compatible?
- Search apps.
- Install and uninstall applications.
- Change DPI.
- Installation guide for WhatsApp.
- Installation guide for Spotify(Not Mod).
- Delete non-functional apps.

## Command to connect via ADB
```bash
adb pair <ip>:<port>
```
This process input a code on the Smart Watch, and the connection is established.
later we can connect with the command:
```bash
adb connect <ip>:<port>
```
## Applications required for installation
- ADB (Android Debug Bridge) - https://developer.android.com/studio/releases/platform-tools

## What applications are compatible?
It is here that we have to be careful, the architecture of the Smart Watch is armeabi-v7a, the apps build in arm64-v8a not work.

### Links of interest.
https://xdaforums.com/t/official-list-of-sideloaded-apps-and-workarounds-for-wear-os-tested-on-galaxy-watch.4379825/
https://xdaforums.com/t/debloat-galaxy-watch-4.4324147/
https://docs.google.com/spreadsheets/d/1ZTABVVW4VJPFn9Pcib_JBg-foceF5B8wR8HkSphmbfQ/edit?pli=1#gid=1255061357&fvid=741828337

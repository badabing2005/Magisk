![Magisk-Logo](docs/images/logo.png)

[![Github Releases](https://img.shields.io/github/downloads/badabing2005/Magisk/total.svg?style=flat)](https://github.com/badabing2005/Magisk/releases)

#### This is not an officially supported Google or even Magisk product

## Introduction

This is a special Magisk fork that disables modules but keeps root to allow recovering from bad modules that are causing bootloop.

## To recover from bootloop due to bad modules

First and foremost try what is suggested in [Magisk's FAQ](https://topjohnwu.github.io/Magisk/faq.html) first bullet.

> ## Q: I installed a module and it bootlooped my device. Help
>
> If you have USB debugging enabled in developer options, connect your phone to the PC. If your device is detected (check by adb devices), enter ADB shell and run the command magisk --remove-modules. This will remove all your modules and automatically reboot the device.
>
> If unfortunately you do not have USB debugging enabled, reboot into Safe Mode. Most modern Android devices support pressing a special key combo at boot to enter Safe Mode as an emergency option. Magisk will detect Safe Mode being activated, and all modules will be disabled. Then reboot back to normal mode (the module disable state persists) and manage your modules through the Magisk app.

### If unable to get into safe mode to disable Magisk or timing isn't right, follow the steps below

1. Flash stock `boot.img` / `init_boot.img` matching your current firmware, this would allow you to boot to system as bad modules cannot be loaded. 
You can do this from fastboot command line or using [PixelFlasher.](https://github.com/badabing2005/PixelFlasher).
    - Follow the [Basic Mode steps](https://github.com/badabing2005/PixelFlasher#basic-mode) 1 to 6, and then hit the ![Image of Flash-Boot](https://github.com/badabing2005/PixelFlasher/raw/v6.0.0.0/images/flash-24.png) `Flash Boot` button to the right of boot selection.
    - At this point your device should be back to a functional unrooted device.
2. Next, download special Magisk build from [releases](https://github.com/badabing2005/Magisk/releases) (debug or release, as you wish). As of this writing the special Magisk is based on **versionCode 26401**, and has module loading disabled but root is enabled, you will need to use this temporarily so that you can fix the bad modules situation.
3. Uninstall currently installed Magisk application from your device.
4. In PixelFlasher, click on `Settings` and `Enable Advanced Option`, as well as `Offer Patch Methods`.
![image](https://github.com/badabing2005/Magisk/assets/22603312/d5078c82-3252-410d-a23d-fd3a58850565)
5. Next, select the same stock boot that you flashed in step 1, and hit the `Patch` button.
6. PixelFlasher will propose patch options. Ignore the recommendation and select `Other Magisk`
![image](https://github.com/badabing2005/Magisk/assets/22603312/12aeb29c-c3b1-4a2c-b9df-c5a500df0ea5)
7. File open dialog will be presented, navigate and select the special Magisk that you downloaded from here.
8. PixelFlasher will create a patch file, and you should see it listed.
![image](https://github.com/badabing2005/Magisk/assets/22603312/dae63f0a-2bd7-4655-af8a-69838a01a593)
9. Next, select the newly created patch file and hit ![Image of Flash-Boot](https://github.com/badabing2005/PixelFlasher/raw/v6.0.0.0/images/flash-24.png) `Flash Boot` button.
10. When your system reboots, you should be rooted, but modules won't be loaded, and you can go and disable suspect modules in Magisk application. Use the downloaded version of Magisk to do so, you can use PixelFlasher's `Install APK` feature to select and install the Magisk from your computer.
11. Now that you have disabled suspect modules, you want to uninstall the special Magisk application, and flash stock boot / init_boot as in step 1.
12. When your system reboots unrooted, select the stock boot and hit the `Patch` button.
13. PixelFlasher will detect that you don't have Magisk installed and will offer the latest available Magisk to install from. Select the flavor that you desire and hit the `Install` button.
![image](https://github.com/badabing2005/Magisk/assets/22603312/4f9a86f0-82fc-4f2d-b817-6c18a0e1e1f5)
PixelFlasher will install Magisk and use it to create a patch file.
14. Select the newly created patch file, and one more time hit the ![Image of Flash-Boot](https://github.com/badabing2005/PixelFlasher/raw/v6.0.0.0/images/flash-24.png) `Flash Boot` button. This will be your final flashing, your device should be properly rooted and whatever modules you enabled should be operational.

## Downloads

See releases section.

## Useful Links

- [PixelFlasher](https://github.com/badabing2005/PixelFlasher/tree/main)
- [Building and Development](https://topjohnwu.github.io/Magisk/build.html)
- [Magisk Documentation](https://topjohnwu.github.io/Magisk/)

## Credits

- Obviously Magisk and contributors to Magisk.
- @HarryWindsor who came up with the idea [here](https://github.com/topjohnwu/Magisk/issues/6301).

## License

    Magisk, including all git submodules are free software:
    you can redistribute it and/or modify it under the terms of the
    GNU General Public License as published by the Free Software Foundation,
    either version 3 of the License, or (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.

## fastboot

### Overview

Android device has 3 important partitions - Boot loader, Recovery, Android ROM. Boot loader loads first and decides the next partition to be loaded (which is usually the Android ROM). Recovery is the mode that is used by device to install updates to Android ROM partition. It is also used while factory resetting the phone. The recovery that comes by default usually has less options and that is why custom recovery modules are available.

Fastboot on the other hand is a protocol that can be used to connect to the device from a computer over USB and issue updates to the partitions of the device. For example, while I'm in fastboot I can update by recovery partition.

From [kingoapp.com](http://www.kingoapp.com/help/fastboot-mode.htm), fastboot is defined as:

> Fastboot is a protocol that can be used to re-flash partitions on your device (update the flash file system in Android devices). It is this small tool that comes with the Android SDK (Software Developer Kit), which is an alternative to the Recovery Mode for doing installations and updates.

> Not all phones have a fastboot mode that the user can access. It’s turned on with Nexus devices by default as well as a few other phones and tablets and has been enabled by independent Android developers and enthusiasts on some other phones.

### What is Fastboot for?

While in fastboot, you can modify the file system images from a computer over a USB connection. Fastboot mode can start on your device even before Android loads, even under the circumstance when Android isn’t installed at all. And because of that, fastboot mode is useful for quick-updating the firmware, without having to use a recovery mode.

### fastboot in AndroidTamer

<center>
![image](/images/fastboot.png)
</center>

> **Usage :** 

> **android@tamer:~$** `fastboot [ <option> ] <command>`
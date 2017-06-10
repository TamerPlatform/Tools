# ADB

## What Are fastboot and adb

Fastboot and Adb are two programs found in the Android development SDK (AndroidSDK) that allow you to transfer files,install programs, 
flash images, and run commands on your Android phone. Another thing to note: ADB can only connect to your phone while it is
in recovery or booted into the OS.Fastboot can only be used when your device is in bootloader mode. 
Finally, one of the most important thing in terms of android development is to access the bootloader for device.

## FastBoot

#### Check to see if your device is recognized 


```Android@Tamer~>fastboot devices```


#### It can reboot your device and reboot it into the bootloader or recovery etc

```Android@Tamer~>fastboot reboot```


```Android@Tamer~>fastboot reboot bootloader```


```Android@Tamer~>fastboot reboot recovery```


#### Using fastboot to flash a new recovery, system, radio, or kernel etc firmware file. 

```Android@Tamer~>fastboot flash recovery \path\to\MyRecoveryFirmware.img```

#### Using fastboot to erase some partition on the device.
```Android@Tamer~>fastboot erase system`````

#### To wipe system, data, and the cache at the same time (would be used before a new rom most of times)

```Android@Tamer~>fastboot erase system -w```

#### fastboot can be used to reboot your device:

```Android@Tamer~>fastboot reboot```

#### Using fastboot to lock / unlock your bootloader

```Android@Tamer~>fastboot oem lock```


```Android@Tamer~>fastboot oem unlock```

## adb

#### Similar to fastboot, adb also has a devices command which will list the found compatible devices connected

```Android@Tamer~>adb devices```

#### It can also, like fastboot, reboot your device and reboot it into the bootloader or recovery etc

```Android@Tamer~>adb reboot```


```Android@Tamer~>adb reboot bootloader```


```Android@Tamer~>adb reboot recovery```

#### Getting logs for diagnostics

```Android@Tamer~>adb logcat > logcat.txt```

#### Install an application (apk format) from your hard drive to the device

```Android@Tamer~>adb install "C:\path\to\apk.apk"```

#### Using push to move a file or directory from your computer to the device

```Android@Tamer~>adb push C:\path\to\file /path/on/device```

#### Copying a file or directory from your device to your computer

```Android@Tamer~>adb pull /path/on/device C:\path\on\computer```

#### ADB can also be used to access the terminal shell on your device

```Android@Tamer~>adb shell```

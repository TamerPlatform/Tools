## adb

#### Similar to [fastboot](fastboot.md), adb also has a devices command which will list the found compatible devices connected

> **android@tamer~>** `adb devices`

#### It can also, like fastboot, reboot your device and reboot it into the bootloader or recovery etc

> **android@tamer~>** `adb reboot`

> **android@tamer~>** `Android@Tamer~>adb reboot bootloader`

> **android@tamer~>** `adb reboot recovery`

#### Getting logs for diagnostics

> **android@tamer~>** `adb logcat > logcat.txt`

#### Install an application (apk format) from your hard drive to the device

> **android@tamer~>** `adb install "C:\path\to\apk.apk"`

#### Using push to move a file or directory from your computer to the device

> **android@tamer~>** `adb push C:\path\to\file /path/on/device`

#### Copying a file or directory from your device to your computer

> **android@tamer~>** `adb pull /path/on/device C:\path\on\computer`

#### ADB can also be used to access the terminal shell on your device

> **android@tamer~>** `adb shell`

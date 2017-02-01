## Fastboot

If you you need a brief about what is `fastboot` you could read it [here](../Development/ROM\ Development/fastboot.md).

#### To view the list of recognized devices 

> **android@tamer~>** `fastboot devices`

#### To reboot your device or to reboot it particularly into the bootloader or recovery

> **android@tamer~>** `fastboot reboot`

> **android@tamer~>** `fastboot reboot bootloader`

> **android@tamer~>** `fastboot reboot recovery`

#### To flash a new recovery, system, radio, or kernel etc firmware file

> **android@tamer~>** `fastboot flash recovery \path\to\MyRecoveryFirmware.img`

#### To erase some partition on the device

> **android@tamer~>** `fastboot erase system`

#### To wipe system, data, and the cache at the same time (would be used before a new ROM most of times)

> **android@tamer~>** `fastboot erase system -w`

#### To reboot your device:

> **android@tamer~>** `fastboot reboot`

#### Using fastboot to lock / unlock your bootloader

> **android@tamer~>** `fastboot oem lock`

> **android@tamer~>** `fastboot oem unlock`

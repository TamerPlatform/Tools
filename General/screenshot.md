# How to take screenshots of device

Taking screenshots is very important part of any process be it development or anything else. ADB provides a way to take screenshot via screencap but then there is a specific command set that needs to be followed.

Here we have created added another feature in our [adb shim called as adb_wrapper](https://github.com/AndroidTamer/adb_wrapper/) 

now to take screenshot all you need to do is 

```
android@tamer ~> adb screenshot savefile.png
```

__Note:__ the screenshot output is always `.png` so keep that in mind

Like all other command this command can also be used with multidevice setup

```
android@tamer ~> adb geny screenshot geny_shot.png
```

This will take a screenshot of geny machine and will save it as `geny_shot.png`


## APKTool

### Overview

A tool for reverse engineering 3rd party, closed, binary Android apps. It can decode resources to nearly original form and rebuild them after making some modifications; it makes possible to debug smali code step by step. Also it makes working with an app easier because of project-like file structure and automation of some repetitive tasks like building apk, etc.

It is NOT intended for piracy and other non-legal uses. It could be used for localizing, adding some features or support for custom platforms, analyzing applications and much more.

### Features

- Disassembling resources to nearly original form (including `resources.arsc`, `classes.dex`, `9.png.` and `XMLs`)
- Rebuilding decoded resources back to binary APK/JAR
- Organizing and handling APKs that depend on framework resources
- Smali Debugging
- Helping with repetitive tasks

### Authors

- [Connor Tumbleson](https://github.com/iBotPeaches) - Current Maintainer
- [Ryszard Wiśniewski](https://github.com/brutall) - Original Creator

### APKTool on AndroidTamer

<center>
![image](/images/APKTool.jpg)
</center>

### Cheatsheet

- To decompile an APK:
  `apktool d file.apk`
- To decompile an APK and put it under a specific folder name:
  `apktool d file.apk folder`
- To compile the smali code to APK:
  `apktool b folder`

### External Links
- [Official Website](http://ibotpeaches.github.io/Apktool/)
- [Official Documentation](http://ibotpeaches.github.io/Apktool/documentation/)
- [XDA Thread](http://forum.xda-developers.com/showthread.php?t=1755243)
- [Gitter #apktool](https://gitter.im/iBotPeaches/Apktool)
- [Freenode #apktool](http://webchat.freenode.net/?channels=apktool)

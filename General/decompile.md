# Decompiling Application

### how to decompile application in AndroidTamer

Android Tamer has all the tools required to perform the application analysis manually however we have gone one step ahead and added more automation to reduce the time spend on remembering command and running them.

To decompile application in AndroidTamer

```android@tamer ~> apk2java <apk>```

__NOTE:__ the source code for [apk2java are here]

This will give you a folder structure as shown below

![Decompiled APK](/images/decompiled_apk.jpg)

Here ```smali``` folder contains the smali version of the source code
where as `src` folder contains two subfolder `jad` and `jadx` containing source codes decompiled via these two decompilers respectively.

If you are not satisfied with the results you can also refer to the original jar created via enjarify in `jar` folder.

You can launch a text editor in this directory using following command

```
android@tamer ~> geany ./
```

### Can other distributions use it

Yes, glad you asked [follow steps outlined here](repo_configure.md) 


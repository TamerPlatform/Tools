# Basic Development Tools

AndroidTamer does not only comprise of offensive tools and scripts for Android security testing, but also frameworks for Android app development. Some development tools which come with AndroidTamer are:
- Android Studio
- Android SDK
- Android AVD Management

### Android-Studio

Android Studio is the official Integrated Development Environment (IDE) for the Android platform. You can code, compile and debug Android apps using Android Studio. Know more about the IDE in its [official website](https://developer.android.com/studio/index.html).

It is by default installed and configured in your terminal path. All you need to do is just type the following command:

```
android@tamer ~> android-studio
```

### Android SDK

Android Software Development Kit (SDK) comes with the Android Studio package. The latest version of Android SDK gets downloaded and installed on the first run of Android Studio. It is a set of development tools used to develop applications for Android platform. The Android SDK includes the following:

- Required libraries
- Debugger
- An emulator
- Relevant documentation for the Android application program interfaces (APIs)
- Sample source code
- Tutorials for the Android OS

Each version of Android has its own SDK. It provides the ability to create an application for particular version(s) of Android. For example, if you have installed SDK for Android Nougat, you can create Android apps for that version. Similarly, you need to install the SDK of all the versions for which you want to create the Android apps.

Android SDK Manager allows you to install, manage and delete SDKs. In AndroidTamer, it is installed on the path `/opt/Arsenal/android-sdk-linux`. You could start the Android SDK Manager with ease using the following command:

```
android@tamer ~> android sdk
```

### Android AVD Management

An Android Virtual Device (AVD) is an emulator configuration that allows developers to test the application by simulating the real device capabilities. Not only does it help with compatibility testing after the Android app development but also helps in dynamic analysis of the apps.

As AndroidTamer is a virtual machine environment hence **its recommended to run emulator only when you have alocated more then 2 GB of RAM** to the virtual machine.

To directly launch AVD manager type following command:

```
android@tamer ~> android avd
```

### Develop an Application

#### Launch Android Studio

A custom bash script named `studio.sh` is packaged with AndroidTamer to help the CLI lovers. The script is configured on the terminal path and is located at `/opt/Arsenal/android-studio/bin/studio.sh`. Instead of manually clicking Android Studio in the `Development` drop-down sublist, it allows the user to launch Android Studio using the terminal with just one command. This script basically checks if JRE, JDK and IDE are properly installed and configured. If anyone is failing then the script doesnt invoke Android Studio and displays the error.

To launch Android Studio from terminal, type the following command:

```
android@tamer ~> studio.sh
```

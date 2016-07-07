# Emulator

Android Tamer by default comes with Android SDK. The emulator images are provided by Google, however users has to accept the license agreement to get those images. Hence it is on the user's behalf to accept the license agreement, and then download an AVD for themselves.

Here are the steps how to download, setup and launch an Android emulator instance.

> At this point Intel x86 emulator might not work due to limitation of AndroidTamer running inside a VM.

We first need to launch Android SDK Manager either via Tamer Menu or by simply from the terminal using the following command:

`android@tamer ~> android sdk`

This will launch SDK and then we need to select a image that we want to download. As shown below, Android 4.4.2 (API 19) ARM image along with Google API has been selected.

<center>
![SDK Lauched](/images/emulator_install/1-sdk.jpg)
</center>

When you select install you will have to **accept the license agreement**.

<center>
![Accept License](/images/emulator_install/2-accept_license.jpg)
</center>

Then the SDK manager automatically downloads, installs and configures the selected Emulator.

<center>
![SDK Lauched](/images/emulator_install/3-loaded.jpg)
</center>

Once the installations successfully finish, the SDK screen should reflect the status as shown below.

<center>
![SDK Lauched](/images/emulator_install/4-status_installed.jpg)
</center>

Once the desired SDK images are installed we will now start the Android AVD manager.

Either by going to menu and selecting 'Android AVD Manager' or directly via commandline

`android@tamer ~> android avd`

In the window you will have to select **Create** and then fill the details as suggested below.

<center>
![SDK Lauched](/images/emulator_install/5-avd_options.jpg)
</center>

Once the options are set, select "OK" which results in AVD being created. When VM is sucessfully created you will get the message as shown below.

<center>
![SDK Lauched](/images/emulator_install/6-vm_created.jpg)
</center>

We can now launch the VM by selecting the entry and clicking on "**Start**"

<center>
![SDK Lauched](/images/emulator_install/7-launch_vm.jpg)
</center>

As shown below a VM will be launched and we can see log via pidcat and adb detects the vm as an emulator.

<center>
![SDK Lauched](/images/emulator_install/8-emulator_running.jpg)
</center>
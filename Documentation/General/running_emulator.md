# Emulator

Android Tamer by default comes with SDK however as emulator images are provided by google once a user has accepted the license agreement hence We are not accepting the agreement on user's behalf and rather user is required to download a AVD for themself.

Here are the steps how to download, setup and launch an android emulator instance.

**P.S.**: At this point intel x86 emualtor might not work due to limitation of androidtamer running inside a VM.

We first need to launch Android SDK Manager either via Tamer Menu or by following command

`android@tamer ~> android sdk`

This will launch SDK and then we need to select a image that we want to download. As shown below i have selected 4.4.2 (API 19) arm image along with google API.

![SDK Lauched](/images/emulator_install/1-sdk.jpg)

When you select install you will have to accept the license aggreement.

![Accept License](/images/emulator_install/2-accept_license.jpg)

This will then Follow by SDK manager performing a download and install + configuration of Emulator.

![SDK Lauched](/images/emulator_install/3-loaded.jpg)

Once installations finishes, the SDK screen should reflect the status as shown below.

![SDK Lauched](/images/emulator_install/4-status_installed.jpg)

Once the desired SDK images are installed we will now start the android AVD manager.

either by going to menu and selecting 'Android AVD Manager' or directly via commandline

`android@tamer ~> android avd`

In the window you will have to select Create and thne fill the details as shown and suggested below.

![SDK Lauched](/images/emulator_install/5-avd_options.jpg)

Once the options are set we select "OK" which results in AVD being created. When VM is sucessfully created you will get the message as listed below.

![SDK Lauched](/images/emulator_install/6-vm_created.jpg)

We can now launch the VM by selecting the entry and clicking on "START"

![SDK Lauched](/images/emulator_install/7-launch_vm.jpg)

As shown below a VM will be launched and we can see log via pidcat and adb is also detecting the vm as an emulator.

![SDK Lauched](/images/emulator_install/8-emulator_running.jpg)

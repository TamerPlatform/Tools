# Drozer

### Overview

drozer (formerly Mercury) is the leading security testing framework for Android.

drozer allows you to search for security vulnerabilities in apps and devices by assuming the role of an app and interacting with the Dalvik VM, other apps' IPC endpoints and the underlying OS.

drozer provides tools to help you use, share and understand public Android exploits. It helps you to deploy a drozer Agent to a device through exploitation or social engineering. Using weasel (MWR's advanced exploitation payload) drozer is able to maximise the permissions available to it by installing a full agent, injecting a limited agent into a running process, or connecting a reverse shell to act as a Remote Access Tool (RAT).

**Source:** [https://github.com/mwrlabs/drozer](https://github.com/mwrlabs/drozer)

### How to use with AndroidTamer

Drozer is already pre configured within AndroidTamer. However there are some steps required before starting drozer.

1. We need to start device / emulator and connect that to the AndroidTamer Machine.
2. Once device connected we need to install a drozer_client APK.
3. Download the [client APK from the official website](https://labs.mwrinfosecurity.com/system/assets/934/original/drozer-agent-2.3.4.apk)<br>
`android@tamer ~/Downloads> adb install ./drozer-agent-2.3.4.apk`
4. Once device shows that the apk is installed then we are ready to use drozer
5. To start using drozer type following <br>
```android@tamer ~> drozer_start <device_name>```


### Dynamic Assessment via Drozer

Drozer at this point doesn't provide html/xml style reporting, instead the report output is directly provided to the console.

AndroidTamer has a build in script which will automatically run all the modules that are available in drozer and will give you a textual output on screen. Its advised to save the output in a text file for further / delayed analysis.

```android@tamer ~> drozer_check <package name> <device_name>```


![drozer](/images/drozer_check.jpg)


### Known issues

__Question:__ Why am I getting error "Magic number incorrect" ?

__Answer:__
You are running drozer on a x86 machine or genymotion emulator. There is a known issue and that's the reason why you get those errors.
[Refer here](https://github.com/mwrlabs/drozer/issues/203)

__Question:__ Drozer caused errors

__Answer:__ 
If you find error in drozer please [raise an issue here](https://github.com/mwrlabs/drozer/issues/). However, if you feel issue is with the automation please [raise an issue here](https://github.com/AndroidTamer/Tools_Repository/issues).

### External Links
- [AndroidTamer drozer repository (Github)](https://github.com/AndroidTamer/drozer)
- [Original Github repository](https://github.com/mwrlabs/drozer)
- [Official Webpage](https://labs.mwrinfosecurity.com/tools/drozer/)
- [Drozer User Guide](https://labs.mwrinfosecurity.com/assets/BlogFiles/mwri-drozer-user-guide-2015-03-23.pdf)
# AndroidTamer Tools

This repository hosts all the documentation regarding various tools available within AndroidTamer

### Overview

Android Tamer is a Virtual / Live Platform for Android Security Professionals.

This environment allows people to work on large array of Android Security related tasks ranging from Malware Analysis, Penetration Testing and Reverse Engineering.

### Installation

AndroidTamer comes as an `.ova` file. Double click it and Virtual Box adds the VM automatically.

AndroidTamer is pre-configured with 1 GB of Base Memory (RAM), however 1.5 GB is recommended. Its also configured with two network adapters:

- NAT - to get updates and access Internet
- Host-Only Adapter - to access the virtual Android devices in Genymotion

### Release Notes

The latest version of Android Tamer is compatible with both VirtualBox and VMware.

The history of compatibility of previous releases:

- **Ver 1** : Virtualbox
- **Ver 2** : VMware player
- **Ver 3** : Not released
- **Ver 4** : Compatibile with both

A short introduction to AndroidTamer is listed below.

<center>
![Slides for AndroidTamer](http://www.slideshare.net/anantshri/android-tamer-virtual-machine-for-android-security-professionals)
</center>

### Packages and Scripts

Name | x86 | x64
--- | --- | ---
androidtamer-adb | &#10004; | &#10004;
andbug | &#x2718; | &#10004;
apk2java | &#10004; | &#10004;
apktool | &#10004; | &#10004;
bytecode-viewer | &#x2718; | &#10004;
burpsuite-free | &#10004; | &#10004;
classyshark | &#10004; | &#10004;
dex2jar | &#10004; | &#10004;
drozer | &#10004; | &#10004;
drozer_checks | &#10004; | &#10004;
enjarify | &#10004; | &#10004;
jad | &#10004; | &#10004;
jadx | &#10004; | &#10004;
jd-gui | &#10004; | &#10004;
MobSF | &#10004; | &#10004;
python packages | | 
- python-cement | &#10004; | &#10004;
- python-configparser | &#10004; | &#10004;
- python-dateutil | &#10004; | &#10004;
- python-flask | &#10004; | &#10004;
- python-flask-restless | &#10004; | &#10004;
- python-frida | &#x2718; | &#10004;
- python-graphviz | &#10004; | &#10004;
- python-mimeparse | &#10004; | &#10004;
- python-mimerender | &#10004; | &#10004;
- python-prompt-toolkit | &#10004; | &#10004;
- python-psutil | &#x2718; | &#10004;
- python-pyfiglet | &#10004; | &#10004;
- python-pygments | &#10004; | &#10004;
- python-six | &#10004; | &#10004;
- python-wcwidth | &#10004; | &#10004;
- python-xhtml2pdf | &#10004; | &#10004;
smali | &#10004; | &#10004;
sslscan | &#10004; | &#10004;
vboxmanage | &#10004; | &#10004;
zaproxy | &#10004; | &#10004;

### Support

AndroidTamer project is based on two things.

- Latest vulnerabilities and exploitation methods for Android
- Suggestions from users

This project was actually an initiative of Anant Shrivastava. Feel free to send your suggestions / issues directly to Anant at [anant@anantshri.info](mailto:anant@anantshri.info)

### Learn Android Security

Have a look at the below URLs.

- [Learn Android Security](https://androidtamer.com/learn_android_security)
- [Awesome Android Security](https://github.com/ashishb/android-security-awesome)

### PGP Key

You can get PGP public key at: [https://androidtamer.com/repo.gpg.key](https://androidtamer.com/repo.gpg.key)

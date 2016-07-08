# AndroidTamer Tools

This repository hosts all the documentation regarding various tools available within AndroidTamer

### Overview

Android Tamer is a Virtual / Live Platform for Android Security Professionals.

This environment allows people to work on large array of Android Security related tasks ranging from Malware Analysis, Penetration Testing and Reverse Engineering.

### Installation

AndroidTamer comes as an `.ova` file. Double click it and Virtual Box adds the VM automatically.

AndroidTamer is pre-configured with 1 GB of Base Memory (RAM), however 1.5 or more GB is recommended. (the more the merrier)

### Release Notes

AndroidTamer has Debian 8 as its base machine. The are a many reasons why Debian was chosen instead of Ubuntu. It comes with some custom scripts which simplifies the life of Android pentester.

The credentials for AndroidTamer is :

> ***Username***: android

> ***Password***: tamer

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
androidtamer-adb: [multidevice](/General/multi_devices) & [screenshot](/General/screenshot.md) | &#10004; | &#10004;
andbug | &#x2718; | &#10004;
[apk2java](/General/decompile.md) | &#10004; | &#10004;
[apktool](/Security Assessment/Manual Analysis/APKTool.md) | &#10004; | &#10004;
burpsuite-free | &#10004; | &#10004;
bytecode-viewer | &#x2718; | &#10004;
classyshark | &#10004; | &#10004;
dex2jar | &#10004; | &#10004;
dextra | &#x2718; | &#10004;
droid-ff | &#10004; | &#10004;
drozer | &#10004; | &#10004;
[drozer_checks](/Security Assessment/Automated Analysis/drozer.md) | &#10004; | &#10004;
enjarify | &#10004; | &#10004;
imgtool | &#10004; | &#10004;
j0din3 | &#x2718; | &#10004;
jaadas | &#10004; | &#10004;
jad | &#10004; | &#10004;
jadx | &#10004; | &#10004;
jd-gui | &#10004; | &#10004;
[MobSF](/Security Assessment/Automated Analysis/MobSF.md) | &#10004; | &#10004;
[Python packages](/General/python_packages.md) | | 
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
rubygem-dex-oracle | &#10004; | &#10004;
rubygem-rubyzip | &#10004; | &#10004;
simplify | &#10004; | &#10004;
smali | &#10004; | &#10004;
spflashtool | &#x2718; | &#10004;
sslscan | &#10004; | &#10004;
vboxmanage | &#10004; | &#10004;
yadd-dumper | &#x2718; | &#10004;
zaproxy | &#10004; | &#10004;

### Importing in VMWare Player / Fusion / Workstation

AndroidTamer is created on VirtualBox and we officially support Virtualbox however its possible to install / import the OVA in VMWare products also.

When am import is initiated you may encounter an error message as shown below.

<center>
![Error Linux](/images/vmware_import_error_linux.jpg "Error Message on Linux") ![Mac Linux](/images/vmware_import_error_mac.jpg "Error Message on Mac")
</center>

Its recommended to click on retry and VM should import easily.

Once inside VM the VM might not auto resize to screen size in that case please install **open-vm-tools-desktop** package and restart the VM and auto resize should start working.

![VMWare Tools](/images/install_open_vm_tools.jpg)

Command: 
```bash
sudo apt-get install open-vm-tools-desktop
```

### Support

AndroidTamer project is based on two things.

- Latest vulnerabilities and exploitation methods for Android
- Suggestions from users

This project was actually an initiative of Anant Shrivastava. However at this point a group of individuals contribute to this Project. Feel free to send your suggestions / issues directly to Anant at [anant@anantshri.info](mailto:anant@anantshri.info)

### Learn Android Security

Have a look at the below URLs.

- [Learn Android Security](https://androidtamer.com/learn_android_security)
- [Awesome Android Security](https://github.com/ashishb/android-security-awesome)

### PGP Key

You can get PGP public key at: [https://androidtamer.com/repo.gpg.key](https://androidtamer.com/repo.gpg.key)

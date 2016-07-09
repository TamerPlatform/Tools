# AndroidTamer Tools

This repository hosts all the documentation regarding various tools available within AndroidTamer

### Overview

Android Tamer is a Virtual / Live Platform for Android Security Professionals.

This environment allows people to work on large array of Android Security related tasks ranging from Malware Analysis, Penetration Testing and Reverse Engineering.

A short introduction to AndroidTamer is listed below.

<center>
![Slides for AndroidTamer](http://www.slideshare.net/anantshri/android-tamer-virtual-machine-for-android-security-professionals)
</center>

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

### Packages and Scripts

AndroidTamer comes pre-installed with many development and security pentesting tools. It is also beefed up with some custom scripts to automate common tasks. You could find a detailed description about the packages and scripts installed in AndroidTamer [here](/General/packages.md).

Check the [package list](http://repo.androidtamer.com/packagelist.html) to view the list of tools available in AndroidTamer.

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

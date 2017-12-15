## Insecure Data Storage - Part 4

We have now arrived at the last part in Insecure Data Storage challenge series. If you click on  **Insecure Data Storage - Part 4**, you would see the following:

<center>![Insecure Data Storage 4a](/images/vuln_apps/DIVA/Challenge_6a.png)</center>

Let's enter credentials as we did in [Challenge 3](/Training/DIVA/03_Insecure_Data_Storage_P1.md), [Challenge 4](/Training/DIVA/04_Insecure_Data_Storage_P2.md) and [Challenge 5](/Training/DIVA/05_Insecure_Data_Storage_P3.md).

<center>![Insecure Data Storage 4b](/images/vuln_apps/DIVA/Challenge_6b.png)</center>

We got a message stating that *3rd party credentials saved successfully*.

Let's check the pseudocode of this activity with the help of [dex2jar and jd-gui](/Training/DIVA/02_Hardcoding_Issues.md). We can find that the code for this challenge is stored in `InsecureDataStorage4Activity.class`.

<center>![Insecure Data Storage 4c](/images/vuln_apps/DIVA/Challenge_6c.png)</center>

Something looks interesting. The source code creates an object to write files to the external storage. Then it gets the credentials from the user and stores that at `/.uinfo.txt`.

> **Here, `/` doesn't mean the root folder. Why ?**
>
> As you can see from the source code that an object (`localObject2`) which utilizes external storage is created. Then that object is used to write the data to the file located at **root directory in external storage.**

In Android, external storage is mounted at `/sdcard/` location. So `/.uinfo.txt` refers to the actual location `/sdcard/.uinfo.txt`.

Let's connect to the emulator or physical device using adb and check if the file `.uinfo.txt` is present at the location.

<center>![Insecure Data Storage 4d](/images/vuln_apps/DIVA/Challenge_6d.png)</center>

Let's check its contents.

<center>![Insecure Data Storage 4e](/images/vuln_apps/DIVA/Challenge_6e.png)</center>

Voila ! We cracked the challenge.

> **NOTE:** The file is prepended with a dot (`.`) which means it is hidden. To view all the files (including hidden) always use the command `ls -a`.

### Takeaway

- When you are running an emulator, make sure that you have mounted a virtual SD card. If not, we might miss out some notable actions of Android apps.
- *Files written to the external storage could be read by other apps which have `READ_EXTERNAL_STORAGE` permission.*
- When you are pentesting an Android app, always execute `ls -la` to see files in a directory. It lets you see which files have been recently modified and shows the files which are intentionally hidden.

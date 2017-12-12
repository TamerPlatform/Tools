## Insecure Data Storage - Part 1

When you click on **Insecure Data Storage - Part 1**, you would see the following screen.

<center>![Insecure Data Storage 1a](/images/vuln_apps/DIVA/Challenge_3a.png)</center>

It resembles a password manager, which stores user's credentials. Let's enter the credentials.

<center>![Insecure Data Storage 1b](/images/vuln_apps/DIVA/Challenge_3b.png)</center>

All the data of Android apps are stored under the location `/data/data/`. The Android OS creates unique directories for each app. The name of the directory is the same as the package name. For DIVA app, the package name is: **`jakhar.aseem.diva`**.

Use Android Debug Bridge (`adb`) tool to connect to the emulator or physical device in which the app is running. Execute `adb shell`.

> **NOTE**: When you connect to an emulator, it gives you `root` access. If you are using a physical device, make sure it is rooted. *If not, you cannot access `/data/data` directory*.

Move to the directory where are the DIVA app's data is stored. Execute `cd /data/data/jakhar.aseem.diva/`.

<center>![Insecure Data Storage 1c](/images/vuln_apps/DIVA/Challenge_3c.png)</center>

Let's check if any file was recently modified. Execute the command `ls -la`.

<center>![Insecure Data Storage 1d](/images/vuln_apps/DIVA/Challenge_3d.png)</center>

Voila ! We could see that the folder `shared_prefs` was recently modified.

**Shared Preference** is one among the different ways of storing data of an Android application. Shared Preferences allow you to save and retrieve data in the form of *key, value pair*.

Listing the files inside the `shared_prefs` directory, we can see a file `jakhar.aseem.diva_preferences.xml`.

<center>![Insecure Data Storage 1e](/images/vuln_apps/DIVA/Challenge_3e.png)</center>

Let's look at the contents of the file. Execute `cat jakhar.aseem.diva_preferences.xml`.

<center>![Insecure Data Storage 1f](/images/vuln_apps/DIVA/Challenge_3f.png)</center>

Finally, we got the credentials.

### Takeaway

- Emulators allow you to start the `adb shell` as `root` user, whereas you have to manually root the physical device to get `root` level permissions.
- The data of an Android application is stored at the location `/data/data/<package_name>`. No app can access other app's data. Only the respective app and `root` user could access the contents in the directory.
- **Shared Preference** is a way to store data of an Android app in the form of value, key pair. It stores these values under `/data/data/<package_name>/shared_prefs` directory.

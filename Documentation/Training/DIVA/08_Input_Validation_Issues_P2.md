## Input Validation Issues - Part 2

This challenge is a bit different from the [previous one](/Training/DIVA/07_Input_Validation_Issues_P1.md).

<center>![Input Validation Issues 2a](/images/vuln_apps/DIVA/Challenge_8a.png)</center>

Let's enter a proper URL.

<center>![Input Validation Issues 2b](/images/vuln_apps/DIVA/Challenge_8b.png)</center>

When you click on `View`, the website is opened at the lower half of the app. Let's remove the scheme `https://` from the URL.

<center>![Input Validation Issues 2c](/images/vuln_apps/DIVA/Challenge_8c.png)</center>

There is a blank screen. We can understand that the app is not appending the scheme `http://` or `https://` to the input. Let's try again with some random input.

<center>![Input Validation Issues 2d](/images/vuln_apps/DIVA/Challenge_8d.png)</center>

We get an error `net::ERR_UNKNOWN_URL_SCHEME`. So the app completely depends on the user input and runs that irrespective of the entered scheme.

Android browsers also accepts another scheme `file://`. This scheme is used to view the contents of files inside the filesystem. Let's give it a try.

<center>![Input Validation Issues 2e](/images/vuln_apps/DIVA/Challenge_8e.png)</center>

Positive results! The app accepts the `file://` scheme. Now let's try to access a [previous challenge's](/Training/DIVA/06_Insecure_Data_Storage_P4.md) file located at `/sdcard/.uinfo.txt`.

<center>![Input Validation Issues 2f](/images/vuln_apps/DIVA/Challenge_8f.png)</center>

Voila ! We cracked the challenge.

### Takeaway

- Whenever an app asks for a URL, try providing `file://` scheme. If it renders the contents of a file at a known location, this is a vulnerability

## Insecure Logging

When you click on the **`Insecure Logging`** option, you will be welcomed by the following screen.

![Insecure Logging 1](/images/vuln_apps/DIVA/Challenge_1a.png "DIVA Challenges 1a")

The screen is pretty simple. It asks for credit card number.

Enter some random credit card number and click `Check out`. You would notice a generic error message: *An error occured. Please try again later.*

![Insecure Logging 1](/images/vuln_apps/DIVA/Challenge_1b.png "DIVA Challenges 1b")

Everything seems normal.

Lets see if the application has logged anything. We can use Android's inbuilt commandline tool - **logcat** - to view the logs.

Execute the command `adb shell logcat`. (Please ensure that the device/emulator is connected to adb)

![Insecure Logging 1](/images/vuln_apps/DIVA/Challenge_1c.png "DIVA Challenges 1c")

It is clear that the app is logging the sensitive information (Credit card number). These logs are accessible by other apps which has read permission to logs.

### Takeaway:

- **Logcat** is a command-line tool that dumps a log of system messages, including stack traces when the device throws an error and messages that you have written from your app with the Log class.
- Check for logs to get more information on how the target app handles inputs / what the android app logs

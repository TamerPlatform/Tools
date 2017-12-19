## Access Control Issues - Part 1

When we click on **Access Control Issues - Part 1**, apart from the *Objective* and *Hint* you would see a single button - **VIEW API CREDENTIALS**

<center>![Access Control Issues 1a](/images/vuln_apps/DIVA/Challenge_9a.png)</center>

When you click on the button, an activity pops up to display the so called API credentials.

<center>![Access Control Issues 1b](/images/vuln_apps/DIVA/Challenge_9b.png)</center>

In Android, an activity represents a single screen with a user interface (just like window or frame of Java). Generally speaking, anything which the user could touch and interact is called activity. Each activity has it's own unique name.

Now, we are left with one question - *How to find the name of the activity which just popped up?*

The answer is logs. Whenever an activity is launched, the name of the activity is logged. Let's check the logs using `adb shell logcat` command.

<center>![Access Control Issues 1c](/images/vuln_apps/DIVA/Challenge_9c.png)</center>

We found the name of the recently launched activity - `jakhar.aseem.diva/.APICredsActivity`.

> **NOTE:** The name of any activity is always appended with the package name. This is done so that there is no confusion when an activity is invoked. Activities of 2 apps can have same name, but the package names cannot be the same.

In Android, we have a utility `am` (Activity Manager) which allows us to manage activities.

Let's check if the activity could be invoked externally. Use the command: `adb shell am start -n jakhar.aseem.diva/.APICredsActivity`

<center>![Access Control Issues 1d](/images/vuln_apps/DIVA/Challenge_9d.png)</center>

When we look at the emulator / device, we could see the activity that displays API Credentials pops up.

<center>![Access Control Issues 1e](/images/vuln_apps/DIVA/Challenge_9e.png)</center>

This activity could be invoked externally, which means other apps on the device could also invoke it without explicit permissions.

**How to find if the activity was invoked externally and through DIVA app ?**

When you press the *Overview* button, you could see how the activity was launched. In the first case, DIVA app had invoked the activity, but in second it was externally invoked.

<center>![Access Control Issues 1y](/images/vuln_apps/DIVA/Challenge_9y.png) ![Access Control Issues 1z](/images/vuln_apps/DIVA/Challenge_9z.png)</center>

### Takeaway

- Activity represents a screen with a user interface
- Whenever an activity is launched, it is logged and could be viewed using `adb shell logcat` command
- Android comes with activity manager (`am`) which can be used to manage the activities
- Command to start an activity: `adb shell am start -n <package_name>/<activity_name>`
  - `am` - activity manager
  - `start` - start the activity
  - `-n` - name of the activity
- Clicking the overview button would help us understand what launched the activity

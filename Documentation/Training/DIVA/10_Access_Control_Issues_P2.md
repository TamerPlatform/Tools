## Access Control Issues - Part 2

When we click on **Access Control Issues - Part 2**, we would stumble upon an activity with two radio buttons ***Register Now*** and ***Already Registered*** and a single button - ***VIEW TVEETER API CREDENTIALS***

<center>![Access Control Issues 2a](/images/vuln_apps/DIVA/Challenge_10a.png)</center>

Let's click on ***Register Now*** and then click ***View Tveeter API Credentials***. It asks us to enter a PIN.

<center>![Access Control Issues 2b](/images/vuln_apps/DIVA/Challenge_10b.png)</center>

On entering some random PIN, we get a toast message - *Invalid PIN. Please try again.*

<center>![Access Control Issues 2c](/images/vuln_apps/DIVA/Challenge_10c.png)</center>

The logs (accessed by `adb shell logcat`) show that the `APICreds2Activity` is displayed when you clicked the button.

<center>![Access Control Issues 2d](/images/vuln_apps/DIVA/Challenge_10d.png)</center>

Let's go back and select ***Already Registered*** radio button. We can see the following:

<center>![Access Control Issues 2e](/images/vuln_apps/DIVA/Challenge_10e.png)</center>

Having a look again at the logs shows the following:

<center>![Access Control Issues 2f](/images/vuln_apps/DIVA/Challenge_10f.png)</center>

In both the above cases, `APICreds2Activity` activity is invoked. So there might be some logic in the app which decides the content of the activity.

Let's [decompile the app](/General/decompile.md) using `apktool` using the command `apktool d jakhar.aseem.diva-1.apk`. On checking the *AndroidManifest.xml*, we see the following:

<center>![Access Control Issues 2g](/images/vuln_apps/DIVA/Challenge_10g.png)</center>

We can see that there is an activity `jakhar.aseem.diva.APICreds2Activity` defined along with an *intent-filter*.

Before cracking the challenge, let's understand the basics:

*Activity* represents a screen with a user interface. All the activites should be declared in *AndroidManifest.xml* - which turns out to be a binary XML file in the apk file. You can't just use an editor to view the file. You have to decompile the apk file using tools like `apktool` to get a readable version of the file.

*Intents* are message objects in Android system. It allows the communication of two or more apps. An *intent-filter* of an app specifies the type of intents it accepts based on the intent's action, data, and category. When an *intent-filter* is used, the activity is exported by default, i.e. *any other component could invoke the activity*.

Back to the challenge.

We assumed that there might be some internal logic. Let's look at the source code with the help of [Dex2Jar and JD-gui](/Training/DIVA/02_Hardcoding_Issues.md). On opening the *APICreds2Activity.class* file, we can see that there is a check on the string (with ID `2131099686`).

<center>![Access Control Issues 2h](/images/vuln_apps/DIVA/Challenge_10h.png)</center>

Here [`getBooleanExtra()`](https://developer.android.com/reference/android/content/Intent.html#getBooleanExtra(java.lang.String,%20boolean)) is used. If the *inverse of the function's result* is true, then the API keys are displayed.

**How to get the string using it's ID ?**

When you use `dex2jar` and `jd-gui`, it gives you a pseudo-code. In this the string and some other resources are generally stored in *R.class*. On searching the file for the ID `2131099686` we can see that it denotes the string ID *chk_pin*.

<center>![Access Control Issues 2i](/images/vuln_apps/DIVA/Challenge_10i.png)</center>

To get the value of *chk_pin*, open **`/res/values/strings.xml`** in the source code and search for the ID.

<center>![Access Control Issues 2j](/images/vuln_apps/DIVA/Challenge_10j.png)</center>

We can use the activity manager (`am`) to invoke the activity with extra Boolean, with the command: `adb shell am start -n jakhar.aseem.diva/.APICreds2Activity -a jakhar.aseem.diva.action.VIEW_CREDS2 --ez check_pin false`

<center>![Access Control Issues 2k](/images/vuln_apps/DIVA/Challenge_10k.png)</center>

Voila, we invoked the activity with the required action.

<center>![Access Control Issues 2l](/images/vuln_apps/DIVA/Challenge_10l.png)</center>

Challenge cracked !

### Takeaway

- *Activity* represents a screen with a user interface
- Information about all the activites are declared in *AndroidManifest.xml*
- *Intents* are message objects
- *intent-filter* specifies the type of intents it accepts. If a activity uses this, then it is exported by default.

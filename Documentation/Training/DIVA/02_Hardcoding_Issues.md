## Hardcoding Issues

When you look at the second challenge, the objective says *to find out what is hardcoded and where*

![Hardcoded Credentials 1](/images/vuln_apps/DIVA/Challenge_2a.png)

There are different ways to check the hardcoded values in an Android app, but most popular method is to [decompile the APK file](/General/decompile.md) and look at the pseudo-source code.

Before directly jumping into decompilation tools, lets learn a few basics.

APK is a package file format used by Android operating system. One could view the contents of the APK file by just unzipping it. Android apps are coded in Java, but when you compile the app using Android Studio, the java code is converted to Dalvik bytecode instead of Java bytecode. All the Java code is collectively compiled into a single Dalvik bytecode file called `classes.dex`. Inorder to view the code of an app, we have to decompile the `classes.dex` file.

Let's start hunting for the hardcoded value.

Right click the apk file and click `Extract Here` option to unzip the file.

![Hardcoded Credentials 2](/images/vuln_apps/DIVA/Challenge_2b.png)

Now the contents will be in the directory `jakhar.aseem.diva-1.apk_FILES`. (*It may differ in your case as the folder is created as per the apk file's name.*) Enter the folder and you can see a few folders and files.

![Hardcoded Credentials 3](/images/vuln_apps/DIVA/Challenge_2c.png)

As mentioned before, to view the code we have to decompile `classes.dex` file. We can use a tool called **`dex2jar`**. It converts Android `.dex` file to Java `.jar` file. Execute **`d2j-dex2jar.sh classes.dex`**. The command creates a new file `classes-dex2jar.jar`

![Hardcoded Credentials 4](/images/vuln_apps/DIVA/Challenge_2d.png)

Now we can use a Java decompiler to view the code in the created `.jar` file. Execute **`jd-gui classes-dex2jar.jar`**. This command create a GUI window and displays the Java pseudo-code of the `classes-dex2jar.jar` file. From the name of the challenge *we understand that its class name would be something like HardcodeActivity.class*. Click on the class file. On viewing the code, it is clearly visible that the app checks for the value **`vendorsecretkey`**.

![Hardcoded Credentials 5](/images/vuln_apps/DIVA/Challenge_2e.png)

Type the key in the Android app.

![Hardcoded Credentials 6](/images/vuln_apps/DIVA/Challenge_2f.png)

### Takeaway:

- APK is a file packaging format and could be unzipped
- Java gets compiled to Dalvik bytecode when you build an app
- **`dex2jar`** - converts the `classes.dex` file to `.jar` file
- **`jd-gui`** - Java decompiler which can be used to decompile `.jar` files and show the pseudo-code contained in them.

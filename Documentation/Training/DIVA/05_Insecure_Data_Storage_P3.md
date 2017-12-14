## Insecure Data Storage - Part 3

When you click on **Insecure Data Storage - Part 3**, you will be greeted by the following screen:

<center>![Insecure Data Storage 3a](/images/vuln_apps/DIVA/Challenge_5a.png)</center>

It's view is similar to [Challenge 3](/Training/DIVA/03_Insecure_Data_Storage_P1.md) and [Challenge 4](/Training/DIVA/04_Insecure_Data_Storage_P2.md). Let's go ahead and enter some credentials.

<center>![Insecure Data Storage 3b](/images/vuln_apps/DIVA/Challenge_5b.png)</center>

We get a message stating that *3rd party credentials saved successfully*.

Let's check the pseudocode of this activity with the help of [dex2jar and jd-gui](/Training/DIVA/02_Hardcoding_Issues.md). We can find that the code for this challenge is stored in `InsecureDataStorage3Activity.class`.

<center>![Insecure Data Storage 3c](/images/vuln_apps/DIVA/Challenge_5c.png)</center>

After looking at the code, we can understand that the app creates a temporary file whose name starts with `uinfo` and then writes the credentials to it. After finishing the task, it prints out the message *3rd party credentials saved successfully*.

In Android, temporary files are stored within the package's directory at `/data/data`. Move to `/data/data/jakhar.aseem.diva` location to see if any temporary file prepended with `uinfo` is present.

<center>![Insecure Data Storage 3d](/images/vuln_apps/DIVA/Challenge_5d.png)</center>

Check the contents of the file.

<center>![Insecure Data Storage 3e](/images/vuln_apps/DIVA/Challenge_5e.png)</center>

We finally got the stored credentials.

### Takeaway

- Temporary files of any app are generally created inside `/data/data/<package>` directory where `<package>` is the unique package name of the app.

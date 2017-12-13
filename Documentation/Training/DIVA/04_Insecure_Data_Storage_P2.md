## Insecure Data Storage - Part 2

When you click on **Insecure Data Storage - Part 2**, you would see the following screen.

<center>![Insecure Data Storage 2a](/images/vuln_apps/DIVA/Challenge_4a.png)</center>

It's view is similar to the previous challenge. Let's enter some credentials.

<center>![Insecure Data Storage 2b](/images/vuln_apps/DIVA/Challenge_4b.png)</center>

We get a message stating that *3rd party credentials saved successfully*.

Let's check the pseudocode of this activity with the help of [dex2jar and jd-gui](/Training/DIVA/02_Hardcoding_Issues.md).

<center>![Insecure Data Storage 2c](/images/vuln_apps/DIVA/Challenge_4c.png)</center>

<center>![Insecure Data Storage 2d](/images/vuln_apps/DIVA/Challenge_4d.png)</center>

From the code we can understand that the activity creates a database **`ids2`** if it doesn't exist. Then creates a table **`myuser`** which holds the strings `user` and `password`. In the function `saveCredentials()`, the app inserts the credentials into the table.

In Android, `sqlite3` database format is used to store data as they are lightweight and runs on low memory devices. The databases of any app are stored in the location `/data/data/<package_name>/databases` where `<package_name>` is the unique name for each Android app.

Connect the emulator or the physical device in which the DIVA app is running. Make sure that you are **root** user. Go to the directory at `/data/data/jakhar.aseem.diva/databases` and check if there is any database with the name `ids2`.

<center>![Insecure Data Storage 2e](/images/vuln_apps/DIVA/Challenge_4e.png)</center>

Then execute the command `sqlite3 ids2` to open the database.

<center>![Insecure Data Storage 2f](/images/vuln_apps/DIVA/Challenge_4f.png)</center>

> **NOTE:** `sqlite3` binary is pre-installed in most of the Android emulators and devices. If your physical device doesn't contain this binary, then try to pull the database to the local system with the help of adb (`adb pull /data/data/jakhar.aseem.databases/ids2`). Then use a local sqlite database management tool like `sqlitebrowser` to view the contents.

Type `.tables` and hit enter to view the tables created.

<center>![Insecure Data Storage 2g](/images/vuln_apps/DIVA/Challenge_4g.png)</center>

Run the query `.schema myuser` to view the schema of the table.

<center>![Insecure Data Storage 2h](/images/vuln_apps/DIVA/Challenge_4h.png)</center>

Run the query `select user, password from myuser` to get all the stored credentials.

<center>![Insecure Data Storage 2i](/images/vuln_apps/DIVA/Challenge_4i.png)</center>

> **NOTE:** Running the query `.dump` will dump all the previously executed queries of a database.
>
> <center>![Insecure Data Storage 2y](/images/vuln_apps/DIVA/Challenge_4y.png)</center>

**Alternate way:**

If we had seen the most recently modified file with the help of `ls -la`, we shall have understood that a file under `databases` folder had been modified. This method didn't require the decompilation of the app to view source code.

<center>![Insecure Data Storage 2z](/images/vuln_apps/DIVA/Challenge_4z.png)</center>

### Takeaway

- Android uses `sqlite3` databases to store the data
- The databases of apps are stored under `/data/data/<package_name>/databases` directory
- Using `sqlite3` in Android we could view (and manage) the data inside the database
  - `.tables` - to view tables
  - `.schema <tablename>` - to view the schema of the table
  - `.dump` - to dump all the executed queries in the database

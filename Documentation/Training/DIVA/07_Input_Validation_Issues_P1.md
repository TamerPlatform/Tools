## Input Validation Issues - Part 1

When you click on  **Input Validation Issues - Part 1**, you would see the following:

<center>![Input Validation Issues 1a](/images/vuln_apps/DIVA/Challenge_7a.png)</center>

There's a pretty long hint for this challenge, but the gist is that there is *no input validation*. Let's provide some input.

<center>![Input Validation Issues 1b](/images/vuln_apps/DIVA/Challenge_7b.png)</center>

No results. You can try with other random inputs, but you will get a error messge `User: (<INPUT>) not found`. But when you type the name of the app: `diva`, you get a different message which includes the details of the account.

<center>![Input Validation Issues 1c](/images/vuln_apps/DIVA/Challenge_7c.png)</center>

Ring any bells ?

In this challenge, the input is taken and checked against some data (most probably present in a database) and displays the credentials if the input user exists. But let's confirm this.

Let's check the pseudocode of this activity with the help of [dex2jar and jd-gui](/Training/DIVA/02_Hardcoding_Issues.md). We can find that the code for this challenge is stored in `SQLInjectionActivity.class`.

From the activity name itself, we can understand that its vulnerable to SQL Injection. Here's how the activity parses the input:

<center>![Input Validation Issues 1d](/images/vuln_apps/DIVA/Challenge_7d.png)</center>

So the query is `SELECT * FROM sqliuser WHERE user = ' + <user_input> + '`.

When you enter some input, say `android`, the SQL query is rendered as `SELECT * FROM sqliuser WHERE user = 'android'`. If you don't understand this query, all it says is *select all the data from the sqliuser table in the database where the user value is android*.

If the value `android` is present in the table `sqliuser`, the condition becomes *TRUE*, else it becomes *FALSE*. In boolean terms, true can be denoted by 1 and false by 0.

To exploit the vulnerability, we have should make the condition true. We can use `OR` operation. The beauty of `OR` is that if any one parameter is true, the result is true.

So our malicious payload will be `' OR 1`. But we have one error, with the above payload. The query becomes: `SELECT * FROM sqliuser WHERE user = '' OR 1 '`. We have a quote (`'`) which ruins the query. We have to comment it out. So we use SQL's comment tags `--`.

Now our malicious payload is `input' OR 1--`. Let's input it.

<center>![Input Validation Issues 1e](/images/vuln_apps/DIVA/Challenge_7e.png)</center>

Voila ! We got the credentials of all the existing users.

The prepended text in the payload doesnt matter. We need not add any text. Even the input `' OR 1--` works.

<center>![Input Validation Issues 1f](/images/vuln_apps/DIVA/Challenge_7f.png)</center>

### Takeaway

- Android uses SQLite databases to store data
- If an app uses a database, always check for input validation issues
- Adding just `'` as input may not create any noticeable errors like those in webapps
- Parts of the payload `' OR 1--`:
  - `'` : closes the open quote in the SQL query
  - `OR` : OR operation, returns *true* if any one condition is true
  - `1` : boolean form of *true*, so that the OR operation finally renders true
  - `--` : comments out the remaining parts of the query
- The payload `' OR 1--` works in most cases where there is one input

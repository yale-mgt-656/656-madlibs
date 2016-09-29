# Madlibs Activity
For this activity, you will use what you've learned about git to work collaboratively as a classroom to fill out a couple Madlibs. The class should be divided into groups responsible for Madlibs stories, nouns, verbs, adjectives, and adverbs.

## How To Setup This Activity

**1) Form a group with your neighbors.**

You should choose one person whose computer you will use. This person will end up registering for GitHub and Cloud9.

**2) Make a Github account if you haven't already got one.**

This should be a personal account for the person whose computer is being used.

**3) Fork the starter repository on Github.**

Forking means to make a copy of the code but attach it to your own Github repository so that you can make changes.
Technically you are "cloning" the starter repo. GitHub calls this "forking" because they add some other
bells and whistles on top. You should see a grey button at the top that says "fork"---that is what you want.

If you need more information, check out [https://help.github.com/articles/fork-a-repo/](https://help.github.com/articles/fork-a-repo/)

**4) Login to [cloud9](https://c9.io/).**

You may have an invite to cloud9 from the instructor. Or, you may already have an account. Once you're in
Cloud9, you'll want to link it to your GitHub account.
Then, create a custom workspace, cloning from your forked repo.

(Of course, you can do all these locally on your computer if you are advanced,
instead of using Cloud9.)

**5) Pick whether you guys will be a story, verb, noun, adjective, or adverb group.**

The instructor may ask you to pick a particular one.
Checkout a new branch with a good name. This will be a command like
```
  git checkout -b kyle-new-verbs
```

Here, I named my branch "kyle-new-verbs". You should name yours something different, no spaces.

**6) Take a look around at the files ***

Familiarize yourself where everything lives. You'll use the shell commands `cd` to change
directories and `ls` to see what is each directory.

**7) Create a new file**

Technically, you can also edit existing files, but that will make our merging harder!
If you want to make a new file of verbs, you might make a file at
`/pos/verbs/my-new-file.js` and it might look like this:

```javascript
module.exports.verbs = [
    'sleep',
    'spit',
    'spin'
];
```

You should choose a name other than "my-new-file.js". You can use the command `nano` to create and edit files, or use the Cloud9 editor.  You may also use the cloud9 editor, or a local text editor you have installed, like [atom](https://atom.io/).

For example `nano pos/verbs/my-new-file.js` will create the file `my-new-file.js` in the directory `pos/verbs`.

**8) Check your code works.**

Assuming you have [node installed](https://nodejs.org/en/), run the following:

```
npm install
./node_modules/.bin/gulp
```

The app is now accessible at `127.0.0.1:3000` in your browser if you're running
locally. If not, you should click "preview" in Cloud9 to see your app.  Ensure
your changes didn't introduce any errors.

**9) Commit your changes and share them**

First, take a look at the status of your work

```
git status
```

It should show what files are new and what files are changed. Now, you want
to add the new files, try the `git add` command. You'll need to supply a file name.

Once you've added your changes to the "staging area", you want to make a commit. This
is a command like

```
git commit -m "Added some verbs for class"
```

Now, push your changes up to GitHub.

```
git push origin BRANCHNAME
```

where `BRANCHNAME` is the name of your branch.

**10) Go to GitHub, find your fork and the new branch, then make a pull request**

  Pull requests let you tell others about changes you've pushed to a repository on GitHub. Once a pull request is sent, interested parties can review the set of changes, discuss potential modifications, and even push follow-up commits if necessary.

  Click on the logo at right to get started.
  ![Starting the pull request](https://github.com/yale-cpsc-113/CPSC113-madlibs/blob/master/images/pull.png)

  Then, once you get to another page, click the blue link.
  ![Continuing the pull request](https://github.com/yale-cpsc-113/CPSC113-madlibs/blob/master/images/pull2.png)

  Finally, click the create button to checkout the commit.
  ![Finishing the pull request](https://github.com/yale-cpsc-113/CPSC113-madlibs/blob/master/images/pull3.png)

  If you need extra help, check this out [https://help.github.com/articles/using-pull-requests/](https://help.github.com/articles/using-pull-requests/) or just come see a TA.

**11) The instructor will merge in everybody's work.**

Bother Kyle or the TAs if nothing's working. Or, put a post-it note on your laptop and we'll come around to you.

## Some hopefully helpful notes

* Each Story group should create a new html file to make a story. Stories should be put into the stories folder `/stories`. An example of a story is already in the folder (see `/stories/layout.html` or `/stories/layout2.html`) **Don't change these example files!** Make new ones!

  Stories are written in HTML! We are not going to be styling it, so forget about the CSS. Remember the general structure of HTML code: (No need to include the DOCTYPE stuff here).

    ```html
    <html>
      <body>
        Insert Code Here.
      </body>
    </html>
    ```
  You may notice that there are weird `{{...}}` everywhere in the example HTML codes. This stuff is super important! It tells our little node app that we need a(n) adjective/verb/adverb/noun at a certain place. When you write your own stories, make sure to do the same! For example, to denote an adjective, used `{{adjectives.get()}}`. The others follow the same style!

* The adjective, noun, and verb groups should work on their files. Adjective, noun, and verb files should be put in their respective folders. For example, verbs should be put in `/pos/verbs/verbs.js`.

  Examples of verbs, adjectives, etc files are found in the corresponding `starter.js` file in the folder in `/pos`. **Don't change these example files!.** Instead, make a new file.

    ```javascript
    module.exports.adjectives = [
      Insert Words Here.
    ];
    ```
  Notice that there is a very specific structure when listing the words in this file. Our node app waits to grab the array of words that is exported from this file. Therefore, don't forget the `module.exports.adjectives = ...`!

## Have Fun and Ask Questions!

Something to keep in mind as you are working: Make sure you comment your code. You may not need it but it's generally a good idea so that you and others can understand what is going on.

![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document 2023-06-28-wdcc-git: Collaborative version control with Git and Gitlab

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: https://tinyurl.com/wdcc-git-06-28

## 👮Code of Conduct

Participants are expected to follow these guidelines:
* Use welcoming and inclusive language.
* Be respectful of different viewpoints and experiences.
* Gracefully accept constructive criticism.
* Focus on what is best for the community.
* Show courtesy and respect towards other community members.
 
## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: [creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).

## 🙋Getting help

To ask a question, just raise your hand.

If you need help from a helper, place a pink post-it note on your laptop lid. A helper will come to assist you as soon as possible.

## 🖥 Workshop website

https://esciencecenter-digital-skills.github.io/2023-06-28-wdcc-git/

🛠 Setup

https://esciencecenter-digital-skills.github.io/2023-06-28-wdcc-git/#setup

## 👩‍🏫👩‍💻🎓 Instructors

Sven van der Burg, Sander van Rijn

## 🧑‍🙋 Helpers

Johan Hidding

## 👩‍💻👩‍💼👨‍🔬🧑‍🔬🧑‍🚀🧙‍♂️🔧 Roll Call
Name/ pronouns (optional) / job, role / social media (twitter, github, ...) / background or interests (optional) / city

## 🗓️ Agenda
09:00	Welcome and icebreaker
09:15	Introduction to version control with Git
10:20	Coffee break
10:30	Tracking changes and exploring history
11:30	Coffee break
11:40	Ignoring things, remotes, and conflicts
12:30	Lunch
13:30	Centralized workflow with Git and GitLab
14:30	Coffee break
14:40	Distributed workflow with Git and GitLab
15:30	Coffee break
15:40	Distributed workflow with Git and GitLab
16:15	Wrap-up
16:30	END

## 🏢 Location logistics
* Coffee and toilets?
* In case of an emergency?
* **Wifi** ?

## 🎓 Certificate of attendance
If you attend the full workshop you can request a certificate of attendance by emailing to training@esciencecenter.nl .

# 🔧 Exercises

## Exercise: git init
### 1. Places to Create Git Repositories

Along with tracking information about planets (the project we have already created),
Dracula would also like to track information about moons.
Despite Wolfman's concerns, Dracula creates a `moons` project inside his `planets`
project with the following sequence of commands:

~~~
$ cd ~/Desktop   # return to Desktop directory
$ cd planets     # go into planets directory, which is already a Git repository
$ ls -a          # ensure the .git subdirectory is still present in the planets directory
$ mkdir moons    # make a subdirectory planets/moons
$ cd moons       # go into moons subdirectory
$ git init       # make the moons subdirectory a Git repository
$ ls -a          # ensure the .git subdirectory is present indicating we have created a new Git repository
~~~

Is the `git init` command, run inside the `moons` subdirectory, required for
tracking files stored in the `moons` subdirectory?



#### Solutions
No, its a subfolder of planets and is already tracked


## Exercise: making changes
### 1. Choosing a Commit Message

Which of the following commit messages would be most appropriate for the
last commit made to `mars.txt`?

1. "Changes"
2. "Added line 'But the Mummy will appreciate the lack of humidity' to mars.txt"
3. "Discuss effects of Mars' climate on the Mummy"

correct answer: 3


### 2. Committing Changes to Git

Which command(s) below would save the changes of `myfile.txt`
to my local Git repository?

1. 
~~~
$ git commit -m "my recent changes"
~~~
2.
~~~
$ git init myfile.txt
$ git commit -m "my recent changes"
~~~
3.
~~~
$ git add myfile.txt
$ git commit -m "my recent changes"
~~~
4.
~~~
$ git commit -m myfile.txt "my recent changes"
~~~


Answer: 3, first use add, next use commit


### 3. Committing Multiple Files

The staging area can hold changes from any number of files
that you want to commit as a single snapshot.

1. Add some text to `mars.txt` noting your decision
to consider Venus as a base
2. Create a new file `venus.txt` with your initial thoughts
about Venus as a base for you and your friends
3. Add changes from both files to the staging area,
and commit those changes.



### 4. (optional) `bio` Repository

* Create a new Git repository on your computer called `bio`.
* Write a three-line biography for yourself in a file called `me.txt`,
commit your changes
* Modify one line, add a fourth line
* Display the differences
between its updated state and its original state.


## Git checkout
### Recovering Older Versions of a File

Jennifer has made changes to the Python script that she has been working on for weeks, and the
modifications she made this morning "broke" the script and it no longer runs. She has spent
~ 1hr trying to fix it, with no luck...

Luckily, she has been keeping track of her project's versions using Git! Which commands below will
let her recover the last committed version of her Python script called
`data_cruncher.py`?

1. `git checkout HEAD`

2. `git checkout HEAD data_cruncher.py`

3. `git checkout HEAD~1 data_cruncher.py`

4. `git checkout <unique ID of last commit> data_cruncher.py`

5. Both 2 and 4

#### Answers
The correct answer is 5. The first command doesn't do anything, the third goes back one commit too many.




### Reverting a Commit


Jennifer is collaborating with colleagues on her Python script.  She
realizes her last commit to the project's repository contained an error, and
wants to undo it.  Jennifer wants to undo correctly so everyone in the project's
repository gets the correct change. The command `git revert [erroneous commit ID]` will create a
new commit that reverses the erroneous commit.

The command `git revert` is
different from `git checkout [commit ID]` because `git checkout` returns the
files not yet committed within the local repository to a previous state, whereas `git revert`
reverses changes committed to the local and project repositories.

Below are the right steps and explanations for Jennifer to use `git revert`,
what is the missing command?
1. `________ # Look at the git history of the project to find the commit ID`

2. Copy the ID (the first few characters of the ID, e.g. 0b1d055).

3. `git revert [commit ID]`

4. Type in the new commit message.

5. Save and close

#### Answers
The `git log --oneline` command, gives us a commit ID.


### Understanding Workflow and History

What is the output of the last command in

~~~
$ cd planets
$ echo "Venus is beautiful and full of love" > venus.txt
$ git add venus.txt
$ echo "Venus is too hot to be suitable as a base" >> venus.txt
$ git commit -m "Comment on Venus as an unsuitable base"
$ git checkout HEAD venus.txt
$ cat venus.txt #this will print the contents of venus.txt to the screen

~~~

1. 
~~~
Venus is too hot to be suitable as a base
~~~
2.
~~~
Venus is beautiful and full of love
~~~
3.
~~~
Venus is beautiful and full of love
Venus is too hot to be suitable as a base
~~~
4.
~~~
Error because you have changed venus.txt without committing the changes
~~~

#### Answers
The answer is 2.


### Checking Understanding of `git diff`

Consider this command: `git diff HEAD~9 mars.txt`. What do you predict this command
will do if you execute it? What happens when you do execute it? Why?

Try another command, `git diff [ID] mars.txt`, where [ID] is replaced with
the unique identifier for your most recent commit. What do you think will happen,
and what does happen?

#### Answers
This will fail because there are no commits nine back. Nothing will be shown, since no changes were made.
 
### (optional) Getting Rid of Staged Changes

`git checkout` can be used to restore a previous commit when unstaged changes have
been made, but will it also work for changes that have been staged but not committed?
Make a change to `mars.txt`, add that change, and use `git checkout` to see if
you can remove your change.

#### Answers
 Yes, it does revert the changes

### (optional) Explore and Summarize Histories

Exploring history is an important part of Git, and often it is a challenge to find
the right commit ID, especially if the commit is from several months ago.

Imagine the `planets` project has more than 50 files.
You would like to find a commit that modifies some specific text in `mars.txt`.
When you type `git log`, a very long list appeared.
How can you narrow down the search?

Recall that the `git diff` command allows us to explore one specific file,
e.g., `git diff mars.txt`. We can apply a similar idea here.

~~~
$ git log mars.txt
~~~

Unfortunately some of these commit messages are very ambiguous, e.g., `update files`.
How can you search through these files?

Both `git diff` and `git log` are very useful and they summarize a different part of the history
for you.
Is it possible to combine both? Let's try the following:

~~~
$ git log --patch mars.txt
~~~

You should get a long list of output, and you should be able to see both commit messages and
the difference between each commit.

Question: What does the following command do?

~~~
$ git log --patch HEAD~9 *.txt
~~~

#### Answers
the same error as before becaus HEAD~9 sill does not exist. But if it did, it should show all changes made to .txt files from the first commit to HEAD~9.


## What to do if I can succesfully run `ssh -T git@git.wur.nl`?
- [Try out GitLab Wiki](https://git.wur.nl/hidding_j/pages-demo/-/wikis/home)
- learn about [merge conflicts](https://swcarpentry.github.io/git-novice/09-conflict.html)

## Exercise: Working as a project collaborator (in pairs):
Both of you should take the following actions:
- Log into GitLab (git.wur.nl) and create a new repository
- Make the repository public
- clone it to your desktop
- add some code
- push the changes to the repository
- Add the other person as a collaborator.
- The other person clones that repo
- make changes on a new branch
- push the changes
- submit a Merge Request
- wait for approval
- At the same time review a collaborators Merge Request
- (Optionally) Learn about [protecting branches](https://docs.gitlab.com/ee/user/project/protected_branches.html) and try it out. 
- (Optionally) learn about [merge conflicts](https://swcarpentry.github.io/git-novice/09-conflict.html)

# 🧠 Collaborative Notes

We use **git** to keep track of changes in any set of documents. Multiple users can make changes to the documents at the same time, and Git can be used to coordinate these changes. Parables of the time-machine and the tree: the tree has branches, git can switch between different branches.

Fire up your Git-bash! By typing `git` you get the basic help on using Git.

:::spoiler output of `git` command
```bash
usage: git [-v | --version] [-h | --help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--config-env=<name>=<envvar>] <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone     Clone a repository into a new directory
   init      Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add       Add file contents to the index
   mv        Move or rename a file, a directory, or a symlink
   restore   Restore working tree files
   rm        Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect    Use binary search to find the commit that introduced a bug
   diff      Show changes between commits, commit and working tree, etc
   grep      Print lines matching a pattern
   log       Show commit logs
   show      Show various types of objects
   status    Show the working tree status

grow, mark and tweak your common history
   branch    List, create, or delete branches
   commit    Record changes to the repository
   merge     Join two or more development histories together
   rebase    Reapply commits on top of another base tip
   reset     Reset current HEAD to the specified state
   switch    Switch branches
   tag       Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch     Download objects and refs from another repository
   pull      Fetch from and integrate with another repository or a local branch
   push      Update remote refs along with associated objects

'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
See 'git help git' for an overview of the system.
```
:::

Git can be configured in many ways

```bash
git config --list
```

Set your name and email-address. These are used to sign commits.

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@address.eu"
```

Between Windows and Linux/Mac, line-endings are different. It is best to make sure that line-endings are converted properly.

```bash
git config --global core.autocrlf input
```

Sometimes Git will try to start a text editor. We'll use `nano`, which is easier to use than `vim`.

```bash

git config --global core.editor "nano -w"
```

## Create a new project
Wolfman and Dracula go to Mars. They coordinate their plans in a Git repository. If you store projects in `~/Projects`, go there by typing `cd ~/Projects`, or maybe you put everything on your desktop, then `cd ~/Desktop`.

We create a new folder for the project, and initiate git version control.

```bash
mkdir planets
cd planets
git init
```

We can see that Git created a folder named `.git` by running `ls -a`

```
.  ..  .git
```

The insides of the `.git` folder are very complicated, luckily you won't have to get into `.git` very often.

We can check the status of Git by typing

```bash
git status
```

If your branch is named `master` you may want to move to `main`. (The default 'main' branch name changed a few years ago from 'master' to 'main')

```bash
git checkout -b main
```

## Add content
Open your editor to create a file `mars.txt`.

```bash
nano mars.txt
# type some text, press Ctrl-O to write and Ctrl-X to exit
```

We can check the contents of the file

```bash
cat mars.txt
```

Now, see what Git thinks of our addition

```bash
git status
```

```
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	mars.txt

nothing added to commit but untracked files present (use "git add" to track)
```

Let's follow those suggestions. The following will have Git track changes to `mars.txt`.

```
git add mars.txt
```

Now we can use `git commit` to create a new commit containing the changes we made.

```
git commit -m  "created mars.txt; Start notes on Mars as a base"
```

Run `git status` again to see what happened.

## Check your history
You can see the entire history of a repository.

```bash
git log
```

```
commit 5e576db9e6900fee5829c7c4e1b2fd54cf8887b6 (HEAD -> main)
Author: <<<You!>>>
Date:   Wed Jun 28 10:42:03 2023 +0200

    created mars.txt; Start notes on Mars as a base
```

Make some more changes to `mars.txt`

```bash
cat mars.txt
```

```
Cold and dry, but everything is my favourite colour!
The two moons may be a problem for Wolfman
```

You can see your changes by running

```bash
git diff
```

```
diff --git a/mars.txt b/mars.txt
index 534c520..e53cc51 100644
--- a/mars.txt
+++ b/mars.txt
@@ -1,2 +1,3 @@
 Cold and dry, but everything is my favourite colour!
+The two moons may be a problem for Wolfman
```

Create a new commit!

```bash
git commit -m "Add concerns about the effect of the 2 moons"
```

Ooops! This doesn't do anything, because we didn't add the changes.

```bash
git add mars.txt
# use the up-arrow key to get back to the previous command
git commit -m "Add concerns about the effect of the 2 moons"
```

When you `git add` changes, these changes are added to the *staging area*. After that, `git commit` creates a new commit from the changes listed in the staging area.

Run `git log` again to see the new commit.

Make another change, add this line to `mars.txt`

```
The mummy will appreciate the lack of humidity
```

and then add with `git add mars.txt`.

If you now run `git diff` nothing is shown. To show differences that are already `git add`ed, run

```
git diff --staged
```

Create a new commit

```
git commit -m "discuss the concerns about Mars climate for Mummy"
```

Again running `git log` will show three commit messages now. If you want a shorter overview of the log, run `git log --oneline`.

### Removing `.git` directory

```bash
mkdir moons
cd moons
git init
```

Not wanted! Be very careful with the following command:

```bash
rm -rf .git
```

### Multiple changes

Create `venus.txt`. Now you can add `venus.txt` to the staging area without including changes to `mars.txt`.

## The `HEAD`

`HEAD` is a pointer to the latest commit in a branch.

We can explicitly refer to `HEAD`, for instance when running `git diff`

```bash
git diff HEAD mars.txt
```

This will give the changes made with respect to the latest commit (instead of the staging area, which is the default).

References to `HEAD` allow for some simple arithmetic. We can refer to the commit before `HEAD` by saying `HEAD~1`, or the one before that by `HEAD~2`, etc.

```bash
git diff HEAD~2 mars.txt
```

We can see the changes made in a single commit by using `git show`

```bash
git show HEAD~1 mars.txt
```

This is the difference between `HEAD~2` and `HEAD~1`.

You can also refer to a commit in your `git log` by copy pasting the hexadecimal key.

```bash
git log
```

```
commit 0a603ced2a4f35729beff41debee3496050cd2a2
Author: <<<You!!!>>>
Date:   Wed Jun 28 10:59:02 2023 +0200

    Add concerns about the effect of the 2 moons

commit 5e576db9e6900fee5829c7c4e1b2fd54cf8887b6
Author: <<<You!!!>
Date:   Wed Jun 28 10:42:03 2023 +0200

    created mars.txt; Start notes on Mars as a base
```

Then run (using the hex-keys on your own screen)

```
git show 5e576db9e6900fee5829c7c4e1b2fd54cf8887b6
```

## Reverting changes

It turns out you're not happy with some change. Use `git checkout` to retrieve a file as it was at a certain commit.

```bash
git checkout HEAD~1 mars.txt
```

This retrieves the state of a file as it was before, but doesn't change the history of commits. If we run `git status` now, we see that the change is added to the staging area. If we commit now, it is as if we manually removed the last lines that we added since the last commit.

We can go back to the most recent version of `mars.txt` by checking out `HEAD`

```bash
git checkout HEAD mars.txt
```

Now, running `git status` should report a clean working tree.

You can remove a file from the git repository, use `git rm`

```bash
git rm venus.txt
```

Should we want to undo this

```bash
git checkout HEAD venus.txt
```

We've seen that we can retrieve previous states of files using `git checkout`, let's try without specifying a file

```bash
git checkout HEAD~2
```

Now the entire repository is in the state of two commits back!

```
Note: switching to 'HEAD~2'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 5e576db created mars.txt; Start notes on Mars as a base
```

We are in a *detached HEAD* state. This means that the current `HEAD` is not coinciding with any known branch. You can work with this, but the state is unreachable. You can create a new branch to resolve this, or checkout the original branch again.

```bash
git checkout main
```

or follow the given instructions to use `git switch`

```bash
git switch -
```

In this case `git switch` does the same as `git checkout`.

:::info
The `git checkout` command is rather overloaded with functionality. It can be used to:

- retrieve content from previous version
- change HEAD pointer to previous version
- switch to a different branch
- create a new branch

and probably much more. Since this is a thoroughly confusing situation, developers of `git` are migrating some of the functionality to the `git switch` and `git branch` commands.
:::

## Ignoring files

For your project you want to make a folder results

```bash
mkdir result
touch a.dat b.dat c.dat
ls
```

To create files inside the results folder

```bash
touch result/a.out result/b.out
git status
```

This lists a lot of files that we don't want to have under version control. Either they are too big or, they change a lot without being relevant. We can ignore these by creating a `.gitignore` file.

```gitignore
*.dat
result/
```

You should add `.gitignore` to fall under version control. That way other users will also get the same `.gitignore` file.

```bash
git add .gitignore
git commit -m 'add a .gitignore file'
```

Should you want to add one of the ignored files anyway, you can add them.

```bash
git add a.dat
```

```
The following paths are ignored by one of your .gitignore files:
a.dat
hint: Use -f if you really want to add them.
hint: Turn this message off by running
hint: "git config advice.addIgnoredFile false"
```

So we should use the `-f` flag.

```bash
git add -f a.dat
git status
```

```
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   a.dat
```

## Remotes

Create a new project on [git.wur.nl](git.wur.nl). Follow the instructions to upload an existing local Git repository:

```bash
# replace <<<...>>> with your info
git remote add origin git@git.wur.nl:<<<username>>>/<<<reponame>>>
git remote -v
```

Check if you can connect to the GitLab server:

```bash
ssh -T git@git.wur.nl
```

Configure SSH keys with GitLab. See [documentation](https://docs.gitlab.com/ee/user/ssh.html#generate-an-ssh-key-pair).

We can now push our files to the remote

```bash
git push origin main
```

Now your files should be visible in GitLab. GitLab has some easy to use buttons to create recommended files like README and LICENSE. Go ahead and add a LICENSE. NLeSC recommends Apache 2.

Now we can pull those changes back to our local repository.

```bash
git pull origin main
```

## Glossary

**commit** a set of coherent changes to your documents. Commits are made as concious decision by the user. Every commit has a message attached that describes the changes in human-readable form.

**diff** an overview of changes between two versions.

**branch** a pointer to the tip of a path through the tree of changes.

**staging area** collection of changes that are a candidate for a new commit.

**head** git equivalent of 'current working directory', a pointer to the latest commit.

**ignore** don't pay attention to this.

**remote** somewhere else (more specifically: someone else's computer)

**license** permission to others to use, change and redistribute your work to others

**merge** join two change sets into a single one. In a merge there is always a source and target branch. The merge creates a new commit in the target branch.

**conflict** change sets (commits) that are not compatible cannot be merged automatically

# Feedback

## post-workshop survey
https://www.surveymonkey.com/r/FSV7MZN


### What goes well
How did it go this morning? What did you like? 

- perhaps ask people whether they are familiar with linux commands and then you can go quicker with creating files and making directories etc. 
- 
- I liked the pace and methods of teaching the materials
- For me, the explanation was nice and clear. I would prefer a slight increase in pace of explanation.
- Nice combination between explanation and practice
-I  liked the help during the exercises and the speed of pathexercises
- the conceptual explaining is very good
- I like the colored posteds.
- Good intro, but could be slighly speed up
- I like the slow explaination but I would prefer not to have over simplification of terms or functionning
- I like the slow teaching in understandable way

- The speed of the tutorial was perfect
- Th interactive approach is OK
- the basics are clear. Now branching becomes more complicated... 

### What can be improved
Please tell us if we went too fast or too slow, if you didn't like the coffee or anything else that we can improve!

- Could have used more coffee
- yes.. more coffee ;-)
- And indeed some diagrams especially now that we go into branching topic ( but also a staging vs repository, local vs gitlab still has to come this afternoon )
- the concept of checkout  was a bit compicated... maybe show in parallele on the screen in Notepad the mars.txt file before and after the checkout step.to distinguish between the "active" file and what is present inthe .git repo.
- Could use more illustrative way or diagrams.
- Airco is set too low
- please, do not scroll to much or to fast
- The coffee was gone too quickly
- More visualisation.
- Demonstrate practical use in for example VS Code / Python
- Little bit mote coffee
- Could you move up the command line a little bit, please
- better explaination of commands, because naming is not always logic. Eg, 'checkout' doesn't logically relate to reverting things, I intuitively thought it had to do with publishing code online...
- Wondering whether the concept of git commits main and branches is easier explained first using a GUI like sourcetree (or even just GitLab itself) and then go into 'what you just saw can be done in a commandline way as well'. For people new in this subject, the visual aspect might appeal more.
- Using passphrases might be easier to use when implementing https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases#auto-launching-ssh-agent-on-git-for-windows which remembers the passphrase for the current session (if I interpret correctly). This means if a passphrase is set, it only needs to be typed once and not at every push.


### Sven's summary
* We need more coffee!? Let's see if our cry for more coffee is heard. Otherwise make sure everyone at least get's a fair share.
* Concept of commit trees and checkout is complicated. Maybe Sander can do a short recap. Then let's let it sink in for a little bit, it will probably become more clear once we start to work with it more. If not, there will be time to ask more questions during the exercises!
* We will try to scroll less. Please stop us if you want us to scroll back to a command.
* We will show some more visual real-world examples of git commit trees later.
* We have a few diagrams coming up


# 📚 Resources

- [The Git Book](https://git-scm.com/book/en/v2)
- [Choose a License](https://choosealicense.com/)
- eScience Center digitial skills workshops: https://www.esciencecenter.nl/digital-skills/
- eScience Center newsletter sign-up: http://eepurl.com/dtjzwP
- NL-RSE: https://nl-rse.org/


# post-workshop survey
https://www.surveymonkey.com/r/FSV7MZN

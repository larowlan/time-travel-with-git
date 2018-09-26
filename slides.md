<!-- .slide: data-background="./images/bttf.jpg" -->

## Time travel with git

Note:

-

---

## Who am I?

@larowlan

Note:

- by way of introduction
- Framework Manager for Drupal CMS
- One of the 'big 10' open source projects
- Runs 2% of the internet including some of the world's biggest sites
- 10 years of Drupal
- security team member
- senior drupal dev at @pnx

---

## Session overview

larowlan.github.io/time-travel-with-git

Note:

- Why you should be using git
- How to use git
- How git works

---

## If you write code and don't use version control<br/><br/>You're doing it wrong.

Note:

- this includes anything where you're working in text files
- e.g svg, puppet, config files

---

## Why git

Note:

- Distributed version control, every clone of a repository is also a repository, no single point of failure
- Non linear
- Open source
- From creator of Linux Kernel to ease collaboration on kernel development
- Fast
- There are other version control applications
- Git is near ubiquitous
- Just learn git

---

## You might need git if...

---

## You do this...

- index.html
- index.html.bak
- index.html.bak1

---

## Or this

- specification-v1-mar-31.docx
- specification-v2-final.docx
- specification-v2-final-approved-by-anthony.docx

---

## Or this

<pre><code class="php">
// Commented out by John Feb 2018.
// We don't need this at the moment, but will in July 2018.
// $widget->addPriceRise(15);
// $widget->recalculateTariff();
// $page->updateWidget($widget);
 
</code></pre>

---

## Core concepts

### Three states for files

1. committed
2. modified
3. staged

---

![](https://git-scm.com/book/en/v2/images/areas.png)

---

## Get started: Installation

- ✅ OSX: <pre>git --version</code>
- 📦 Linux: git-core from your package manager
- ⬇️ Windows: https://git-scm.com/download/win

---

## First time setup

<pre><code class="bash">
git config --global user.name "Beryl Johnson"
git config --global user.email cray.z.nana@gmail.com
</code></pre>

---

## Help - detailed

<pre><code class="bash">
git help <command>
</code></pre>

<pre><code class="bash">
git help add
</code></pre>

---

## Help - succinct

<pre><code class="bash">
git add -h
</code></pre>

<pre><code class="bash">
usage: git add [<options>] [--] <pathspec>...

    -n, --dry-run         dry run
    -v, --verbose         be verbose

    -i, --interactive     interactive picking
    -p, --patch           select hunks interactively
    -e, --edit            edit current diff and apply
    -f, --force           allow adding otherwise ignored files
    -u, --update          update tracked files
    -N, --intent-to-add   record only the fact that the path will be added later
    -A, --all             add changes from all tracked and untracked files
    --ignore-removal      ignore paths removed in the working tree (same as --no-all)
    --refresh             don't add, only refresh the index
    --ignore-errors       just skip files which cannot be added because of errors
    --ignore-missing      check if - even missing - files are ignored in dry run
    --chmod <(+/-)x>      override the executable bit of the listed files
</code></pre>

---

## Create your first repo

<pre><code class="bash">
mkdir -p ~/git/learning-git
cd ~/git/learning-git
git init
</code></pre>

<pre><code class="bash">
Initialized empty Git repository in /Volumes/files/code/git/learning-git/.git/
</code></pre>

---

## Basic flow

![](https://git-scm.com/book/en/v2/images/lifecycle.png)

---

## Checking status

<pre><code class="bash">
git status
</code></pre>

<pre><code class="bash">
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
</code></pre>

---

## Adding a file

- create a file with https://raw.githubusercontent.com/exercism/php/master/exercises/hello-world/hello-world.php
<pre><code class="bash">
wget https://raw.githubusercontent.com/exercism/php/master/exercises/hello-world/hello-world.php
</code></pre>

---

## Adding a file continued

<pre><code class="bash">
git status
</code></pre>

<pre><code class="bash">
On branch master

No commits yet

Untracked files:
  (use "git add &lt;file&gt;..." to include in what will be committed)

	hello-world.php

nothing added to commit but untracked files present (use "git add" to track)
</code></pre>

---

## Adding a file continued

<pre><code class="bash">
git add hello-world.php
</code></pre> 

<pre><code class="bash">
git status
</code></pre>

<pre><code class="bash">
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached &lt;file&gt;..." to unstage)

	new file:   hello-world.php
</code></pre>

---

## Your first commit

<pre><code class="bash">
git commit -m "Added hello world feature"
</code></pre>

<pre><code class="bash">
[master (root-commit) c3bd2d0] Added hello world feature
 1 file changed, 13 insertions(+)
 create mode 100644 hello-world.php
</code></pre>

Note:

- the sha
- the stat

---

## Commit messages

### do

- describe what was changed
- make it clear what is added
- keep it succinct
- be kind to your future self and colleagues
- reference ticket numbers (use a convention)

---

## Commit messages

### don't

- "fixed"
- write a novel
- "changes"
- "wip"

---

## Making changes

- edit hello-world.php and make these changes

<pre><code class="php">
function helloWorld()
{
    echo "Hello world!";
}
</code></pre>

---

## Making changes

<pre><code class="bash">
git status
</code></pre>

<pre><code class="bash">
On branch master
Changes not staged for commit:
  (use "git add &lt;file&gt;..." to update what will be committed)
  (use "git checkout -- &lt;file&gt;..." to discard changes in working directory)

	modified:   hello-world.php

no changes added to commit (use "git add" and/or "git commit -a")
</code></pre>

---

## Making changes

<pre><code class="bash">
git diff
</code></pre>

<pre><code class="diff">
diff --git a/hello-world.php b/hello-world.php
index 6f8ce23..72f3031 100644
--- a/hello-world.php
+++ b/hello-world.php
@@ -1,13 +1,7 @@
 &lt;?php

-//
-// This is only a SKELETON file for the "Hello World" exercise.
-// It's been provided as a convenience to get you started writing code faster.
-//

 function helloWorld()
 {
-    //
-    // YOUR CODE GOES HERE
-    //
+  echo "Hello world!";
 }
</code></pre>

---

## Making changes

<pre><code class="bash">
git add hello-world.php
git status
</code></pre>

<pre><code class="bash">
rowlandss-MacBook-Pro:learning-git rowlands$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD &lt;file&gt;..." to unstage)

	modified:   hello-world.php

</code></pre>

---

## Making changes

<pre><code class="bash">
git diff
</code></pre>

???

<pre><code class="bash">
git diff --staged
</code></pre>

<pre><code class="diff">
diff --git a/hello-world.php b/hello-world.php
index 6f8ce23..72f3031 100644
--- a/hello-world.php
+++ b/hello-world.php
@@ -1,13 +1,7 @@
 &lt;?php

-//
-// This is only a SKELETON file for the "Hello World" exercise.
-// It's been provided as a convenience to get you started writing code faster.
-//

 function helloWorld()
 {
-    //
-    // YOUR CODE GOES HERE
-    //
+  echo "Hello world!";
 }
</code></pre>

---

## Making changes

<pre><code class="bash">
git commit -m "Implemented hello-world"
</code></pre>

<pre><code class="bash">
[master 4842ada] Implemented hello-world
 1 file changed, 1 insertion(+), 7 deletions(-)
</code></pre>

---

## Seeing our changes

<pre><code class="bash">
git log --oneline --decorate
</code></pre>

<pre><code class="bash">
4842ada (HEAD -> master) Implemented hello-world
c3bd2d0 Added hello world feature
</code></pre>

Note:

- Make note of the HEAD and master, more on them later
- Notice the shas again, more on them later

---

## Undoing things

### I forgot something 

<pre><code class="bash">
git add forgotten-file.txt
git commit --amend
</code></pre>

---

## Undoing things

### My commit message was wrong

<pre><code class="bash">
git commit --amend
</code></pre>

---

## Undoing things

### I need to unstage a file

<pre><code class="bash">
git add file-i-should-not-add.txt
git reset -- file-i-should-not-add.txt
</code></pre>

---

## Undoing things

### I don't want the changes anymore

<pre><code class="bash">
git checkout -- file-with-edits-i-do-not-want.txt
</code></pre>

---

## Collaboration - existing and remote repositories

### Existing repositories

<pre><code class="bash">
cd ~/git
git clone https://github.com/larowlan/tl.git
# If you have a github account
git clone git@github.com:larowlan/tl.git
</code></pre>

---

## Collaboration - remotes

<pre><code class="bash">
git remote -v
</code></pre>

<pre><code class="bash">
origin	git@github.com:larowlan/tl.git (fetch)
origin	git@github.com:larowlan/tl.git (push)
</code></pre>

Note:

- origin is the default
- you can name it anything

---

## Fetching remote commits

<pre><code class="bash">
git fetch origin
</code></pre>

---

## Pushing your commits <br/>to remote

<pre><code class="bash">
git push origin master
</code></pre>

Note:

- remote name
- branch name

---

## Tags, branches

- So before we saw each commit got a sha hash
- Tags and branches are ways to name those commits
- Tag is fixed in time (always points to one sha)
- Branches follow the latest commit
- E.g. master

<pre><code class="bash">
git log --oneline --decorate
6a05994 (HEAD -> master) Implemented hello-world
c3bd2d0 Added hello world feature
</code></pre>

---

![](https://git-scm.com/book/en/v2/images/commits-and-parents.png)

---

![](https://git-scm.com/book/en/v2/images/branch-and-history.png)

---

## Branches

- Branches allow development of features in parallel
- Unlimited branches

Note:

- Think of it like a tree branch

---

## Creating a new branch

<pre><code class="bash">
git branch amazing-feature
git log --oneline --decorate
6a05994 (HEAD -> master, amazing-feature) Implemented hello-world
c3bd2d0 Added hello world feature
</code></pre>

---

![](https://git-scm.com/book/en/v2/images/two-branches.png)

---

## HEAD?

<pre><code class="bash">
git log --oneline --decorate
6a05994 (HEAD -> master, amazing-feature) Implemented hello-world
c3bd2d0 Added hello world feature
</code></pre>

A special pointer that keeps track of what branch you're currently on 

---

![](https://git-scm.com/book/en/v2/images/head-to-master.png)

---

## Switching to the branch

<pre><code class="bash">
git checkout amazing-feature
git log --oneline --decorate
6a05994 (master, HEAD -> amazing-feature) Implemented hello-world
c3bd2d0 Added hello world feature
</code></pre>

---

![](https://git-scm.com/book/en/v2/images/head-to-testing.png)

---

## Create and switch in one go

<pre><code class="bash">
git checkout -b amazing-feature
</code></pre>

---

## Working in a branch

Edit hello-world like so:
<pre><code class="php">
function helloWorld($name = 'World')
{
  echo "Hello $name!";
}
</code></pre> 
Commit it
<pre><code class="bash">
git add hello-world.php
git commit -m "Can greet anyone"
</code></pre>

---

## So what?

<pre><code class="bash">
git log --oneline --decorate
997d247 (HEAD -> amazing-feature) Can greet anyone
6a05994 (master) Implemented hello-world
c3bd2d0 Added hello world feature
</code></pre>

Note:

- HEAD points to amazing feature
- master does not have can greet anyone

---

![](https://git-scm.com/book/en/v2/images/advance-testing.png)

---

## Back to master?

<pre><code class="bash">
git checkout master
git log --oneline --decorate
6a05994 (HEAD -> master) Implemented hello-world
c3bd2d0 Added hello world feature
</code></pre>

---

![](https://git-scm.com/book/en/v2/images/checkout-master.png)

---

## Where is my greet anyone feature?

<pre><code class="bash">
git diff amazing-feature
</code></pre>

<pre><code class="diff">
diff --git a/hello-world.php b/hello-world.php
index d4f1f53..72f3031 100644
--- a/hello-world.php
+++ b/hello-world.php
@@ -1,7 +1,7 @@
 &lt;?php


-function helloWorld($name = 'World')
+function helloWorld()
 {
-  echo "Hello $name!";
+  echo "Hello world!";
 }
</code></pre>

---

## Parting ways

Let's edit hello-world.php on master like so
<pre><code class="php">
function helloWorld($greeting = 'Hello')
{
  echo "$greeting world!";
}
</code></pre> 
Commit it
<pre><code class="bash">
git add hello-world.php
git commit -m "Can vary greeting"
</code></pre>

---

## Parting ways

<pre><code class="bash">
git log --oneline --decorate
41887a0 (HEAD -> master) Can vary greeting
6a05994 Implemented hello-world
c3bd2d0 Added hello world feature
</code></pre>

---

![](https://git-scm.com/book/en/v2/images/advance-master.png)

---

## Gee that chart is nice?

<pre><code class="bash">
git log --oneline --decorate --graph --all
* 41887a0 (HEAD -> master) Can vary greeting
| * 997d247 (amazing-feature) Can greet anyone
|/
* 6a05994 Implemented hello-world
* c3bd2d0 Added hello world feature
</code></pre>

---

## Merging

<pre><code class="bash">
git merge amazing-feature
Auto-merging hello-world.php
CONFLICT (content): Merge conflict in hello-world.php
Automatic merge failed; fix conflicts and then commit the result.
</code></pre>

---

## Oh-oh

<pre><code class="php">
<<<<<<< HEAD
function helloWorld($greeting = 'Hello')
{
  echo "$greeting world!";
=======
function helloWorld($name = 'World')
{
  echo "Hello $name!";
>>>>>>> amazing-feature
</code></pre>

---

## We manually edit

new contents:

<pre><code class="php">
function helloWorld($greeting = 'Hello', $name = 'world')
{
  echo "$greeting $name!";
}
</code></pre>

---

## And commit

<pre><code class="bash">
git status
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add &lt;file&gt;..." to mark resolution)

	both modified:   hello-world.php

no changes added to commit (use "git add" and/or "git commit -a")
</code></pre>

---

## Commit continued

<pre><code class="bash">
git add hello-world.php
git commit
[master 7b53116] Merge branch 'amazing-feature'
</code></pre>

---

## Looking at our tree

<pre><code class="bash">
git log --oneline --decorate --all --graph
*   7b53116 (HEAD -> master) Merge branch 'amazing-feature'
|\
| * 997d247 (amazing-feature) Can greet anyone
* | 41887a0 Can vary greeting
|/
* 6a05994 Implemented hello-world
* c3bd2d0 Added hello world feature
</code></pre>

---

## Tagging

We decide we want to roll a 1.0.0 and a 1.1.0
<pre><code class="bash">
git tag 1.1.0 -m "Vary greeting and name"
git log --oneline --decorate
7b53116 (HEAD -> master, tag: 1.1.0) Merge branch 'amazing-feature'
41887a0 Can vary greeting
997d247 (amazing-feature) Can greet anyone
6a05994 Implemented hello world
c3bd2d0 Added hello world feature
</code></pre>

---

## Tagging an earlier commit

<pre><code class="bash">
git tag 1.0.0 -m "Vary greeting and name" 6a05994
git log --oneline --decorate
7b53116 (HEAD -> master, tag: 1.1.0) Merge branch 'amazing-feature'
41887a0 Can vary greeting
997d247 (amazing-feature) Can greet anyone
6a05994 (tag: 1.0.0) Implemented hello world
c3bd2d0 Added hello world feature
</code></pre>

---

## Going back in time

We can checkout code at any point and take a look around

<pre><code class="bash">
git checkout 1.0.0
 Note: checking out '1.0.0'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b &lt;new-branch-name&gt;

HEAD is now at 6a05994... Implemented hello world
</code></pre>

---

## Detached HEAD?

<pre><code class="bash">
git checkout -b coding-standards
Switched to a new branch 'coding-standards'
git log --all --graph --decorate --oneline
*   7b53116 (tag: 1.1.0, master) Merge branch 'amazing-feature'
|\
| * 997d247 (amazing-feature) Can greet anyone
* | 41887a0 Can vary greeting
|/
* 6a05994 (HEAD -> coding-standards, tag: 1.0.0) Implemented hello world
* c3bd2d0 Added hello world feature
</code></pre>

---

Make this change

<pre><code class="php">
/**
 * Outputs hello world.
 */
function helloWorld() {
  echo "Hello world!";
}
</code></pre>

---

## Commit

<pre><code class="bash">
git add hello-world.php
git commit -m "Coding standards holy war"
[coding-standards dbd5654] Coding standards holy war
 1 file changed, 4 insertions(+), 3 deletions(-)
</code></pre>

---

## Looking at the graph

<pre><code class="bash">
git checkout master
git log --all --graph --decorate --oneline
* dbd5654 (coding-standards) Coding standards holy war
| *   7b53116 (HEAD -> master, tag: 1.1.0) Merge branch 'amazing-feature'
| |\
| | * 997d247 (amazing-feature) Can greet anyone
| |/
|/|
| * 41887a0 Can vary greeting
|/
* 6a05994 (tag: 1.0.0) Implemented hello world
* c3bd2d0 Added hello world feature
</code></pre>

---

## Resetting

- Think of this as the rewind button

* rewrites history

---

<pre><code class="bash">
git checkout amazing-feature
git log --oneline --decorate
997d247 (HEAD -> amazing-feature) Can greet anyone
6a05994 (tag: 1.0.0) Implemented hello world
c3bd2d0 Added hello world feature
</code></pre>

---

<pre><code class="bash">
git reset coding-standards
Unstaged changes after reset:
M	hello-world.php
git log --oneline --decorate
dbd5654 (HEAD -> coding-standards) Coding standards holy war
6a05994 (tag: 1.0.0) Implemented hello world
c3bd2d0 Added hello world feature
</code></pre>

---

<pre><code class="bash">
git diff
</code></pre>

<pre><code class="diff">
diff --git a/hello-world.php b/hello-world.php
index 96f669c..68bcf64 100644
--- a/hello-world.php
+++ b/hello-world.php
@@ -3,6 +3,6 @@
 /**
  * Outputs hello world.
  */
-function helloWorld() {
-  echo "Hello world!";
+function helloWorld($name = 'World') {
+  echo "Hello $name!";
 }
</code></pre>

---

## history is rewritten

- Our changes are still there, but the commit is gone

---

## hard reset

<pre><code class="bash">
git reset coding-standards --hard
HEAD is now at dbd5654 Coding standards holy war
git diff
</code></pre>

- our changes are gone...

---

## hard reset

- ...from this branch

<pre><code class="bash">
git show 997d247
</code></pre>

<pre><code class="diff">
commit b2a6a02a69ea01071483f36dd495020ffd0cf99a
Author: Lee Rowlands &lt;lee.rowlands@previousnext.com.au&gt;
Date:   Thu Sep 20 11:22:39 2018 +1000

    Can greet anyone

diff --git a/hello-world.php b/hello-world.php
index 96f669c..68bcf64 100644
--- a/hello-world.php
+++ b/hello-world.php
@@ -3,6 +3,6 @@
 /**
  * Outputs hello world.
  */
-function helloWorld() {
-  echo "Hello world!";
+function helloWorld($name = 'World') {
+  echo "Hello $name!";
 }
</code></pre>

---

## resetting again

<pre><code class="bash">
git reset 997d247 --hard
git log --oneline --decorate
997d247 (HEAD -> amazing-feature) Can greet anyone
6a05994 (tag: 1.0.0) Implemented hello world
c3bd2d0 Added hello world feature
</code></pre>

---

## reset summary

* reset moves the pointer around without changing files
* reset --hard moves the pointer and changes files

---

## Rebasing

Think of this as rewind + replay

* rewrites history

---

<pre><code class="bash">
git checkout amazing-feature
Switched to branch 'amazing-feature'
git log --oneline --decorate
997d247 (HEAD -> amazing-feature) Can greet anyone
6a05994 (tag: 1.0.0) Implemented hello-world
c3bd2d0 Added hello world feature
</code></pre>

---

<pre><code class="bash">
git rebase coding-standards
First, rewinding head to replay your work on top of it...
Applying: Can greet anyone
Using index info to reconstruct a base tree...
M	hello-world.php
Falling back to patching base and 3-way merge...
Auto-merging hello-world.php
CONFLICT (content): Merge conflict in hello-world.php
error: Failed to merge in the changes.
Patch failed at 0001 Can greet anyone
The copy of the patch that failed is found in: .git/rebase-apply/patch

Resolve all conflicts manually, mark them as resolved with
"git add/rm &lt;conflicted_files&gt;", then run "git rebase --continue".
You can instead skip this commit: run "git rebase --skip".
To abort and get back to the state before "git rebase", run "git rebase --abort".
</code></pre>

---

## Resolve conflicts

<pre><code class="php">

<<<<<<< HEAD
/**
 * Outputs hello world.
 */
function helloWorld() {
  echo "Hello world!";
=======

function helloWorld($name = 'World')
{
  echo "Hello $name!";
>>>>>>> Can greet anyone
}
</code></pre>

---

<pre><code class="php">

/**
 * Outputs hello world.
 */
function helloWorld($name = 'World') {
  echo "Hello $name!";
}
</code></pre>

---

## Finish rebase

<pre><code class="bash">
git add hello-world.php
git rebase --continue
Applying: Can greet anyone
</code></pre>

---

## Rebasing creates new <br/>commits

### before
<pre><code class="bash">
997d247 (HEAD -> amazing-feature) Can greet anyone
6a05994 (tag: 1.0.0) Implemented hello-world
c3bd2d0 Added hello world feature
</code></pre>

### after

<pre><code class="bash">
b2a6a02 (HEAD -> amazing-feature) Can greet anyone
dbd5654 (coding-standards) Coding standards holy war
6a05994 (tag: 1.0.0) Implemented hello world
c3bd2d0 Added hello world feature
</code></pre>

---

## the full tree

<pre><code class="bash">
git log --all --graph --decorate --oneline
* b2a6a02 (HEAD -> amazing-feature) Can greet anyone
* dbd5654 (coding-standards) Coding standards holy war
| *   7b53116 (tag: 1.1.0, master) Merge branch 'amazing-feature'
| |\
| | * 997d247 Can greet anyone
| |/
|/|
| * 41887a0 Can vary greeting
|/
* 6a05994 (tag: 1.0.0) Implemented hello world
* c3bd2d0 Added hello world feature
</code></pre>

---

## Rebasing tips

- rebase onto tip before merging, so you get linear commits
- don't rebase things others may have pulled to their local - you're rewriting history
- use the <code>-i</code> flag to reorder, squash, drop and rename commits 💪

---

## The Blame game

<pre><code class="bash">
git checkout master
git blame hello-world.php
</code></pre>

<pre><code class="bash">
^c3bd2d0 (Lee Rowlands 2018-09-20 10:24:36 +1000 1) &lt;?php
^c3bd2d0 (Lee Rowlands 2018-09-20 10:24:36 +1000 2)
^c3bd2d0 (Lee Rowlands 2018-09-20 10:24:36 +1000 3)
7b53116c (Lee Rowlands 2018-09-20 11:34:09 +1000 4) function helloWorld($greeting = 'Hello', $name = 'world')
^c3bd2d0 (Lee Rowlands 2018-09-20 10:24:36 +1000 5) {
7b53116c (Lee Rowlands 2018-09-20 11:34:09 +1000 6)   echo "$greeting $name!";
^c3bd2d0 (Lee Rowlands 2018-09-20 10:24:36 +1000 7) }
</code></pre>

---

## Viewing the diff of a sha

<pre><code class="bash">
git show 7b53116c
</code></pre>

<pre><code class="diff">
commit 7b53116c9698277ca12332ed8db1392944d70a42 (HEAD -> master, tag: 1.1.0)
Merge: 41887a0 997d247
Author: Lee Rowlands &lt;lee.rowlands@previousnext.com.au&gt;
Date:   Thu Sep 20 11:34:09 2018 +1000

    Merge branch 'amazing-feature'

diff --cc hello-world.php
index a21d0d9,d4f1f53..3680758
--- a/hello-world.php
+++ b/hello-world.php
@@@ -1,7 -1,7 +1,7 @@@
  &lt;?php


- function helloWorld($greeting = 'Hello')
 -function helloWorld($name = 'World')
++function helloWorld($greeting = 'Hello', $name = 'world')
  {
-   echo "$greeting world!";
 -  echo "Hello $name!";
++  echo "$greeting $name!";
  }
</code></pre>

---

## or just the files

<pre><code class="bash">
git show 7b53116c --name-only
commit 7b53116c9698277ca12332ed8db1392944d70a42 (HEAD -> master, tag: 1.1.0)
Merge: 41887a0 997d247
Author: Lee Rowlands &<lt;lee.rowlands@previousnext.com.au&gt;>
Date:   Thu Sep 20 11:34:09 2018 +1000

    Merge branch 'amazing-feature'

hello-world.php
</code></pre>

---

## or just one file

<pre><code class="bash">
git show 7b53116c -- /path/to/some/file
</code></pre>

---

## Bisect

- find out when things broke 💪
- best if you have a test suite
- which commit introduced a bug
- tell git which is a good commit
- which is a bad
- it will go forward and backward in commits
- you test and tell it if the commit is good/bad
- it will pinpoint the commit that introduced the bug

---

## Reverting

- reverse a commit but retain in the history
- use this instead of reset when the commit has been pushed

<pre><code class="bash">
git revert 9823abf
</code></pre>

---

## Resources

- The git book - https://git-scm.com/book/en/v2

---

## Image credits

<ul class="tight">
<li>http://time.com/3943784/back-to-the-future-theories/</li>
<li>https://git-scm.com/book</li>
</ul>

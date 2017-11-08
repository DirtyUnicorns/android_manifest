# Dirty Unicorns #
[<center><img src="https://lh3.googleusercontent.com/-p9S_rIap_No/V9iIHcrU1_I/AAAAAAAAEPk/Mba0HIFDvR8oE_1hmfj0SGWqlx561mZBwCL0B/w971-h547-n-no/12.png" height="100%" width="100%;"/></center>](https://github.com/dirtyunicorns)
## To initialise Dirty Unicorns repo to this current branch ##
```bash
repo init -u https://github.com/DirtyUnicorns/android_manifest.git -b du-n
```
## To sync to Dirty Unicorns repo ##
```bash
repo sync --force-sync
```
## Setup your build enivornment & Sync our source ##
To setup your build enivornment and sync DU, please follow this guide: [Link](https://raw.githubusercontent.com/nathanchance/Android-Tools/master/Guides/Building_AOSP.txt)

## Submitting Patches ##
Dirty Unicorns is a open source project and welcomes new contributors.

To start contributing to DU, just register at "gerrit.dirtyunicorns.com".

Open up terminal to create your ssh keys required for submitting patches to gerrit and type in:

```bash
git config --global review.gerrit.dirtyunicorns.com.username <username you registered with>

git config --global review.gerrit.dirtyunicorns.com.email <your email you registered with>

ssh-keygen -t rsa -C "your@email.com"
```

In our gerrit click on your "Avatar" on the top right, then on "Settings".

While in 'Settings' Click on "SSH Public Keys" on the left hand side and then on "Add Key".

Now on your computer navigate to your home "~/.ssh" and open up "id_rsa.pub", copy/paste the context to "Gerrit SSH Public Keys".

You can send patches to us by using these commands in terminal:

```bash
cd PROJECT - i.e cd packages/apps/Settings

Make whatever edits you need to .....

git add -A
git commit -a

Add commit message that makes sense for others to understand what the commit is for

Ctrl X, then Y to save and Enter

git push ssh://USERNAME@gerrit.dirtyunicorns.com:29418/PROJECT HEAD:refs/for/BRANCH

BRANCH - i.e n
PROJECT - i.e packages_apps_Settings
USERNAME - i.e Mazda
```

If you are going to make extra additions, just repeat steps (don't start a new patch), but instead of git commit -m
use git commit --amend. Gerrit will recognize it as a new patchset.

For more information on how to push to a gerrit, please read the following: [Link](https://wiki.mahara.org/wiki/Developer_Area/Contributing_Code)

Also to make this even easier, you can use a universal gerrit script provided by PAC: [Link](http://forum.xda-developers.com/showthread.php?t=2530388)

If you still can not figure it out, don't hesitate to contact us in our G+ community: [Link](https://plus.google.com/u/0/communities/109738128866939227235)

## Maintain Authorship ##
Please make sure if you submit a patch/fix from another ROM that you maintain authorship. 
This is very important to not only us but to the entire open source community. It's what keeps it going and encourages more developers to contribute their work.

If you manually cherry pick a patch/fix please add the original author prior to pushing to our gerrit. 
This task is very easy and is usually done after you commit a patch/fix locally.

i.e - Once you type in "git commit -a" the commit message and you have saved it, type in the following:

```bash
git commit --amend --author "Author <email@address.com>"
```

So it should look like this once you get all author's information:

```bash
git commit --amend --author "Alex Cruz <mazdarider23@gmail.com>"
```

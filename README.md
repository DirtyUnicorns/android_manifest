# Dirty Unicorns #

## Setup your build enivornment & sync our source ##

To setup your build enivornment and sync DU, please follow this guide [HERE](https://raw.githubusercontent.com/nathanchance/Android-Tools/master/Building_AOSP.txt)

## Submitting Patches ##

Dirty Unicorns is open sourced and welcomes new contributors.

To start contributing to DU, just register at gerrit.dirtyunicorns.com

Open up a terminal to create your ssh keys for pushing to gerrit and type in

```bash
git config --global review.gerrit.dirtyunicorns.com.username <username you registered with>

git config --global review.gerrit.dirtyunicorns.com.email <your email you registered with>

ssh-keygen -t rsa -C "your@email.com"
```

Go back to our gerrit and click on your avatar on the top right, click on Settings

Click on SSH Public Keys on the left hand side and click on "Add Key ..."

Now on your computer navigate to home/.ssh and open up id_rsa.pub and copy/paste the context to Gerrit under SSH Public Keys

You can send patches to us by using these commands in terminal:

```bash
cd project i.e cd packages/apps/Settings

Make whatever edits you need to.....

git add -A
git commit -a

Add commit message that makes sense for others to understand what the commit is for

Ctrl X, then Y to save and Enter

git push ssh://USERNAME@gerrit.dirtyunicorns.com:29418/PROJECT HEAD:refs/for/BRANCH

BRANCH - m
PROJECT - i.e packages_apps_Settings
USERNAME (for gerrit) - i.e Mazda
```

If you are going to make extra additions, just repeat steps (Don't start a new patch), but instead of git commit -m
use git commit --amend. Gerrit will recognize it as a new patchset.

For more information on how to push to a gerrit, please read the following
https://wiki.mahara.org/index.php/Developer_Area/Pushing_Git_Commits

Also to make this even easier, you can use a universal gerrit script provided by PAC found here
http://forum.xda-developers.com/showthread.php?t=2530388

If you still can not figure it out, don't hesitate to contact us in our G+ community found here
https://plus.google.com/u/0/communities/109738128866939227235

## Maintain Authorship ##
Please make sure if you submit a patch/fix from another ROM that you maintain authorship. This is very important to not only us 
but to the entire open source community. It's what keeps it going and encourages more developers to contribute their work.

If you manually cherry pick a patch/fix then add the original author prior to pushing to our gerrit. This task is very easy and is
usually done after you commit a patch/fix locally. i.e once you type in git commit -a and type in the commit message and save, you
type in the following

```bash
git commit --amend --author "Author <email@address.com>"
```

So it should look like this once you get all author's information

```bash
git commit --amend --author "Alex Cruz <mazdarider23@gmail.com>"
```

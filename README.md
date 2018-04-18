# Dirty Unicorns #
[<center><img src="https://lh3.googleusercontent.com/-p9S_rIap_No/V9iIHcrU1_I/AAAAAAAAEPk/Mba0HIFDvR8oE_1hmfj0SGWqlx561mZBwCL0B/w971-h547-n-no/12.png" height="100%" width="100%;"/></center>](https://github.com/dirtyunicorns)

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

git push ssh://<username>@gerrit.dirtyunicorns.com:29418/<project> HEAD:refs/for/<branch>
```

* `<username>` - Your Gerrit username (which can be seen/set [here](https://gerrit.dirtyunicorns.com/#/settings/))
* `<project>` - The git repo you are pushing to; all options can be viewed at [this link](https://gerrit.dirtyunicorns.com/#/admin/projects/)
* `<branch>` - The git branch your change is based on; for projects using this manifest, it is `o8x`

A full command would look like:

```bash
git push ssh://Mazda@gerrit.dirtyunicorns.com:29418/android_packages_apps_Settings HEAD:refs/for/o8x
```

If you are going to make extra additions, just repeat steps (don't start a new patch), but instead of git commit -m
use git commit --amend. Gerrit will recognize it as a new patchset. Do NOT change the Change-Id in the commit message.

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
git commit --amend --author "Alex Cruz <du.alexcruz@gmail.com>"
```

If you do not want to clone or fetch the repo and the patch is on GitHub, you can easily get the author of the patch by adding `.patch` to the end of the commit URL and copy the contents of the from line after the `From:`.

For example: https://github.com/DirtyUnicorns/android_manifest/commit/9d44b2e34fd0b6674de79d001010e513ba14e312.patch

It is also recommended that you keep the date intact as well as it helps other open source users figure out the original version that a patch may have come from. Copy the contents of the date line after the `Date:` then add `--date="<date_just_copied>"` to the above `git commit --amend` command.

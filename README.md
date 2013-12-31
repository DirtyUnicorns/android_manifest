Get Repo
---------------------------------------

    mkdir ~/bin
    PATH=~/bin:$PATH
    curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
    chmod a+x ~/bin/repo

Syncing the DU Source
---------------------------------------

    mkdir ~/du
    cd ~/du
    repo init -u https://github.com/DirtyUnicorns-KitKat/manifest.git -b du44
    repo sync -f -j 4 | 8 | 16 | 24 | 32


Submitting Patches
------------------
We are a open source project that lives because of contributions of the Android community.

With that said, patches are always welcome!

You can send patches by using these commands:

    cd <project>
    <make edits>
    git add -A
    git commit -m "commit message"
    git push ssh://<username>@gerrit.dirtyunicorns.com:29418/<project> HEAD:refs/for/<branch>

Register at gerrit.dirtyunicorns.com and use the username that you registered there in the above command

Commit your patches in a single commit. Squash multiple commit using this command: git rebase -i HEAD~<# of commits>

If you are going to make extra additions, just repeat steps (Don't start a new patch), but instead of git commit -m
use git commit --amend. Gerrit will recognize it as a new patchset.

Thank you,
DU Team

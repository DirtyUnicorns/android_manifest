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


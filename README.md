vim: fdl=3:

my fork of the excellent [tagbar](https://github.com/preservim/tagbar) with thanks to the developers

My only tweak is to remove `'<F1>', ` from `tagbar/plugin/tagbar.vim` such that `<f1>` is free for my (unrelated) preferred use.

## how I merge this from preservim upstream

    git pull --unshallow
    git remote -v                                   # check remote locations
        git remote add upstream https://github.com/preservim/tagbar
    git fetch upstream                              # grab the changed upstream
    git merge upstream/master -m '5 commits behind' # merges in the changes
    rg HEAD                                         # ripgrep for any conflicts
        in vim: /^<<<<<<< HEAD$\|^=======$\|^>>>>>>> upstream/master$
    ga .                                            # if necessary
    gic '2 commit behind'
        git merge --abort                           # undo the merge
    git push

## files on my system
    $GHrCl/CP/Vim/preservim-tagbar/README.md
    $vimfiles/pack/packs-cp/opt/tagbar/README.md


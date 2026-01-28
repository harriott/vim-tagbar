vim: fdl=3:

    $vfvp/packs-cp-full/opt/vim-tagbar/README.md

my fork of the excellent [$GRs/d-CP/d-Vim-Vim/r-preservim-tagbar](https://github.com/preservim/tagbar) with thanks to the developers

My only tweak is to remove `'<F1>', ` from `tagbar/plugin/tagbar.vim` such that `<f1>` is free for my (unrelated) preferred use.

## how I merge this from preservim upstream

    git pull --unshallow
    git remote -v                                   # check remote locations
        git remote add upstream https://github.com/preservim/tagbar
    git fetch upstream                              # grab the changed upstream
    git merge upstream/master -m '1 commit behind' # merges in the changes
    rg HEAD                                         # ripgrep for any conflicts
        in vim: /^<<<<<<< HEAD$\|^=======$\|^>>>>>>> upstream/master$
    ga .                                            # if necessary
    gic '1 commit behind'
        git merge --abort                           # undo the merge
    git push


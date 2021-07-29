# git-cherry-pick-tutorial
tutorial for git-cherry-pick

1. `git clone` this repo. 

2. on line 5 in `cherry-pick.txt`, add "This sentence represents the last commit in the tutorial." " and `git add .` and `git commit`. 

3. run `git log` to find the number for the 'wrong' commit:

```
commit 01ec7674c359004493950a17fbe0a42d6b08c2de
Author: Lucia Cerchie <lucia@stepzen.com>
Date:   Thu Jul 29 13:29:03 2021 -0700

    cherry-pick me
```


Run `git cherry-pick 01ec7674c359004493950a17fbe0a42d6b08c2de -x` 

You may need to resolve some conflicts.


helpful flags [from the docs](https://git-scm.com/docs/git-cherry-pick):

-x
When recording the commit, append a line that says "(cherry picked from commit …​)" to the original commit message in order to indicate which commit this change was cherry-picked from. This is done only for cherry picks without conflicts. Do not use this option if you are cherry-picking from your private branch because the information is useless to the recipient. If on the other hand you are cherry-picking between two publicly visible branches (e.g. backporting a fix to a maintenance branch for an older release from a development branch), adding this information can be useful.

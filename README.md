# git-cherry-pick-tutorial
tutorial for git-cherry-pick

1. `git clone` this repo. 

2. on line 5 in `cherry-pick.txt`, add "This sentence represents the last commit in the tutorial." and `git add .` and `git commit`. 

3. run `git log` to find the number for the 'wrong' commit:

```
commit 01ec7674c359004493950a17fbe0a42d6b08c2de
Author: Lucia Cerchie <lucia@stepzen.com>
Date:   Thu Jul 29 13:29:03 2021 -0700

    cherry-pick me
```


Run `git cherry-pick 01ec7674c359004493950a17fbe0a42d6b08c2de -x` 

You may need to resolve some conflicts.

### Optional: 

Learn how to cherry-pick multiple commits!

   - Remove your addition to line 5, save, and `git add .` and `git commit`

   - Make an addition, like "This sentence represents a middle commit", save, and `git add .` and `git commit`

   - Make another addition, like "This sentence represents the latest commit", save, and `git add .` and `git commit`

   - run `git log` to find the number for the first commit, and the latest commit. 


Now, if you want to include the first commit you made (the removal of your addition to line 5) run:

`git cherry-pick commit_number_first_commit^..commit_number_of_last_commit`

If you _don't_ want to include it, run:

`git cherry-pick commit_number_first_commit..commit_number_of_last_commit`, without the carat. 

source: https://stackoverflow.com/questions/1670970/how-to-cherry-pick-multiple-commits

______________________

git cherry-pick A..B
helpful flag [from the docs](https://git-scm.com/docs/git-cherry-pick):

-x
When recording the commit, append a line that says "(cherry picked from commit …​)" to the original commit message in order to indicate which commit this change was cherry-picked from. 
This is done only for cherry picks without conflicts. Do not use this option if you are cherry-picking from your private branch because the information is useless to the recipient. 
If on the other hand you are cherry-picking between two publicly visible branches (e.g. backporting a fix to a maintenance branch for an older release from a development branch), adding this information can be useful.

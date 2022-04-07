### What is the difference between push, fetch, and pull?

* `git push` - Sends changes from a local branch to a remote repository.

* `git fetch` - Gets changes from a remote repo and adds them to your tracking branch.

* `git pull` - Gets changes from a remote branch, adds them to your tracking branch, and merges them into a local branch.




`git push` takes your local branch and checks to see if there is a tracking branch for a remote repository connected to it. If so, changes from your local branch are pushed to the remote branch. This is how code is shared with a remote repository. Think of it as "make the remote branch match my local branch." This will fail if not all the commits in the remote branch are in your local branch. When this happens, your local branch needs to be synchronized with the remote branch with `git pull` or `git fetch` and `git merge`.

Often `git fetch` and `git pull` are described as equivalent. This is not correct. `git fetch` takes your local branch and checks to see if there is a tracking branch for a remote repository. If so, it looks for changes in the remote branch and pulls them into your local tracking branch. It does not change your local branch. To do that, you need to do `git merge` origin/master (for the "master" branch) to merge those changes into your branch. 

`git pull` does a `git fetch` followed immediately by `git merge`. This is often the desired action, but you may prefer to use `git fetch` followed by `git merge` to verify changes before the merge.


# Git as a tool for controlling versions

Things to remember:

1. Do always PULL from the repository before starting your work session

2. The MASTER branch of a repo is a sacred one. Always work from a parallel branch and from there make the pull request. Bear in mind that when creating the branch in your local repository, when trying to push you'll get an error since that branch doesn't exist in the remote repo.

The work process: pull, branch, add, commit, push -> review, approval, merge

3. When finishing the work session, if we want to delete our working branch in the local repo (using git branch /D nameofthebranch), in order to do so in the remote one we have to push using : (:nameofthebranch).

4. Be careful using git reset. With git reset --hard commithash (or git reset--hard HEAD~indexofthecommit, NOT recommended) we move head to any commit, but if the superior commits just exist in the local branch (and not in the remote one) we'll lose those commits forever. If those commits exist in the remote branch, we can pull that branch to return to the original status in our local branch.

5. To update our forked repo to keep the same status as the original, we have to use 'git remote originalrepourl' (called upstream) which we'll use to sync with our remote repo with a push.



Testing inconsistent changes!!

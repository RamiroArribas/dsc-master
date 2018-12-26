RamiroArribas
follow me on: https://github.com/RamiroArribas

## (A)	Sync local with remote, clone your own repo and make changes on it

1.- The first thing we want to do is configuring our git account and sync with our local ecosystem:
	
	git config --global user.name "Username"
	git config --global user.email user@mail.com


2.- Now we have to 'download' the remote repo in our machine (local). In order to do so, we have two ways to proceed:
	
	a. git init projectname
	
What this command does is to create a folder in our machine which name will be the name of the repo. We then move to the created folder and do all the changes we want, and when we are ready we'll proceed to the next step.
	
	b. git clone url
	
This command clones a repo previously created on our account. It creates a folder which name will be the name of the repo, and its contents will be all the files and folders contained inside the remote repo. We then do all the changes we want, and when we are ready we'll proceed to the next step.


3.- When modifying the contents of the repo, our prompt will change:   branchnameinredcolor(+n,-n)  That allows us to keep track of all the changes made (compared with the original state of the repo). When we are satisfied with the changes, we type:
	
	git add 'nameofthefile'

We can do as many additions as we want before pushing (even changes that we add after committing). When the changes are added, our prompt will change to:   branchnameinredcolor(+0,-0)


4.- The next step is to commit our changes:
	
	git commit -m 'Message to send with the commitment'

This command will also change our prompt, so the number of files modified is showed in yellow color:   branchnameinredcolor(+n,-n,#)


5.- When all the files and changes are ready in the commitment, we are ready to push:
	
	git push

If we proceeded through 2.b, the prompt will ask for our account details and the changes will be uploaded.
If we chose the 2.a path, since our repo doesn't exist online, we have to do some extra steps. First, we have to create the repo on the github web (as we would do in the 2.a path). Then, on the teminal, type the following commands:
	
	git remote add origin remote repository URL
	# Sets the new remote
	git remote -v
	# Verifies the new remote URL
	git push origin master
	# Pushes the changes in your local repository up to the remote repository you specified as the origin

Our changes will show now on the online repo, along with the commit messages we wrote.


6.- INCONSISTENCIES(???)

Sometimes, when we push our commit, the prompt will show an error alerting that there are inconsistencies between the remote and the local repo that the program doesn't know how to solve itself (that's a reason why it's SO important to PULL BEFORE starting a new work session).

In order to solve the inconsistencies, if we pull now, the 'corrupted' file will be modified so if we access it (through gedit, for example) we'll see the changes made in local and the ones in remote. We can manually solve the inconsistencies and now push again.


*** TIPS ***
--------------

git status	:	is a command that helps us to keep track of the changes made.

git log		:	is a command that let the user check the commitments already made in the repo and the future commitments that have not still been pushed.

git reset --hard commithash	: use with EXTREME CAUTION. This command let us undo commitments still not pushed. It allows us to move the 'HEAD' but doesn't keep record of the deleted stuff so use it with caution.



## (B)	Fork repo, create a branch to make out changes, pull request

1.- On the github browser, fork the desired repo and clone it as you would do in the (A) guide.


2.- Create a branch in which you will work on the changes to make and avoid modifying important things of the master branch.
	
	git branch nameofthenewbranch

Now we have to move to the new branch to start working:
	
	git checkout nameofthenewbranch


3.- Make all the changes you like as you would do in the 3 and 4 steps of the (A) guide.


4.- Push the changes made as in 5 (A). Since the new branch created in local will not exist online, we have to take extra steps in order to push:

	git push -u origin nameofthenewbranch

5.- On our github webpage we will see the new branch created and we can now do a pull request online. It's always better to add a message or comment on the changes made.


6.- When we have finished our work session, we can delete the branch we created:

	git branch -D nameofthenewbranch

This command will only delete the branch on the local level. To delete the branch on the remote repo:

	git push origin :nameofthenewbranch



*** EXTRA ***
-------------

If we are the ones asked for a pull request, we can check the changes made by the solicitor (ALWAYS CHECK THE CODE BEFORE MERGING THE REQUEST). If everything is OK, we can send a message like 'LGTM' (looks good to me) and merge the changes.


 
## (C)	Update your forked repo to the status of the original

In order to update a previously forked repo, we don't fork it again. Instead, we update our fork following 2 steps: first download the latest status of the original repo in local and second, update the remote repo pushing the changes

1.- In order to download the latest changes to our local repo, we use the following command:

	git remote add upstream urloftheoriginalrepo (***NOT the url of our fork***)

	git remote

When we use the second command, it will show us 'Origin' and 'Upstream'. We have access to pull and push from origin, which will be our fork of the main repo. To pull changes from this main repo, we add a remote "upstream" in our local repo, pointing to this original and pull from it.

Note: "origin" is a clone of our fork repo, from which we pull and push. "Upstream" is a name for the main repo, from where we pull and keep a clone of our fork updated, but we don't have push access to it.


2.- To update our remote-tracking branch we use:

	git fetch upstream

In the simplest terms, git pull does a git fetch followed by a git merge. The command git fetch never changes any of our own local branches under refs/heads, and is safe to do without changing our working copy.


3.- Now we update our master branch, merging upstream (updated) with master (our current local branch):

	git merge upstream/master

Our master branch is now updated, and we can push the changes to our remote repo.


*** TIPS ***
------------

git remote show 'nameoftheremote'	:	shows us the fetch url and the push url of the current remote	

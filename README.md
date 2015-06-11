#How to use git and github?

Here all the steps and git bash code snippet are discussed shortly but I tried to set those step by step. I personally use these steps and those work for me effectively. Hope it will be help full for beginners.

###1. To set name and email address for a repo
	git config --global user.name "mofassel"
	git config --global user.email "mofassel.me@gmail.com"
	
###1.1. To see current username and email info
	git config --list

###2. To initiating git repo we need to create a directory where to set the local repo named gitrepo.git
	git init // or
	git init gitrepo.git // gitrepo.git is your custom name of git repo

###3. When we create a file in git project folder then we need to add it before making commit
	git add . or git add filename
	

###4. Git commit: 
This step help us to set a custom message against all the changes that we made and added in last step before pushing those to remote repo.
	git commit -m "commit message here"
	git commit -a -m "commit message goes here" // it will directly add and commit. it must use with existing file that were commited before not very new file.

###4.1. To delete/remove a commit to switch head to that commit.
NB: All latest commit that were commited after reset commit will be deleted.
	git reset --hard commit_id

###5. We can see status or log message
	git status
	git status -s
	git log
	git log --oneline
	
###6. We can see difference with old file when their is a change
	git diff //before adding it using git add command
	git diff --cached //when it is already added/staged

###7 When our log message will be larger than terminal screen then their will be appeared a message named "end" at the bottom of the screen
	shift+zz //We need to press shift+zz to be get rid of from here.

###8. To create and use ssh key follow this link
	https://help.github.com/articles/generating-ssh-keys

###9. To add remote repo url and to reset remote url
	git remote add origin your-github-project-url
	git remote set-url origin your-new-github-project-url

###10. To upload/push local repo to github repo.
	git push -u origin master

###10.1. To force push a specific commit to remote repo
NB: Sometime you may want to delete a specific commit from remote repo and change the head to its previous commit
	git push origin +commit_id^:master

###11. To download/pull remote repo into local repo folder (note: do pull before each push - recommended)
	git pull origin master

##12. BRANCHING IN GIT
Branching is used to create individual environment for developing any new feature without creating any issue with master branch. While feature is ready then this branch can be be merged to master for production.

###12.1. To see existing branch and create new branch
	git branch
	git branch new_branch_name

###12.2. To enter/switch into new branch
	git checkout new_branch_name


###12.3. To create a new branch and immediately switch to that branch
	git checkout -b new_branch_name

###12.4. To pull or push repo to its respective branch
	git pull origin branchname
	git push origin branchname

###12.5. To make a clone of master branch repo to a new branch (needed for different PC). First checkout into that brach...
	git clone ssh-repo-url

###12.6. To delete a local branch
	git branch -d branchName

###12.7. To delete a remote branch
	git push origin :branchName

###12.8. To import remote branch into local repo with same branch name like remote
	git fetch origin branchName:branchName

###12.9. To merge branch repo with master repo (checkout into master first, need to make additional commit to see changes in master after merge command)
	git merge origin branchName

##13. TAGGING AND RELEASING A REPO IN GIT
Tag is used to create version of the repo and it helps ot release that version while it is ready to release.

###13.1. To create a tag (verision info) Example: tagname-v1.0
	git tag tagname

###13.2. To push a tag to github to release that version to github
	git push origin tagname

###13.3. To create branch from a specific tagname to edit a tag
	git checkout -b newbranch tagname

###13.4. To delete a local tag
	git tag -d tagname

###13.5. To delete a remote tag
	git push --delete origin tagname
	git push origin :tagname

	
I collected and gathered all the codes above to use easily from one place. If anyone wants to update some codes or snippets he/she is most welcome

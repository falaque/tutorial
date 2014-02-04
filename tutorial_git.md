Undo a commit and redo
----------------------
$ git commit ...              (1)
$ git reset --soft 'HEAD^'    (2)
$ edit                        (3)
$ git add ....                (4)
$ git commit -c ORIG_HEAD     (5)
This is what you want to undo

This is most often done when you remembered what you just committed is incomplete, or you misspelled your commit message, or both. Leaves working tree as it was before "reset". (The quotes may or may not be required in your shell)

Make corrections to working tree files.

Stage changes for commit.

"reset" copies the old head to .git/ORIG_HEAD; redo the commit by starting with its log message. If you do not need to edit the message further, you can give -C option instead.



Add remote repository:
----------------------
ex1: 
cd existing_git_repo
git remote add origin git@github.com:caius/foo.git

ex2:

$ git remote add origin ssh://git.amazon.com:2222/pkg/STORMDataAccess
$ git pull
$ git checkout hibernateimpl

Looking committed unpushed changes:
-----------------------------------

* view in current branch
  $ git log origin/master..HEAD
* view the diff in current branch:
  $ git diff origin/master..HEAD

* if you want to see all commits on all branches:
  $ git log --branches --not --remotes


Resetting the staging area:
---------------------------
* change the file:
 $ git add tutorial_git.txt
 $ git status
* reset the staging area
 $ git reset HEAD tutorial_git.txt
 $ git status
* checkout the committed version
 $ git checkout tutorial_git.txt
 $ git status



View the Previous version:
--------------------------------------
$git checkout <hash>
 e.g. git checkout 64ea39c
# this will checkout version corresponding to hash 64ea39c in the branch.

# Return the latest version in the master branch

$git checkout master



History:
========
$ git log
$ git log --pretty=oneline #one line histories
$ git 
#--------some other format
git log --pretty=oneline --max-count=2
git log --pretty=oneline --since='5 minutes ago'
git log --pretty=oneline --until='5 minutes ago'
git log --pretty=oneline --author=<your name>
git log --pretty=oneline --all

#-------graph

$git log --graph

#------- ultimate

$ git log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short


pulling the remote files:
========================
$ git pull origin master

adding file to a repository:(using https://github.com)
======================================================
* add a repository tutorial in github as https://github.com/falaque/tutorial
* run commands:
	$ mkdir tutorial
	$ cd tutorial
	$ git init
 * inside tutorial folder add the file tutorial_git.txt then run command(in folder tutorial):
	$ git add tutorial_git.txt
	$ git commit -m 'adding file' 				
			# commit file
	$ git remote add origin https://github.com/falaque/tutorial.git 
			# Creates a remote named "origin" pointing at your GitHub repository
	$ git push origin master
			# Sends your commits in the "master" branch to GitHub
	(it will ask username and password)


adding a change and committing to a file:
=========================================
* modify the file tutorial_git.txt
* stage it :
	$ git add tutorial_git.txt
* again modify the file tutorial_git.txt
* stage it :
	$ git add tutorial_git.txt
* commit it :
	$ git commit -m "added about viewing pervious changes and commiting"
* push it to remote repo:
	$ git push origin master
	
	

starting with git:(only first time)
===================================
(https://help.github.com/articles/set-up-git)
* Modify the C:\Program Files (x86)\Git\etc\profile file to change $HOME directory.
* use following command:
  - git config --global user.name "Your Name Here"
      # Sets the default name for git to use when you commit
  - git config --global user.email "your_email@example.com"
      # Sets the default email for git to use when you commit
* if using window this is enough.

# BitGame
This is going to be EP1K


Basic Setup

	GitHub

		Create account

			Username

			Email

			Password

	Git

	Install git

		sudo apt-get install git //Debian,Ubuntu

		https://git-scm.com/downloads

	Config

		$ git config --global user.name <Username>

		$ git config --global user.email <Email>

		$ git config --global core.editor <YourPreferredEditor> // Search on google for the appropriate setup for your text editor. -w might need to get added

		$ git config --global credential.helper cache //Cache's your github credentials. Apparently it doesn't work in Windows. Maybe changing cache for wincred ?

		$ git config --global credential.helper 'cache --timeout=<Time>' // <Time> in seconds

		$ git config --global push.default simple

	Edit .gitconfig file and add:

		[alias] 

		tree = log --graph --decorate --pretty=oneline --abbrev-commit //allows for a pretty tree graph when $ git tree

Repository:

	Create:

	1. Create repository on remote (GitHub). //In case of starting a new project

		1. Add name, description, etc.

		2. Copy remote URL.

	2. Create repository on local.

		1. Create folder to store repository.

		2. $ git init //Initializes new empty repository

		3. $ git remote add origin <Remote URL> //Assigns new repository a remote URL

		4. $ git remote -v //Optional, checks that the assignment was done correctly

		5. $ git pull origin master //Syncs local with remote, useful if you've added README or license from github.

		6. $ git push -u origin master //-u, short for –set-upstream, adds upstream reference for master branch.

	Join:

		1. See Repository/Create, skip 1.1.

	Delete:

		1. GitHub/Repository Settings/Danger Zone/Delete this Repository

		2. Delete folder in local //Optional if you want to keep the files. You should at least delete the .git folder within the repo directory.

Commit:

	Basics

		Add File:

			1. Create file

			2. $ git add <Filename>

			3. $ git commit <Filename> -m “Commit Message”

			4. //$ git push

		Delete File:

			Option A:

				1. Delete file from GitHub

				2. $ git pull

			Option B:

				1. $git rm <Filename>

				2. $ git commit -m “Commit Message”

				3. //$ git push

		Modify Contents of File

			1. Open up text editor and make changes.

			2. Save the file.

			3. $ git commit <Filename> -m “Commit Message” //or -am to commit all changes

			4. //$ git push

		Undo previous commit (Undoes the changes in that commit. Does not delete the commit.)

			1. $ git log --graph --all //Find the commit to revert

				1. $ git revert <CommitID>// add -n after revert if you don't want to commit yet.

				2. Commit the revert and other changes

		Move to specific commit (Peek at how the code was after the commit)

			$ git checkout <CommitID> // you can specify a new branch by appedning -b <branchname> to create a new branch from that commit. Otherwise you'll be detached

			From here you can start a new branch from that specific commit.


# About
This directory contains the code and documentation for the fan-made Lawbreakers game.
- View the [Trello](https://trello.com/b/9YLzWwyQ) to stay up to date with development
- Visit the [Discord Channel](https://discord.gg/pVzUfu) for questions and discussion

## Contents
- Getting Started
	- Setting up a working copy
	- Making changes
	- Using the volatile development repository
- To-Do

## Getting Started
Git is the open source distributed version control system that facilitates GitHub activities on your laptop or desktop. Please follow the guides below to set up Git and begin making changes to this repository. For more info, see the [Official Documentation](https://git-scm.com/doc).

### Setting up a working copy
1. [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

2. Set the user name and email for commit transactions using your favorite shell program:   
`$ git config --global user.name "[name]"`  
`$ git config --global user.email "[email address]"`
   
3. Create a personal fork of the project on GitHub:  
<img src="https://i.imgur.com/nBIoqI2.png"><br>

4. Clone the fork to a local directory:  
`$ cd .../Documents/GitHub`  
`$ git clone https://github.com/[your username]/NewStreak.git`
   
5. Create a remote *upstream* to the original repository:    
`$ git remote add upstream https://github.com/ProjectHadronium/NewStreak-official.git`

"volatile" is the name of the NewStreak repo in ProjectHadronium on GitHub.
Your GitHub repo is called "origin".

6. Start making changes!

### Making changes  
1. Navigate to the working directory (use `/` instead of `"\"` which is what you get when you copy-paste the path from explorer):     
`$ cd [file-path]/NewStreak`
   
2. Sync your project with the original:
`$ git checkout master` (if you aren't on master already)
`$ git pull volatile master 
$ git push origin master`

2a. You can also do:
`$ git checkout master` (if you aren't on master already)
`$ git pull volatile master && git push origin master ` 

The "&&" just means you run two lines of code in one line but running them separately achieves the same thing and you can see if things go wrong.

One instance where things can go wrong is if you're on master, you type in "git pull volatile master" and it says "please commit or stash your changes".

2b. To solve this, type in:
`$ git reset --hard`

Then try again and it should accept it.

A good habit would be to not open the project while you're on master. The reason is, you don't want to contaminate your master with changes and then end up deleting them when you pull from volatile (hence the error above). Instead, create a new branch, give it a name you'll remember. I like to use the convention "yymmddbuild#" for example, "181014build" (if it's the first build of the day) but if I have to update and open a new branch for that day, "181014build2", etc. You don't have to do this, just giving an example. 

If you don't remember the branch names, download GitHub desktop, it'll show you all of your branches. 

3. Create a new branch:      
`$ git checkout -b [branch name]`
   
Okay, so this is where it gets confusing. When you're done making changes and you're ready to push those changes to GitHub, you have to add files to a "staging area". Essentially, this is where all the modified files go for getting pushed to master, it's just an area that isn't your branch or master. Only add files that were changed, do not add files you don't need.

4. Stage any changes:     
`$ git add [file-path]/[file name].[extension]`

4a. If you have a folder of several files, do this:
`$ git add [file-path]/[folder name]  `

All of the modified files will be added to the staging area.

5. Switch to master (don't worry, your modified files are still in the staging area):
`$ git checkout master`

When you use these next commands, here's what happens. Your modified files get packaged together into what is known as a "commit", commits have IDs which are useful if you ever fubar your git repository, you can use the commit ID to reset your repo to when that commit was the latest version. The commit then gets pushed to your master, changing it. You then have to push your current version of master to origin (GitHub repo), which will update it with the commit you just created. 

6. Commit the changes and push the branch to your fork, the remote *origin*:  
`$ git commit -m [descriptive message]`   
`$ git push origin [branch name]`
   
7. Create a new pull request (make sure you select YOUR master as "from"):   
<img src="https://i.imgur.com/lR8L0uv.png"><br>

8. Repeat from step 2 of "Making Changes"

Note: All changes are reviewed before merging to this repository. If requested to make further changes, just push them to your branch to automatically update the PR. Please use descriptive commit and pull request summaries to explain your changes!

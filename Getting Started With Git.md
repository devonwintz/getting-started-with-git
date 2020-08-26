
## Commonly Used Git Commands
Before we begin, let us understand **what Git is**. 
Git is a Version Control System (VCS). A VCS is ideally a process management system that manages/maintains changes made to a file or set of files over time.
#

**Downloading & Installing Git**

To get started you can download git from [here](https://git-scm.com/download/win). 

Once, you would have downloaded and installed git on your machine then you can begin using the git commands through the **Git Bash** terminal (*that is usually installed when you install git*) or your **Command Prompt**, if you are using Windows. I personally make use of the git bash terminal.
Before proceeding, please bear with me as I will share
some of my personal opinions / recommendations throughout this guide. On that note, a good habit to develop is to always be knowledgeable about the version of the tool or package that you are using. See below to how this can be achieved using git.

**Getting the Current Version of Git**
```
$ git --version
```
or
```
$ git version
```

**Initializing Your Local Git Repository**
Before you can start using git, you need to initialize the directory that will become your local repository. This could be done by running the following command: 
```
$ git init
```
After you initialize your repository, it is important to add your configuration information for that repository. The good news is, this only has to be done once. As such, you can skip this step if you've already done this before. 

**Adding Your Username & Email**
```
$ git config --global user.name 'username'
$ git config --global user.email 'email'
```
If there is a need to check your current settings (configurations), the following command can be used:

**Checking Your Setting**
```
$ git config --list
```
**Note:** If there is an existing remote repository that you want to use, you will need to download/clone that repository. The following section looks at cloning an existing repository. By doing this, you do not need to run the ***git init*** as this is done through this command.

**Downloading/Cloning An Exisiting Repository Into a New Directory**
If there is a remote repository that you want to work on, you can use the following command to get that repository on to your local machine: 
```
$ git clone <url>
```

**Pushing To An Existing Remote Repository**

If you are not cloning an existing repository but instead want to push to an existing one, you need to add that remote repository by running the following command:
```
$ git add remote <url>
```
It should be noted that this command can be used right before the push command instead of here.

**Working With Branches**
What is a branch?
In short, a branch is a pointer to a specific commit or set of commits. Ideally, as you will see shortly, you commit your changes to a branch which may be your master branch (default branch) or a newly created branch.

**Creating a New Branch**

Before you start working in your local repository, it is recommended that you createa new branch that will be used for all of your edits/changes *(here is my personal recommendation :))*. Essentially, this branch will be merged to your origin/master branch when you are satisfied with your changes. 
```
$ git branch <branch name>
```
Running the above command will not carry you to that newly created branch, thus you need to run:
```
$ git checkout <branch name>
```
But! That is not the only way. You can create a new branch and switch to that newly created branch in one line using the **-b** flag.
```
$ git checkout -b <branch name>
```

At this point, you may want to know how you can check all of your existing branches. This can be done using the following commands.

**List All Existing Branches (Local & Remote)**
```
$ git branch -a
```
**Delete A Local Branch**
```
$ git branch -d <branch name>
```

**Delete A Remote Branch**
```
$ git push origin --delete <branch name>
```

**Rename A Local Branch**
```
$ git branch -m <old branch name> <new branch name>
```

After using the necessary commands above to get started, the following commands are used to add your files to the staging area, commit them, push them to an existing remote repository, perform merges and pull changes (mostly used when you are a part of a team or you are you are using more than one machine). 


**Add File(s) to Staging Area/Index**
```
$ git add <file>    //add specific file(s)
$ git add .        //add files with changes
$ git add *.html/  //add files with a specific extension, in this case .html
```

**Remove File(s) From Staging Area**
```
$ git rm --cached <file>
```

**Check Status of Working Tree**
```
$ git status
```

**Commit Changes in Index**
```
$ git commit -m <message>
```

**Push Local Repository to a Remote Repository**
```
$ git push
```

**Pull Latest Changes From a Remote Repository**
```
$ git pull 
```

**Commonly Asked Questions**
* **What is the difference between 'git fetch' and 'git clone'?**
When you run the clone command, you are ideally copying the entire repository to your local repository. Git fetch on the hand will only fetch the meta-data of all the changes made in the remote repository. An answer like this often leads to the following question. 

* **What is the difference between 'git fetch' and 'git pull'**?
Git pull performs a pull operation, that is, it copies all the changes that have been made to the remote repository since your last pull to your local repository.
Git fetch comes in handy when you want to check the changes that were made before your last pull. 

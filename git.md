# Getting started with Git & GitHub

Acknowledgement: below notes adapted from [EHS](\\root\BCCDC\Groups\EHS\Research%20and%20Surveillance\Projects\GitRepositories\Git_Instructions.pdf).

| Terms | Meaning |
| :-- | :-- |
| ```master``` | local copy, typically refers to your copy |
| ```origin``` | remote copy |

### Quick summary

You create a new **master** copy that will be stored **locally** on your computer whenever you clone from a remote repository via a command like this:
```git clone https://github.com/BCCDC-DSI/CANUE-ML.git```

Note that the command above creates a folder called ```CANUE-ML``` while the one below creates a folder called ```my_phido_dashboard```:
```git clone O:\BCCDC\Groups\Analytics\Data Science and Innovation\Research_Development_Training\Research and Development\Projects\p06_PHIDO_dashboard\GitHub" my_phido_dashboard```

Each new session/day, it is good practice to compare your local copy with the remote one:
```git remote show origin```


If the output mentions:
- ***fast-fowardable***, you can push your changes to remote
- ***local out of date***, your local copy is behind the remote copy

To update your local copy, issue:
```git pull origin master```

To update the remote copy, i.e. "publish" your changes for every interested user of the remote repository, **replace ```pull``` from above with ```push```**; i.e. you **push** the local changes **up** to the remote.


### Typical workflow

A cycle of:
1. Work on your local branch.
2. ```Stage``` and ```Commit``` files that you want to archive/ publish
3. ```Push``` changes to the remote repository when ready.


### Staging 

[To be expanded]



### Making changes and commiting to the ```origin```
```
git add --all
git commit -am "<commit message>"
git push
```
Or run in 1 line:

```
git add-commit -m 'My commit message'
```

**After** having created command alias called ```add-commit``` with this:
```
git config --global alias.add-commit '!git add -A && git commit'
```


### Starting a bare repository from scratch

In [Git Bash](#gitbash), issue commands like this:
```
cd /o/BCCDC/Groups/Analytics/Data\ Science\ and\ Innovation/

mkdir Collaborations
cd Collaborations

mkdir NLP-Overdose
cd NLP-Overdose

git init --bare
```

**Note: The ```bare``` means that the folder will NOT be a ```working``` directory**.

The output will look like:
```
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint:   git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint:   git branch -m <name>
Initialized empty Git repository in //phsabc.ehcnet.ca/root/BCCDC/Groups/Analytics/Data Science and Innovation/Collaborations/NLP-Overdose/
```

Suppose further that you started a folder in your own folder ```U:\myprojects\NLP```, then issue:
```
git remote add origin "U:\myprojects\NLP"
git push origin master
```


### Branch

A branch is a new version, usually for experimentation of a "small" change. 

1. To create new branch named ```beta_version```:
```git branch beta_version```

2. To work in this experimental version, make sure you **switch** to this newly created branch like this:
```git checkout beta_version```

You can also run steps 1-2 in one command:
```git checkout -b beta_version```

To integrate your experimental version with your own **master branch (version)**, you first switch back into your **master**:
```
git checkout master
git merge beta_version
```

If you no longer need the experimental version and wish to delete it, issue:
```
git branch -d beta_version
```

### Summary of commands

[To be completed]

```
git merge
git rebase
git rm
...
```

### Additional resources
- [Summary list created by Rochelle A. on May 28, 2023](https://rochellea.medium.com/your-git-cheat-sheet-commands-to-remember-1381db3f8efd)
- [Merge vs rebase, and other topics](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)

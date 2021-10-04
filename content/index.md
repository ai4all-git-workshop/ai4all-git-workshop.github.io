<style type="text/css">
p { text-align: left; }
</style>

## Apply AI Workshop

### Github & Version Control


## Check-in

- How have you been collaborating?
- How is the experience so far?
- Highly encourage to interrupt.


#### Poll

1. What's your comfort level with command line tools?
2. What operating system (OS) are you using?

Please respond : https://pollev.com/anujpatel447


### Tips
GitHub Student Pack : https://education.github.com/pack

Easy Command Line Explanations : https://explainshell.com



## Agenda

1. Glossary
2. Git Commands and Common Workflows
3. Github



## Glossary


<img src="https://imgs.xkcd.com/comics/git.png"  alt="XKCD"/>


### Version Control
A version control system is a database that holds multiple revisions of a project.


### Revision
A revision _usually_ contains information about;
- What changed?
- Who made those changes?
- When the changes were made?
- Why the change were made?
- What was the state of changed files before the changes were made?


### Git
Git is an open source distributed version control system.


### Repository
A repository in git is a `directory` specific to your project where all your files are stored.
<br/><br/>
The directory that is kept on servers is called `remote repository` while the copy of that on your
local computer is referred as `local repository`.


### Remote
In git, the server that hosts your repositories is referred as `remote`. A git server can host
multiple repositories (example: GitHub).

A single repository can also be stored on multiple git servers which allows it to be a `distributed`
version control.

Demo : GitHub and GitLab


### Branch
A branch is isolated/separated version of repository, it allows team-members to work on tasks
independently. A branch can exists only in local, or only in remote or in both.

The corresponding remote branch for your local branch is also referred to as `upstream`


## Tree
Tree in git refers to a chain of revisions, as we noted all* revisions in version control point to a 
previous revision. That allows git to form a chain.


## HEAD
`HEAD` in git refers to current revision on your git tree. 

DEMO: https://git-school.github.io/visualizing-git/


### Staging
Staging refers to marking changed files in the local repository that ready to be _committed_.


### Commit
Commits is marking staged changes as a new revision and removing them from staging.

A commit creates new `revision` in the repository, which is stored in your `local repository` until 
you send them to `remote repository`.


### GitHub
[GitHub](https://github.com) is one of the most used git hosting services, they provide git servers for free for opensource
and educational collaboration. 

On top of normal git server functionality, github also provides a host of project management and 
developer productivity tools which are at core of most software teams.  

We will be using github for today's workshop, while we will try to focus on git fundamentals, 
if time permits we will do a dive into how you can use 




### Git Commands and Common Workflows


### Basic* Git Commands
<style>
table th:first-of-type {
    width: 50%;
}
table th:nth-of-type(2) {
    width: 50%;
}
</style>
|||
|:---|---:|
|`remote`|`config`|
|`clone`|`init`|
|`fetch`|`status`|
|`pull`|`show`|
|`checkout`|`log`|
|`merge`|`add`|
|`push`|`commit`|


## remote
Used to manage remote servers that will be hosting our `remote repository`
```shell
git remote 

git remote -v

git remote add gitlab \
  "https://gitlab.com/anuj.ai4all/ai4all-git-workshop-github-io.git"
  
git remote rm gitlab 
```


## config
Used to manage configuration of git client on your local machine, you probably used this already.
```shell
git config --global user.name "My Name"
git config --global user.email "my.name@mydomain.com" 
```

There is a huge number of configurations that you can change on your local git client allowing you
to boost your productivity, we will cover some of them at the end if time permits.


## clone
- Copies content from a `remote repository` to a new `local repository`. 
```shell
# Clone and create new directory automatically
git clone "https://gitlab.com/anuj.ai4all/ai4all-git-workshop-github-io.git"
#
# Clone git's own source code from github to my-local-git directory
git clone "https://github.com/git/git" my-local-git  
```


## init
- Used to create a new `local repository` 
```shell
mkdir my-new-project
cd my-new-project
git init 
```


## fetch
- Tells git to retrieve changes from `remote repository` without applying those changes to `local repository`  
```shell
git fetch --all
```


## pull
- Tells git to retrieve changes from `remote repository` AND applies changes from your upstream branch to `local repository`
```shell
git pull
git pull --rebase
```


## checkout
Allows you to either switch to another branch or create a fresh branch from current state.
```shell
git checkout -b new_branch # Creates new branch

git checkout old_branch # Switches state of our repo to old_branch
```


## status
Shows you the current state of your `local repository`.
```shell
git status
```


## merge
Brings other branch's history/revisions into current branch.
```shell

git merge featureB # merges featureB change into our current branch
```


## add
Stages changes made in local repository for commit.
```shell
# Stage a specific file (my-file.txt)
git add my-file.txt 
#
# Stage all contents under my-directory
#
git add my-directory/
#
# Stages all contents under current working directory
#
git add . 
```


## commit
Creates a new revision in your `local repository` on current branch. 
**This doesnt update your `remote repository`**
```shell
#
# Commit staged changes with a message 'Adding new Data'
#
git commit -m "Adding new data"
#
# Commit all changes in your local repo. DO NOT DO THIS!!! 
git commit -am "Adding new data"
```


## log
Shows you revision history of a given branch.


## push
Sends your `local repository` changes to  `upstream` of your branch in `remote repository`.
```shell
git push
```


### Some advanced Git Commands
<style>
table th:first-of-type {
    width: 50%;
}
table th:nth-of-type(2) {
    width: 50%;
}
</style>
|||
|:---|---:|
|`rebase`|`stash`|
|`revert`|`switch`|
|`cherry-pick`|`gc`|


## [Handy Cheatsheet](https://raw.githubusercontent.com/iPraBhu/ADevGuide/master/Resources/Most%20Common%20Git%20Commands%20Every%20Developer%20Should%20Know%20Cheatsheet.PNG)



## GitHUb
- Forks
- Pull Requests
- Issues


## Forks


## Pull Requests


## Issues



### Bonus
- .gitignore file
- Branch Naming Conventions
- Commit messages
- Git Configurations
  - Aliases
  - Merge Tools
- Git Hooks
<style type="text/css">
p { 
  text-align: left;
  font-size: 0.8em;
}
</style>
## AI4ALL GitHub Workshop



### Prerequisite
- Make sure you have followed setup guide and;
  - Installed git client in your local computer
  - Installed Text Editor/IDE of your choice
  - Signed up for GitHub and provided us with your github username



### Setup



### Install git
- Follow : https://github.com/git-guides/install-git
  - Fastest way: https://github.com/git-guides/install-git#install-git-using-github-desktop
- macOS comes pre-installed with `git`
- Windows Users -> https://gitforwindows.org
- Linux Users
  - debian/ubuntu -> ```sudo apt install git-all```
  - fedora -> ```sudo dnf install git-all```



### Configure git
- Open your terminal
  - [Mac Users](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125/mac#:~:text=Open%20Terminal,%2C%20then%20double%2Dclick%20Terminal)
  - Windows Users : Right click on desktop, click `git bash`



## Checkpoint 1
### Is everyone setup with git?



### Clone Workshop Repo
```shell
# Make sure you are in correct directory before cloning
#
git clone https://github.com/ai4all-git-workshop/ai4all-git-workshop.github.io workshop 
```

Go to repo and confirm you are on the default (`main`) branch and have all contents
```shell
cd workshop
git status
```

You should see following in the console;
```shell
On branch main
Your branch is up to date with 'origin/main'.
```



### Clone Workshop Repo (Cntd) 
Check the contents of the repo;
```shell
# Command to list contents of your current directory
ls -ah .
```

You should see something like following;
```shell
.		..		.git		LICENSE		README.md	content 
```



## Checkpoint 2
### Was everyone able to clone the git?



### Create file
Create a new file under content directory with following naming convention
```shell
# For example my file will be created as ./content/anuj4all.md
./content/<YOUR_GITHUB_USER_NAME>.md
```

Introduce and a fun-fact about yourself in the newly created file. 

Update README.md to include a link to newly created file, add a
line after line #8 with following content;
```markdown
|<YOUR_NAME>|[About](content/<YOUR_GITHUB_USER_NAME>.md)|
```



### Create file (cntd.)
Now check status of your working
directory
```shell
git status
```

It should show something like;
```shell
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	content/<YOUR_GITHUB_USER_NAME>.md

no changes added to commit (use "git add" and/or "git commit -a")
```



### Stage files
Now that you have made changes, you want to stage them so that you can commit those to `local repository`
```shell
git add README.md
git add content/<YOUR_GITHUB_USER_NAME>.md
```

Now,
```shell
git status
```
should show something like;
```shell
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   README.md
	new file:   content/<YOUR_GITHUB_USER_NAME>.md
```



### Commit changes
```shell
git commit -m "Added about link for <YOUR_NAME>"
```

You should see an output like;

```shell
[main <SHORT_SHA>] Added about link for <YOUR_NAME>.
 2 files changed, 1 insertion(+), 8 deletions(-)
 create mode 100644 content/<YOUR_GITHUB_USER_NAME>.md
```



### Push your changes
```shell
git push
```

At this point you'll following;
```shell
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 378 bytes | 378.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: error: GH006: Protected branch update failed for refs/heads/main.
remote: error: At least 1 approving review is required by reviewers with write access.
To https://github.com/ai4all-git-workshop/ai4all-git-workshop.github.io
 ! [remote rejected] main -> main (protected branch hook declined)
error: failed to push some refs to 'https://github.com/ai4all-git-workshop/ai4all-git-workshop.github.io'
```



### What??
Well, you tried to push your changes to `remote repository` so that rest of the team can see and use
them. But github refused to accept your changes because of configuration I have setup on the `remote 
repository` that wont allow merging without a pull request. 

One of the best practices is to make sure at least one other team member (preferably whole team but 
it's impractical) reviews changes being made. Usually you work on `feature branch`that contains 
changes for your specific task. Once you're ready with your changes you push your branch and create
a pull request.



### Create a pull request
First, you need to create your own `feature branch` so that you can file the PR, from your terminal execute;

```shell
git checkout -b adding_<YOUR_NAME>_about_info
```
You should see an output;
```shell
Switched to a new branch 'adding_anuj_about_info'
```



### Create a PR (cntd.)
Now let's push the newly created branch to `remote repository`
```shell
git push
```
You should see an output;
```shell
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 378 bytes | 378.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'adding_<YOUR_NAME>_about_info' on GitHub by visiting:
remote:      https://github.com/ai4all-git-workshop/ai4all-git-workshop.github.io/pull/new/adding_<YOUR_NAME>_about_info
remote:
To https://github.com/ai4all-git-workshop/ai4all-git-workshop.github.io
 * [new branch]      adding_<YOUR_NAME>_about_info -> adding_<YOUR_NAME>_about_info
```



### Create a PR (cntd.)
If you notice the output in previous command, github is being nice and giving you a direct link for 
you to simply click so that you can file a Pull Request.

For example in last command
```shell
https://github.com/ai4all-git-workshop/ai4all-git-workshop.github.io/pull/new/adding_<YOUR_NAME>_about_inforemote: Create a pull request for 'adding_<YOUR_NAME>_about_info' on GitHub by visiting:
remote:      https://github.com/ai4all-git-workshop/ai4all-git-workshop.github.io/pull/new/adding_<YOUR_NAME>_about_info
```

Open the link in your web browser and you will be taken to create PR option on GitHub UI. Once there
simply click on `Create pull request` button which will create your PR.



![CREATE_PR](content/create_pr.png) <!-- style="display: block;" -->




### Merge conflicts
Once first PR from us has been merged, you will see that your PRs will not be mergeable because of 
merge conflicts. Merge conflicts are a very common situation arising from the fact that while working
on two separate tasks two branches were created from a single revision (let's call it `revision-a`) 
and both features ended up changing same file (but differently) for their purpose.

Which is exactly our case, where multiple people are adding different values at line #8 in README.md.

To resolve this we use git mergetools, in my demo I will [use IntelliJ IDEA](https://www.jetbrains.com/help/idea/resolve-conflicts.html)
There are other alternatives such as vimdiff, meldmerge, diffmerge, etc.




### Q&A

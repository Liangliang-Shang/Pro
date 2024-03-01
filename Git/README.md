# GIT
* A free and open source distributed version control system(VCS)
# Version
```
@Liangliang-Shang ➜ ~ $ git -v
git version 2.42.1
@Liangliang-Shang ➜ ~ $ git --version
git version 2.42.1
@Liangliang-Shang ➜ ~ $ git version
git version 2.42.1
```
# Help
```
@Liangliang-Shang ➜ ~ $ git help
usage: git [-v | --version] [-h | --help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--config-env=<name>=<envvar>] <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone     Clone a repository into a new directory
   init      Create an empty Git repository or reinitialize an existing one
...
```
# Config
* `git config --global user.name "Liangliang"`
* `git config --global user.email "liangliang.shang@icloud.com"`
# Local repository
## Init
```
@Liangliang-Shang ➜ ~ $ mkdir test && cd test

@Liangliang-Shang ➜ ~/test $ git status			# keep tracking
fatal: not a git repository (or any of the parent directories): .git

@Liangliang-Shang ➜ ~/test $ git init .			# init a repo: ~/test
Initialized empty Git repository in /home/codespace/test/.git/

@Liangliang-Shang ➜ ~/test (main) $ git status
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```
## Config
```
@Liangliang-Shang ➜ ~/test (main) $ git config --local core.editor vim

@Liangliang-Shang ➜ ~/test (main) $ git config --list --show-origin --show-scope
system  file:/etc/gitconfig     init.defaultbranch=main
system  file:/etc/gitconfig     filter.lfs.smudge=git-lfs smudge -- %f
system  file:/etc/gitconfig     filter.lfs.process=git-lfs filter-process
system  file:/etc/gitconfig     filter.lfs.required=true
system  file:/etc/gitconfig     filter.lfs.clean=git-lfs clean -- %f
global  file:/home/codespace/.gitconfig user.name=Liangliang
global  file:/home/codespace/.gitconfig user.email=liangliang.shang@icloud.com
local   file:.git/config        core.repositoryformatversion=0
local   file:.git/config        core.filemode=true
local   file:.git/config        core.bare=false
local   file:.git/config        core.logallrefupdates=true
local   file:.git/config        core.editor=vim

@Liangliang-Shang ➜ ~/test (main) $ cat .git/config
[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
        editor = vim
```
## Working Directory
## Index/Staging Area
## Repository
![](https://pic4.zhimg.com/80/v2-a933cd4bb34672899ffd5a30cccdce03_720w.webp)
## File Status
* **`Untracked`**
  ```
           @Liangliang-Shang ➜ ~/test (main) $ git log
           fatal: your current branch 'main' does not have any commits yet

           @Liangliang-Shang ➜ ~/test (main) $ git reflog
           fatal: your current branch 'main' does not have any commits yet

           @Liangliang-Shang ➜ ~/test (main) $ touch hello2git

           @Liangliang-Shang ➜ ~/test (main) $ git status
           On branch main

           No commits yet

           Untracked files:
             (use "git add <file>..." to include in what will be committed)
                   hello2git

           nothing added to commit but untracked files present (use "git add" to track)
  ```
* **`Cached`**
  ```
           @Liangliang-Shang ➜ ~/test (main) $ git add hello2git 

           @Liangliang-Shang ➜ ~/test (main) $ git status
           On branch main
	
           No commits yet
	
           Changes to be committed:
             (use "git rm --cached <file>..." to unstage)
                   new file:   hello2git
  ```
* **`Committed`**
  ```
           @Liangliang-Shang ➜ ~/test (main) $ git commit -m "<New> ~ hello2git"
           [main (root-commit) bafd70b] <New> ~ hello2git
            1 file changed, 0 insertions(+), 0 deletions(-)
            create mode 100644 hello2git

           @Liangliang-Shang ➜ ~/test (main) $ git status
           On branch main
           nothing to commit, working tree clean

           @Liangliang-Shang ➜ ~/test (main) $ git log
           commit bafd70b48c2343bec9a3fc5eb6b2ad5cf42d405a (HEAD -> main)
           Author: Liangliang <liangliang.shang@icloud.com>
           Date:   Fri Mar 1 12:52:38 2024 +0000

               <New> ~ hello2git

           @Liangliang-Shang ➜ ~/test (main) $ git reflog
           bafd70b (HEAD -> main) HEAD@{0}: commit (initial): <New> ~ hello2git
  ```
* **`Tracked`**
    + **`Unstaged`**
	```
		@Liangliang-Shang ➜ ~/test (main) $ echo "Hello to GIT!" >> hello2git		# Modify a tracked file

		@Liangliang-Shang ➜ ~/test (main) $ git status
		On branch main
		Changes not staged for commit:
 		  (use "git add <file>..." to update what will be committed)
		  (use "git restore <file>..." to discard changes in working directory)
 			modified:   hello2git

		no changes added to commit (use "git add" and/or "git commit -a")

		# `git diff` would show changes in the working tree not yet staged for the next commit
		@Liangliang-Shang ➜ ~/test (main) $ git diff
		diff --git a/hello2git b/hello2git
		index e69de29..0a3b6d2 100644
		--- a/hello2git
		+++ b/hello2git
		@@ -0,0 +1 @@
		+Hello to GIT!
 	```
    + **`Staged`**
	```
		@Liangliang-Shang ➜ ~/test (main) $ git add hello2git 

		@Liangliang-Shang ➜ ~/test (main) $ git status
		On branch main
		Changes to be committed:
		  (use "git restore --staged <file>..." to unstage)
			modified:   hello2git

		@Liangliang-Shang ➜ ~/test (main) $ git diff			# no diff? as `git add` already run!

		@Liangliang-Shang ➜ ~/test (main) $ git diff --cached		# diff between cached and last commit!
		diff --git a/hello2git b/hello2git
		index e69de29..0a3b6d2 100644
		--- a/hello2git
		+++ b/hello2git
		@@ -0,0 +1 @@
		+Hello to GIT!

		@Liangliang-Shang ➜ ~/test (main) $ git diff --staged		# diff between staged and last commit!
		diff --git a/hello2git b/hello2git
		index e69de29..0a3b6d2 100644
		--- a/hello2git
		+++ b/hello2git
		@@ -0,0 +1 @@
		+Hello to GIT!
	```
     + **`Committed`**
	```
		@Liangliang-Shang ➜ ~/test (main) $ git commit -m "<Upd> ~ Add line Hello to GIT!"
		[main 1cdf010] <Upd> ~ Add line Hello to GIT!
 		 1 file changed, 1 insertion(+)

		@Liangliang-Shang ➜ ~/test (main) $ git status
		On branch main
		nothing to commit, working tree clean

 		@Liangliang-Shang ➜ ~/test (main) $ git log
		commit 1cdf010451dc55e1e45167d50aaeefa9f1f9b179 (HEAD -> main)
		Author: Liangliang <liangliang.shang@icloud.com>
		Date:   Fri Mar 1 13:26:01 2024 +0000
		
		    <Upd> ~ Add line Hello to GIT!

		commit bafd70b48c2343bec9a3fc5eb6b2ad5cf42d405a
		Author: Liangliang <liangliang.shang@icloud.com>
		Date:   Fri Mar 1 12:52:38 2024 +0000
		
		    <New> ~ hello2git

		@Liangliang-Shang ➜ ~/test (main) $ git reflog
		1cdf010 (HEAD -> main) HEAD@{0}: commit: <Upd> ~ Add line Hello to GIT!
		bafd70b HEAD@{1}: commit (initial): <New> ~ hello2git
	 ```

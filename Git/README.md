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

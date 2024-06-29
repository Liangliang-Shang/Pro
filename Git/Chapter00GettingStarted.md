# Version
```
$ git -v
git version 2.43.0

$ git --version
git version 2.43.0

$ git version
git version 2.43.0
```

# Help
```
$ git help
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

$ git help config

$ git config --help

$ man git-config
```

# Config
```
$ git config --global user.name "Liangliang"

$ git config --global user.email "liangliang.shang@icloud.com"

$ git config --global --list
user.name=Liangliang
user.email=liangliang.shang@icloud.com
```

# Local Repository
## Init
```
$ mkdir test && cd test

$ git status
fatal: not a git repository (or any of the parent directories): .git

$ git init .
Initialized empty Git repository in /home/imsha/test/.git/

$ git status
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

## Config
```
$ git config core.editor

$ git config --local core.editor vim

$ git config core.editor
vim

$ git config --list  --show-origin --show-scope
system  file:/etc/gitconfig     init.defaultbranch=main
global  file:/home/imsha/.gitconfig     user.name=Liangliang
global  file:/home/imsha/.gitconfig     user.email=liangliang.shang@icloud.com
local   file:.git/config        core.repositoryformatversion=0
local   file:.git/config        core.filemode=true
local   file:.git/config        core.bare=false
local   file:.git/config        core.logallrefupdates=true
local   file:.git/config        core.ignorecase=true
local   file:.git/config        core.editor=vim
```

## Track File
```
$ git log
fatal: your current branch 'main' does not have any commits yet

$ git reflog
fatal: your current branch 'main' does not have any commits yet
```

![](https://git-scm.com/book/en/v2/images/lifecycle.png)

### **`Untracked`**
```
$ touch hello2git

$ git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
       	hello2git

nothing added to commit but untracked files present (use "git add" to track)
```

### **`Cached`**
```
$ git add hello2git

$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
       	new file:   hello2git

```

### **`Committed`**
```
$ git commit -m "<New> hello2git"
[main (root-commit) 28e0dbe] <New> hello2git
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 hello2git

$ git status
On branch main
nothing to commit, working tree clean

$ git log
commit 28e0dbe48ba0aeb993dc55b3e77d3666092b78c7 (HEAD -> main)
Author: Liangliang <liangliang.shang@icloud.com>
Date:   Sat Jun 29 16:34:37 2024 +0800

    <New> hello2git

$ git reflog
28e0dbe (HEAD -> main) HEAD@{0}: commit (initial): <New> hello2git

```

### **`Tracked`**
```
$ echo "Hello to Git!" >> hello2git         # Modify a tracked file

$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
       	modified:   hello2git

no changes added to commit (use "git add" and/or "git commit -a")

# `git diff` would show changes in the working tree not yet staged for the next commit
$ git diff
diff --git a/hello2git b/hello2git
index e69de29..f938a94 100644
--- a/hello2git
+++ b/hello2git
@@ -0,0 +1 @@
+Hello to Git!
```

### **`Staged`**
```
$ git add hello2git

$ git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
       	modified:   hello2git

$ git diff                                  # no diff? as `git add` already run!

$ git diff --cached                         # diff between cached and last commit!
diff --git a/hello2git b/hello2git
index e69de29..f938a94 100644
--- a/hello2git
+++ b/hello2git
@@ -0,0 +1 @@
+Hello to Git!

$ git diff --staged                         # diff between staged and last commit!
diff --git a/hello2git b/hello2git
index e69de29..f938a94 100644
--- a/hello2git
+++ b/hello2git
@@ -0,0 +1 @@
+Hello to Git!

```

### **`Committed`**
```
$ git commit -m "<Upd> hello2git ~ Add Hello to Git!"
[main c6d0817] <Upd> hello2git ~ Add Hello to Git!
 1 file changed, 1 insertion(+)

$ git status
On branch main
nothing to commit, working tree clean

$ git log
commit c6d08173585679436db34c54e49abdf3dff44d11 (HEAD -> main)
Author: Liangliang <liangliang.shang@icloud.com>
Date:   Sat Jun 29 16:47:40 2024 +0800

    <Upd> hello2git ~ Add Hello to Git!

commit 28e0dbe48ba0aeb993dc55b3e77d3666092b78c7
Author: Liangliang <liangliang.shang@icloud.com>
Date:   Sat Jun 29 16:34:37 2024 +0800

    <New> hello2git

$ git reflog
c6d0817 (HEAD -> main) HEAD@{0}: commit: <Upd> hello2git ~ Add Hello to Git!
28e0dbe HEAD@{1}: commit (initial): <New> hello2git

$ git diff 28e0 c6d0
diff --git a/hello2git b/hello2git
index e69de29..f938a94 100644
--- a/hello2git
+++ b/hello2git
@@ -0,0 +1 @@
+Hello to Git!

$ git show
commit c6d08173585679436db34c54e49abdf3dff44d11 (HEAD -> main)
Author: Liangliang <liangliang.shang@icloud.com>
Date:   Sat Jun 29 16:47:40 2024 +0800

    <Upd> hello2git ~ Add Hello to Git!

diff --git a/hello2git b/hello2git
index e69de29..f938a94 100644
--- a/hello2git
+++ b/hello2git
@@ -0,0 +1 @@
+Hello to Git!
```

### Status
```
$ git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
       	new file:   README
       	modified:   hello2git

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
       	modified:   hello2git

Untracked files:
  (use "git add <file>..." to include in what will be committed)
       	LICENSE.txt

$ git status -s
A  README                                   # 'A ' in green - staged new file
MM hello2git                                # 'MM' in green and red - staged and unstaged
?? LICENSE.txt                              # '??' in red - untracked new file

```

### Ignore Files
The rules for the patterns you can put in the .gitignore file are as follows:
  * Blank lines or lines starting with # are ignored.
  * Standard glob patterns work, and will be applied recursively throughout the entire working tree.
  * You can start patterns with a forward slash (/) to avoid recursivity.
  * You can end patterns with a forward slash (/) to specify a directory.
  * You can negate a pattern by starting it with an exclamation point (!).
```
# ignore all .a files
*.a

# but do track lib.a, even though you're ignoring .a files above
!lib.a

# only ignore the TODO file in the current directory, not subdir/TODO
/TODO

# ignore all files in any directory named build
build/

# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# ignore all .pdf files in the doc/ directory and any of its subdirectories
doc/**/*.pdf
```

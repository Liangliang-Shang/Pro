# GIT
* A free and open source distributed version control system(VCS)

![Distributed Version Control](https://git-scm.com/book/en/v2/images/distributed.png)

-----

## Snapshot
* With Git, every time you commit, or save the state of your project, Git basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot. To be efficient, if a file has not changed, Git doesn't store it again, just a link to the previous identical file it has already stored. Git thinks about its data more like a stream of snapshots

![Checkins Over Time](https://git-scm.com/book/en/v2/images/snapshots.png)

-----

## Workflow
1. New or modify files in the working directory
2. Selectively stage just those changes which want to be part of the next commit
3. Do a commit, which takes the files in the stage and stores their snapshot permanently to .git directory

![Working tree, staging area, and Git directory](https://git-scm.com/book/en/v2/images/areas.png)


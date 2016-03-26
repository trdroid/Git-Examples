**To add a Remote Respository**

git remote add origin git@\<repository\>.git

**To add another Remote Repository**

git remote add \<anotherRemoteRepHandlerName\> git@\<repository\>.git

**To Reset a Remote Repository**

git remote set-url origin git@\<repository\>.git

**To push to default Remote Repository**

The repository pointed to by "origin" is the default remote repository

> git push

or

> git push origin 

**To pull from the default Remote Repository**

> git pull

**To push to a Remote Repository pointed by another handler**

> git push \<anotherRemoteRepHandlerName\> master

**To pull from a Remote Repository pointed by another handler**

> git pull \<anotherRemoteRepHandlerName\> master

In case of the following

```
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<branch> master
```

Perform 

git pull <remote> master

git branch --set-upstream-to=origin/master master

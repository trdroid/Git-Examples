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

or 

> git push origin master

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

> git pull <remote> master

> git branch --set-upstream-to=origin/master master

### Viewing information about Github profile for the user "trdroid"

<https://api.github.com/users/trdroid>

Follow the "repos_url" link to get information about the repositories owned by "trdroid"

<https://api.github.com/users/trdroid/repos>


### Cloning a Repository to Surface Book

1) Installed Git

2) Cloning a repository

```sh
MINGW64 /c/onGit
$ git clone git@bitbucket.org:gruprog/c-sharp-tryouts.git
Cloning into 'c-sharp-tryouts'...
The authenticity of host 'bitbucket.org (2401:1d80:1010::152)' can't be established.
RSA key fingerprint is SHA256:zzXQOXSRBEiUtuE8AikJYKwbHaxvSc0ojez9YXaGp1A.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'bitbucket.org,2401:1d80:1010::152' (RSA) to the list of known hosts.
Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

3) Follow the instructions at 

https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/

4) Generate a public-private key pair.

```sh
 MINGW64 /c/onGit
$ ssh-keygen -t rsa -b 4096 -C "email@gmail.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/username/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/username/.ssh/id_rsa.
Your public key has been saved in /c/Users/username/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:<43-Characters> email@gmail.com
The key's randomart image is:
+---[RSA 4096]----+
|         .*      |
|E        = =     |
| o.     o + .    |
|.+.  . . o .     |
|..+ o . S =      |
|oo + o   o o     |
|=.B..   . .      |
|**+B.o o .       |
|+**.+o+.+o.      |
+----[SHA256]-----+
```

5) Copy the public key 

```sh
MINGW64 /c/onGit
$ clip < ~/.ssh/id_rsa.pub
```

6) Add the public key to bitbucket/github

7) Make sure that the ssh-agent is running on the local machine

```sh
MINGW64 /c/onGit
$ eval $(ssh-agent -s)
Agent pid 6524
```

8) Add the private key to ssh-agent running on the local machine

```sh
MINGW64 /c/onGit
$ ssh-add ~/.ssh/id_rsa
Enter passphrase for /c/Users/username/.ssh/id_rsa:
Identity added: /c/Users/username/.ssh/id_rsa (/c/Users/username/.ssh/id_rsa)
```

9) Verify if the private key has be added to the ssh-agent running on the local machine

```sh
MINGW64 /c/onGit
$ ssh-add -l
4096 SHA256:<43-Characters> /c/Users/username/.ssh/id_rsa (RSA)
```

10) Clone the repository now

```sh
 MINGW64 /c/onGit
$ git clone git@bitbucket.org:gruprog/c-sharp-tryouts.git
Cloning into 'c-sharp-tryouts'...
remote: Counting objects: 63, done.
remote: Compressing objects: 100% (50/50), done.
remote: Total 63 (delta 13), reused 0 (delta 0)
Receiving objects: 100% (63/63), 6.69 KiB | 0 bytes/s, done.
Resolving deltas: 100% (13/13), done.
```

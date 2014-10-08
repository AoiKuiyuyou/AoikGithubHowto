# AoikGithubStart
Start guide for Github.

Slightly tiled towards Windows platform.

## Contents
- [Install Git](#install-git)
- [Install TortoiseGit](#install-tortoisegit)
- [Configure TortoiseGit](#configure-tortoisegit)
- [Install Putty](#install-putty)
- [Generate private and public keys](#generate-private-and-public-keys)
- [Add public key to Github](#add-public-key-to-github)
- [Convert private key to Putty's ppk format](#convert-private-key-to-puttys-ppk-format)
- [Create a repository on Github](#create-a-repository-on-github)
- [Find the repository's URLs](#find-the-repositorys-urls)
- [Clone the repository](#clone-the-repository)
- [Prepare a README.md file](#prepare-a-readmemd-file)

## Install Git
Git is available at [here](http://git-scm.com/downloads).

## Install TortoiseGit
GUI git client is handier for me and the one I prefer to use is **TortoiseGit**.

TortoiseGit depends on programs shipped with Git to work. So make sure to [install Git](#install-git) first.

TortoiseGit is available at [here](https://code.google.com/p/tortoisegit/wiki/Download).

After the installation, some menus will be available when you right click a blank area.  
More will be available if you are clicking inside a git repository dir.

## Configure TortoiseGit
###  Name and Email
Each git commit will include the commit author's name and email.  
We need to configure the name and email in TortoiseGit.

Right click a blank area, select menu **TortoiseGit - Settings**.  
![Image](/images/TortoiseGit_SettingsMenu.png?raw=true)

In the **Git** tab, enter your name and email.  
![Image](/images/TortoiseGit_SettingsPage_GitTab.png?raw=true)

## Install Putty
You need to use Putty's **PUTTYGEN** program to [convert private key to Putty's ppk format](#convert-private-key-to-puttys-ppk-format),  
as TortoiseGit only supports this format.

Putty is available at [here](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html).

## Generate private and public keys
The communication between Github's git server and our git client (i.e. TortoiseGit)
is via SSH protocol. And public-private key authentication is required.
Therefore we need to create our public and private keys.

To generate keys, we need program **ssh-keygen**.
Luckily, a **ssh-keygen.exe** program is shipped with Git.  
Assume Git's root dir is **git_root_dir**, the program should be found at
```
git_root_dir\bin\ssh-keygen.exe
```

With the program available, the command to generate keys is:
```
ssh-keygen -t rsa -b 2048 -N "" -C AoiKuiyuyou -f AoiKuiyuyou
```
- **-t rsa**  
  Key type is RSA.  
- **-b 2048**  
  Key length is 2048.  
- **-N ""**  
  Do not password-protect the key.  
- **-C AoiKuiyuyou**  
  Add comments *AoiKuiyuyou* to the end of the public key file.  
- **-f AoiKuiyuyou**  
  Name the private key *AoiKuiyuyou*. The public key will be named *AoiKuiyuyou.pub* accordingly.

## Add public key to Github
Go to [this page](https://github.com/settings/ssh) to add your public key.

## Convert private key to Putty's ppk format
Run program **PUTTYGEN.EXE** installed in [this step](#install-putty).  
Load the private key.  
Save it as Putty's ppk format.

## Create a repository on Github
Go to [this page](https://github.com/new) to create a repository.

The only thing that has to be specified right now is **Repository name**.

## Find the repository's URLs
For example, my Github username is **AoiKuiyuyou**, and my repository's name is **AoikGithubQuickStart**,
so the HTTPS protocol URL for my repository is
```
https://github.com/AoiKuiyuyou/AoikGithubQuickStart
```

The SSH protocol URL for my repository is
```
git@github.com:AoiKuiyuyou/AoikGithubQuickStart.git
```

## Clone the repository
Now that you have found your repository's SSH URL,
you can clone it to local.

Open the dir where you want to put the cloned repository,
right click **Git Clone...**  
![Image](/images/TortoiseGit_CloneMenu.png?raw=true)

Enter your repository's SSH URL and your Putty ppk private key's path  
![Image](/images/TortoiseGit_ClonePage.png?raw=true)

Click **Ok**.

After cloned the repository to local, you should be able to push changes back to remote.

## Prepare a *README.md* file
If a repository has a **README.md** file in its root dir,
Github will render it as part of the repository's page content. (This page's [README.md](/README.md?raw=true) for example.)

A README.md file is written in **GitHub Flavored Markdown**.  

Here are some readings:

- [GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/)
- [Markdown Basics](https://help.github.com/articles/markdown-basics/)
- [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

Here are some WYSIWYG online Markdown editors:

- [Dillinger](http://dillinger.io/)
- [StackEdit](https://stackedit.io/editor)

Here is Github's official tool to render README.md file to html.  
You can use it to render locally if online editors are not preferred.
- [github-markup](https://github.com/github/markup)

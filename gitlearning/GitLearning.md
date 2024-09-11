# Git

## 1 Getting Started

**VCSs**: Version Control Systems  
It allows you to revert selected files(even entire project) back to a previous state,and compare changes over time.

- ez to recover

![image-20240910110507955](GitLearning.assets/image-20240910110507955.png)

**CVCSs:**  Centralized Version Control Systems

![image-20240910190907590](GitLearning.assets/image-20240910190907590.png)

**DVCSs:**  Distributed Version Control Systems

![image-20240910190930011](GitLearning.assets/image-20240910190930011.png)

### history

The relationship between Linux community and the company BitKeeper broke down,this prompted the linux development community to develop their own tool.

the goals they set at first:

- speed
- simple design
- strong support for non-linear development(thousands of parallel branches)
- fully distributed
- able to handle large projects like the linux kernel efficiently (speed and data size)

### feature

- Git thinks about its data more like a stream of snapshots

​	*Git Branching*

- Nearly Every Operation is local

​	*Change it locally first, then upload when you could get to network*

- Git has integrity

​	*Use a hash set (SHA-1) to detect changes*

- Git Generally Only add data

​	*Safe to try everything for you could undo everything*

- The three states
  - modified
  - staged
  - committed

The basic Git workflow goes something like this:

1. modify a file in your working tree
2. selectively stage just those you want to commit ,which adds the changes to the staging area
3. A commit happens, the files in the staging area would store as a snapshot permanently to your Git directory

### Command Line

use Git on the command line  

1. **First-Time Git Setup**

​	view all of your settings and where they are coming form using

```bash
$ git config --list --show-origin
```

2. **Make some settings**

```bash
$ git config --global user.name "xxxx"
$ git config --global user.email xxxxx@xx.com
```

**Set your default branch name as "main"!**

```bash
$ git config --global init.defaultBranch mian
```



## 2 Git Basics

### Getting a Git Repository

Use `git init` to creates a new subdirectory named *.git* that contains all of your necessary repository files --a Git repository skeleton. At this point,nothing in your project is tracked yet.

### Git add

Use this command to tracking New Files 

and also could stage the tracked files which has been modified

 also could marking merge-conflicted files as resolved

### Git commit



------
 表述积累：

**fairly large scope**

**what is xx in a nutshell？**

------
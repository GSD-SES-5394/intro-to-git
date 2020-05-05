# Intro to Git and Github


## What is Git?

Git is a Version Control System (VCS). Version control systems track changes to files and allow you to easily share those file changes with others.  You can see the history of all changes made to each file and who made the change and undo changes to rollback to earlier versions of the file. They are ubiquitous in the software development industry but increasingly used in other engineering fields.

Git was originally written by Linus Torvalds, famous for his development of the Linux operating system. Git is a very powerful VCS but is a little tricky to learn. It has become the most ubiquitous VCS in the software development industry.

## What is Github?

Github is a website that provides a service of hosting git repositories with a very generous free tier of usage. What this means is that it is a free place to store your files with git.

There are many other alternatives to github, but github is quite popular for hobbyists, open source projects, and academia.

## Terminology
This document explains the git concepts and terminology instead of the terminal commands. If you understand the terminology and the concepts, then the commands are easy to google.

![image](https://user-images.githubusercontent.com/2446659/80841413-f9dbbd80-8bc4-11ea-813e-31ed9ea92d07.png)
<!--
digraph G {
  subgraph cluster_0 {
    label = "Repository";
    subgraph cluster_1 {
        rank="same"
        style="rounded"
        M2[label="Commit 2"]
        M1[label="Commit 1"]
        M2 -> M1[dir="back"]
        label="Branch 1"
    }
    subgraph cluster_2 {
        rank="same"
        style="rounded"
        B3[label="Commit 3"]
        B2[label="Commit 2"]
        B1[label="Commit 1"]
        B2 -> B1[dir="back"]
        B3 -> B2[dir="back"]
        label="Branch 2"
    }
  }
}
-->
### Commit
A commit is a set of file changes. A commit can include adding, deleting, or modifying files. Commits also have a message which you can write. Usually the commit message summarizes the changes that were made.

### Branch
A branch is a sequence of commits. The most recent commit is called the **HEAD**. You can name branches whatever you like, but the default branch is named **master**. One of the branches is the **active branch**. Only one branch can be active at a time.

### Repository
A Repository is a collection of branches. The files in a repository represent the latest version of the files for the active branch.

### Git Server
A Git server like github, can hold many git repositories. Your computer can also hold many git repositories. You can download and upload repositories between the git server and your computer. It is also possible to transfer commits between your computer and the git server. Sometimes repositories on a git server are called **remotes**.
![image](https://user-images.githubusercontent.com/2446659/80843061-eb8fa080-8bc8-11ea-8e26-b3fc345e32af.png)
<!--
digraph G {
    subgraph cluster_3 {
        label = "Git Server (Github)"
        s1[label="Repository 1"]
        s2[label="Repository 2"]
    }
       subgraph cluster_1 {
        label = "Your Computer"
        "Repository 1"
    }
}
-->

## Operations

### Clone

Cloning is downloading a copy of a [repo](#repository) from a [git server]($git-server) onto your computer. By default it only downloads the [master branch](#branch). An important point is that by downloading the branch, you not only get the latest version of the file, but you are also downloading the entire history of that file. A repo remembers which server it was cloned from and refers to that server as **origin**.

![image](https://user-images.githubusercontent.com/2446659/80843657-74f3a280-8bca-11ea-87f9-2e6bc4cdf2e0.png)
<!--
digraph G {
    rankdir="LR"
    subgraph cluster_3 {
        label = "Git Server (Github)"
        subgraph cluster_0 {
            label="Repository"
            s1[label="Master"]
        }
    }
    subgraph cluster_1 {
        label = "Your Computer"
        subgraph cluster_0 {
            label="Repository"
            Master[style="dashed"]
        }
    }
    s1 -> Master[label="Clone"]
}
-->
### Push
Push moves [commits](#commit) from your [active branch](#branch) to the git server. Usually your active branch has a **tracking branch** which is the branch on the server that it will push to by default. If there is no tracking branch for the active branch, then push can create one for you. Sometimes creating a new remote branch by pushing is called "Publish" but that is not a git term.
![image](https://user-images.githubusercontent.com/2446659/80844584-9d7c9c00-8bcc-11ea-8c43-5cc5a9080e4c.png)
<!--
digraph G {
    rankdir="LR"
    subgraph cluster_3 {
        label = "Git Server (Github)"
        subgraph cluster_0 {
            label="Repository"
            s1[label="Tracking Branch"]
        }
    }
    subgraph cluster_1 {
        label = "Your Computer"
        subgraph cluster_0 {
            label="Repository"
            c1[label="Active Branch"]
        }
    }
    s1 -> c1[label="Push" dir="back"]
}
-->

### Pull
Pull moves [commits](#commit) from the [git server](#git-server) to your computer, from the tracking branch to your [active branch](#branch).
![image](https://user-images.githubusercontent.com/2446659/80844678-de74b080-8bcc-11ea-9ba1-59b239db5221.png)
<!--
digraph G {
    rankdir="LR"
    subgraph cluster_3 {
        label = "Git Server (Github)"
        subgraph cluster_0 {
            label="Repository"
            s1[label="Tracking Branch"]
        }
    }
    subgraph cluster_1 {
        label = "Your Computer"
        subgraph cluster_0 {
            label="Repository"
            c1[label="Active Branch"]
        }
    }
    s1 -> c1[label="Pull"]
}
-->

### Branch
Branch makes a new [branch](#branch) which is a copy of the active branch. This can be done on [repositories](#repository) on your computer or on the [Git server](#git-server). Branching on Github is done through the web interface.

![image](https://user-images.githubusercontent.com/2446659/80845377-9c4c6e80-8bce-11ea-9fc1-d8dd65e37cbc.png)
<!--
digraph G {
    rankdir="LR"
    subgraph cluster_3 {
        label = "Your Computer"
        subgraph cluster_0 {
            label="Repository"
            "Branch 1" -> "Branch 2"[label="Branch"]
            "Branch 2"[style="dashed"]
        }
    }
}
-->

### Merge
Merge moves [commits](#commit) from one [branch](#branch) to another branch. You can either merge local branches on your computer or merge branches on the Git server. Merging branches on Github is done through the web interface. Often instead of merging directly, you can create a **Pull Request** which is asking permission to merge to that branch.

![image](https://user-images.githubusercontent.com/2446659/80845161-13cdce00-8bce-11ea-9f44-7d9fb2ccacc3.png)
<!--
digraph G {
    rankdir="LR"
    subgraph cluster_3 {
        label = "Git Server (Github)"
        subgraph cluster_0 {
            label="Repository"
            "Branch 1" -> "Branch 2"[label="Merge" dir="back"]
        }
    }
}
-->

### Checkout
Checkout switches which [branch](#branch) is the active branch and replaces the files in the [repository](#repository) with the latest versions for that branch.

### Add and Commit

After a file has been created or modified, you need to "add" the change to the **staging area**. The staging area is where we collect file changes to create a new [commit](#commit). After we have added all of the files, then we commit them to the [active branch](#branch) with a commit message. This creates a new commit to the active branch and that commit becomes the new HEAD for that branch.

![image](https://user-images.githubusercontent.com/2446659/80923594-47cdfe00-8d4a-11ea-81a6-9efa0fda86fd.png)
<!--
digraph G {
    rankdir="LR"
    subgraph cluster_3 {
        label = "Your Computer"
        subgraph cluster_0 {
            label="Repository"
            "Modified Files" -> "Staging Area"[label="Add"]
            "Staging Area" -> "Active Branch"[label="Commit"]
        }
    }
}
-->

## Basic Workflow

There is no standard workflow for git. Every company and organization has different policies about how they branch and merge and push. This is one of the simplest ways to use git that is appropriate for a single individual working on a repository by themselves.

![image](https://user-images.githubusercontent.com/2446659/80923543-15240580-8d4a-11ea-8c34-be88d9b58f6a.png)
<!--
digraph G {
    rankdir="LR"
    subgraph cluster_1 {
        label = "Github"
        subgraph cluster_2 {
            label="Repository"
            gm[label=master]
        }
    }
    subgraph cluster_3 {
        label = "Your Computer"
        subgraph cluster_0 {
            label="Repository"
            master -> modified
            modified -> staged [label=add]
            staged -> master [label=commit]
        }
    }
    
    gm -> master [label=clone]
    master -> gm [label=push]
}
-->
1. [Clone](#clone) a repo from github.
2. modify a file.
3. [add](#add-and-commit) the file to stage the change and commit the change to master
4. [push](#push) your commit to github

## Collaboration Workflow

The basic workflow isn't going to work very well if you have multiple people working in the same repo and reviewing changes before they are merged into master. So something like this is more typical.

![image](https://user-images.githubusercontent.com/2446659/80923486-c24a4e00-8d49-11ea-987f-3e92124dfd62.png)
<!--
digraph G {
    rankdir="LR"
    subgraph cluster_1 {
        label = "Github"
        subgraph cluster_2 {
            label="Repository"
            gm[label=master]
            gb[label=Bob]
            gb -> "Pull Request"
            "Pull Request" -> gm [label=merge]
        }
    }
    subgraph cluster_3 {
        label = "Your Computer"
        subgraph cluster_0 {
            label="Repository"
            master -> Bob [label=branch]
            Bob -> modified
            modified -> staged [label=add]
            staged -> Bob [label=commit]
        }
    }
    Bob -> gb [label=push]
    gm -> master [label="clone"]
}
-->
1. [Clone](#clone) a repo from github
2. [Branch](#branch-1) from master to create a new branch (named for example "Bob")
3. [Checkout](#checkout) Bob
4. Modify a file
5. [Add and commit](#add-and-commit) your change to "Bob"
7. [Push](#push) "Bob" to the github server (creating a new tracking branch on the server). The tracking branch is also named "Bob".
8. Create a Pull request from "Bob" to master on the github server. This is usually the point where your code change can be reviewed.
9. Complete the Pull Request by [merging](#merge) to master
10. [Checkout](#checkout) master on your computer
11. [Pull](#pull) to get the changes into your copy of master.

If someone provides feedback during your pull request that requires you to make a change, you can make additional changes to the PR using steps 4-7.

In this workflow, you never push to master. In fact you can configure your repo to disallow anyone to push directly to master. The only way to get code into master is through a pull request.

You might find it helpful to perform steps 4-7 frequently. This means that even if your computer has a catastrophic failure you would still have a backup of the latest version of all of your files on the server. It also allows others to see what you are doing so you can easily collaborate with others.


# Questions

## Can I undo a commit?

Under normal circumstances, I recommend that you do not. Its easier to look back in the history of the file and make a new commit that puts the file back the way you want it. But for mistakes like when you commit to the wrong branch sometimes it is necessary. The command is named reset.

## Can I remove a commit from a branch on the server?

Yes. A `push --force` can remove commits as well as add commits. But I would avoid doing this when possible. You can lose work.

## What if two people change the same file?

Don't do that. Git will attempt to merge the changes and for text files it may succeed. Other file types will always fail and ask you to resolve the conflict before merging.


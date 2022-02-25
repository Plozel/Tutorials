
<img src="misc/images/git.png" width="40%" height="40%">

Git is a version control system used by developers around the world.  <br>
It allows us to manage projects, track changes to files, and go back to a specific version of those files, at any point in time.

## Setup
#### <ins> Varifying Git is installed: <ins />

```
git --version
```

All is well if it returns details about your Git version.
Otherwise, you probably need to install Git.

#### <ins> Configuring Name & Email: <ins />

Git uses our email and user name as identifiers to keep track of who has made what changes.

```
git config --global user.name "Your Name"
git config --global user.email "Your Email"
```

## Repositories

A repository is a container for a project that is tracked by Git.
  
You typically obtain a Git repository in one of two ways: <br>
* You can take a local directory that is currently not under version control, and turn it into a Git repository, or <br>
* You can clone an existing Git repository from elsewhere.
  
In either case, you end up with a Git repository on your local machine, ready for work. <br> <br>
  
<ins> Initializing a Repository in an Existing Directory: <ins />

If you have a project directory that is currently not under version control and you want to start controlling it with Git, you first need to go to that project’s directory.
```
cd your_proj_directory
git init
```
  
This creates a new hidden subdirectory named .git that contains all of your necessary repository files — a Git repository skeleton. <br>
At this point, nothing in your project is tracked yet.

## Staging and committing code

The git commit command creates a commit, which is like a snapshot of your repository. <br>
Commits should be made often, based on logical units of change. <br>
Over time, commits should tell a story about the history of your repository and how it came to be the way it is now. <br>
In addition to the content and message, commits include a lot of metadata, such as the author and timestamp. 
  
#### <ins> Inspecting a repository <ins />

Git status displays the state of the working directory and staging area. <br>
You can see which changes have been staged (to stage a file is simply to prepare it finely for a commit),<br>
which haven't, and which files aren't being tracked by Git.
```
git status
```

#### <ins> Staging files: <ins />
  
From the project folder, we can use the **git add** command to add our files to the staging area, which allows them to be tracked. <br>
We can add a specific file to the staging area with the following command: <br>
```
git add jupy_nb.ipynb
```
Furthermore, you can list multiple files in order to add them all together, or you can use `git add .` to add all files in the repository into the staging area.
  
```
git branch -m master main
```
definition of commit

```
touch index.html
git status
```

```
git add index.html
```
```
git status
```

```
git commit -m "Create index.html"
```


```
git status
```


```
git log
```

make changes and show how the status looks now


```
git checkout <commit hash>
```

# Branches

```
git branch oren_branch
```

```
git checkout oren_branch
```

```
git merge oren_branch
```

<img src="misc/images/github.png" width="40%" height="40%">

Github let us share our repositories with others, make colabrations and publish our work online.

# Creating a new GitHub repository





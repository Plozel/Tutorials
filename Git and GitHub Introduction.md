
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

#### <ins> Configuring Name & Email <ins />

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
  
In either case, you end up with a Git repository on your local machine, ready for work. <br>
  
<ins> Initializing a Repository in an Existing Directory <ins />

If you have a project directory that is currently not under version control and you want to start controlling it with Git, you first need to go to that project’s directory.
```
cd your_proj_directory
git init
```
  
This creates a new hidden subdirectory named .git that contains all of your necessary repository files — a Git repository skeleton. At this point, nothing in your project is tracked yet.

## Staging and committing code
  
The git commit command creates a commit, which is like a snapshot of your repository. Commits should be made often, based on logical units of change. Over time, commits should tell a story about the history of your repository and how it came to be the way it is now. In addition to the content and message, commits include a lot of metadata, such as the author and timestamp. 
```
git status
```
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





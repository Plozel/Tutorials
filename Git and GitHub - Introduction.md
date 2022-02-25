
<img src="misc/images/git.png" width="40%" height="40%">

Git is a version control system used by developers around the world.  <br>
It allows us to manage projects, track changes to files, and go back to a specific version of those files, at any point in time.

## Common Git workflow

* Initialize a repository
* Create branches
* Edit files
* Add and commit changes
* Merge sub-branch into the main branch.

## Setup
#### <ins> Varifying Git is installed: <ins />

```
git --version
```

All is well if it returns details about your Git version. <br>
Otherwise, you probably need to install Git ([Click here for an installation guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git))

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

The `git commit` command creates a commit, which is like a snapshot of your repository. <br>
Commits should be made often, based on logical units of change. <br>
Over time, commits should tell a story about the history of your repository and how it came to be the way it is now. <br>
In addition to the content and message, commits include a lot of metadata, such as the author and timestamp. 
  
Before we'll start to commit our files we need to know a bit more.
  
#### <ins> Inspecting a repository <ins />

The `git status` commaned displays the state of the working directory and staging area. <br>
You can see which changes have been staged (to stage a file is simply to prepare it finely for a commit),<br>
which haven't, and which files aren't being tracked by Git.
```
git status
```

#### <ins> Staging files: <ins />
 
First, let's create a file to be used as an example (you are welcome to use your own files).
```
touch jupy_nb.ipynb
```
From the project folder, we can use the `git add` command to add our files to the staging area, which allows them to be tracked. <br>
We can add a specific file to the staging area with the following command: <br>

```
git add jupy_nb.ipynb
```
We can run now `git status` and inspect our new unstaged file
  
Try to run `git status` again and see how the status had changed.
  
Furthermore, you can list multiple files in order to add them all together, or you can use `git add .` to add all files in the repository into the staging area.
  
Now, before we do our first commit, run the following (We'll see why later):
```
git branch -m master main
```

Finally, we commit the files which are in the staging area:
  
```
git commit -m "Commit message"
```

#### <ins> Commit history <ins />
You can view all the commits made to our project by running the following command:  
```
git log
```

#### <ins> Ignoring files <ins />

Put files you don't want to be tracked in the `.gitignore` file.
  
## Branching
  
Branching means you diverge from the main line of development and continue to do work without messing with that main line.

We can then add new (experimental, unfinished, and potentially buggy) features in separate branches without touching the 'official' version of the code (which is usually kept on the master branch).  
  
#### <ins> Creating a New Branch: <ins />

```
git branch oren_branch
```
  
#### <ins> Switching Branches <ins />
To switch to an existing branch, you run the git checkout command. Let’s switch to the new testing branch:
```
git checkout oren_branch
```

#### <ins> Merging branches <ins />

When you want to implement the changes you made to an individual branch to another branch, you can merge branches.

Once you have fully implemented and tested a new feature in your code, you should merge it into the stable branch of your project (which is usually the master branch).

To merge the changes from a different branch into your current branch, you can use this command:
```
git merge oren_branch
```

#### <ins> Deleting branches: <ins />

```
git branch -d oren_branch
```

<img src="misc/images/github.png" width="40%" height="40%">

GitHub is a hosting platform for Git repositories that let us share our repositories with others, make colabrations and publish our work online.

## Common GitHub workflow

* Initial a repository
* Create branches
* Edit files
* Add and commit changes
* Push local branch to the remote github repository
* Merge sub-branch into the main branch locally/remotely.


[Click here for GitHub official "Get Started Guide"](https://docs.github.com/en/get-started/quickstart/hello-world#introduction)

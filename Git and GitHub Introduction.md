# Git

Git is a version control system used by developers around the world. 
It allows us to manage projects, track changes to files, and go back to a specific version of those files, at any point in time.

# Varifying Git is installed

```
git --version
```

If it returns details about your Git version, then everything is ok :)
If not, you probably should install Git.

# Configuring Name & Email

Our email and user name serve as identifiers to let git know who has made what changes.

```
git config --global user.name "Your Name"
git config --global user.email "Your Email"
```

# Repositories

A repository is a container for a project that is tracked by Git.

* Local repository -

* Remote repository -

Everytime you want to use git on a project you'll need to initalize a repository.

```
cd your_proj_directory
git init
```

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


# GitHub

Github let us share our repositories with others, make colabrations and publish our work online.

# Creating a new GitHub repository





# Git Cheat Sheet
A collection of handy Git commands and snippets.

### Git Config
Setting up Git for the first time.

Setting up user name:
```
git config --global user.name "<user_name>"
```

Setting up user email:
```
git config --global user.email "<user_email>"
```

Setting up default editor:
```
git config --global core.editor "<editor_name>"
```

### Working with Git
Initializing a Git repository:
```
git init
```

Cloning a remote repository:
```
git clone <remote_repo_url>
```

Adding files to staging area:
```
git add <file_name>
```

Adding all files to staging area:
```
git add .
```

Committing changes:
```
git commit -m "<commit_message>"
```

Pushing changes to remote repository:
```
git push
```

Pulling changes from remote repository:
```
git pull
```

Checking status of repository:
```
git status
```

Checking commit history:
```
git log
```

### Branching
Creating a new branch:
```
git branch <branch_name>
```

Switching to a branch:
```
git checkout <branch_name>
```

Creating a new branch and switching to it:
```
git checkout -b <branch_name>
```

Deleting a branch:
```
git branch -d <branch_name>
```

Merging a branch into the current branch:
```
git merge <branch_name>
```

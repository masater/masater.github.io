# Introduction to GitHub

## Git
Git is a programm that handles the complex development workflow of code. Often code is developed in groups, and different people changing different things would constantly break everything, while having exactly one person writing code at any given time would slow down development and complicated everything.
This is solved by git - it allows you to branch, develop, test and merge your code in a safer way, while allowing multiple people work on the same code base, and it tracks and backs up changes such that you in principle can go back to a previous, working version.

## GitHub, GitLab, BitBucket, SourceFrog
These are all webhosted git services, hosting, tracking and backing up your code, while offering further integration tools and services.
To effictivly use them, you should have git installed.
While most of the following is applicable to all services with slight adaptations, the following will focus on GitHub syntax / examples.

## Setting up Git
Make sure git is installed.
Setup user, and Email:

```bash
git config --global user.name "Ernest Rutherford"
git config --global user.email "erutherford@example.com"
```

Next set up a ssh key. To check whether you already have a ssh key saved type:
```bash
ls -al ~/.ssh
```
If you have none, you can creat aa ed25519 ssh key, or a rsa ssh (outdated) key via
```bash
ssh-keygen -t ed25519 -C "erutherford@example.com"
```

```bash
ssh-keygen -t rsa -b 4096 -C "erutherford@example.com"
```
you will be asked to save the key in a file and enter a passphrase.

If something seems off, you can check whether the ssh agent is running via:
```bash
eval "$(ssh-agent -s)"
```
Now add the ssh key to the agent and copy the keay via "cat":
ed25519:
```bash
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub
```
rsa:
```bash
ssh-add ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub
```

Next log into github and unde Settings > SSH and GPG add the key and name it (good practice to maintain an overview).

## git Commands
### (Branch) Control and Navigation
Clone a Repo:
```bash
git clone git@github.com:username/repository.git
```
Creates a local repo copy with the entire history of the original.

Branch and switch to new Branch:
```bash
git checkout -b feature-branch
```
"-b" -> create branch
"checkout" -> go to feature

View all branches in your Repo:
```bash
git branch
```
### Applying Changes

Stage all Changes for next commit:
```bash
git add .
```
Commit all staged changes __locally__ along with short description
```bash
git commit -m "Brief Description"
```
"-m" -> message

Push new branch onto GitHub Repo:
```bash
git push origin feature-branch
```

Update local Repo with Updates from remote GitHub Repo. The following command fetches and merges changes from the specified branch on GitHub into your current branch:
```bash
git pull origin feature-branch
```

Merge feature-branch into current branch (use "git checkout main" to go to main branch):
```bash
git merge feature-branch
```
If Conflicts occur git will tell you. Open the conflict files and stage resolved files with "git add" and then commit soved files ("git commit").
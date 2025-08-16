

# Git \& GitHub Complete Beginner Guide


***

## 1. What is Git?

- Git is a distributed version control system.
- Tracks changes in files, supports collaboration, allows “undo.”
- Works locally; syncs with remote hosts (like GitHub).

***

## 2. What is GitHub?

- GitHub is a website that hosts Git repositories online.
- Enables cloud backup, sharing, and project collaboration.
- You use Git locally and GitHub as the remote.

***

## 3. Setting Up

### a. **Install Git**

- Download from: [git-scm.com](https://git-scm.com/)
- Install with default settings.


### b. **Configure Git for the First Time**

```sh
git config --global user.name "selvaneyas01-cpu"
git config --global user.email "your_email@example.com"
```

These set your author info for all future commits.

***

## 4. Creating a GitHub Account

- Go to [GitHub.com](https://github.com/)
- Click “Sign Up,” enter email, username, and password.
- Confirm your email and log in.

***

## 5. Starting a Project: Local Git

### a. **Create a Project Folder**

```sh
mkdir my-first-project
cd my-first-project
```


### b. **Initialize Git Repository**

```sh
git init
```


### c. **Add Files \& First Commit**

- Create or copy files into the folder.

```sh
git status                # Shows changes
git add filename.txt      # Stages a specific file
git add .                 # Stages all files
git commit -m "Initial commit"
```


***

## 6. Working With Repositories

### a. **Check Status \& History**

```sh
git status
git log
```


### b. **See File Changes**

```sh
git diff                  # Shows unstaged changes
git diff --staged         # Shows changes to be committed
```


***

## 7. Connecting to GitHub (Remote)

### a. **Create a Repo on GitHub**

- Click “New” repository (top right).
- Name it \& leave “Initialize with README” unchecked if you already have local commits.


### b. **Connect Local to Remote**

For HTTPS:

```sh
git remote add origin https://github.com/YourUsername/my-first-project.git
git branch -M main
git push -u origin main
```

If prompted, use your GitHub username and a **Personal Access Token** (not password).

For SSH:

```sh
# (After adding your public SSH key to GitHub)
git remote add origin git@github.com:YourUsername/my-first-project.git
git branch -M main
git push -u origin main
```


***

## 8. Branching

### a. **Create and Switch Branch**

```sh
git branch feature-branch   # Creates new branch
git checkout feature-branch # Switches to it
```

Or both at once:

```sh
git checkout -b feature-branch
```


### b. **Merge a Branch**

```sh
git checkout main
git merge feature-branch
```


### c. **Delete a Branch**

```sh
git branch -d feature-branch
```


***

## 9. Undoing and Recovering

### a. **Undo Uncommitted Changes to A File**

```sh
git checkout -- filename.txt
```


### b. **Undo Last Commit (Keep Changes)**

```sh
git reset --soft HEAD~1
```


### c. **Undo Last Commit (Discard Changes)**

```sh
git reset --hard HEAD~1
```


### d. **Revert a Commit (Create a New Commit that Reverses)**

```sh
git revert <commit-hash>
```


### e. **Recover Deleted Files Before Commit**

- If deleted:

```sh
git checkout -- deletedfile.txt
```


### f. **See All Branches, Commits, States**

```sh
git log --oneline --graph --all
```


***

## 10. Collaborating with Others

### a. **Clone a Repository**

```sh
git clone https://github.com/someuser/somerepo.git
# or using SSH
git clone git@github.com:someuser/somerepo.git
```


### b. **Pull Latest Changes from Remote**

```sh
git pull
```


### c. **Push Local Commits to Remote**

```sh
git push
```


### d. **Resolve Merge Conflicts**

- Edit conflicting files, then

```sh
git add .
git commit
```


***

## 11. Best Practices

- Make small, frequent commits with clear messages.
- Use branches for new features/bug fixes.
- Pull before you push to avoid conflicts.
- Never share your private SSH keys or tokens.

***

## 12. Common Recovery Scenarios

| Scenario | Command | Description |
| :-- | :-- | :-- |
| Undo file edit | `git checkout -- file.txt` | Discards uncommitted changes in file |
| Undo last commit | `git reset --hard HEAD~1` | Reverts last commit, discards changes |
| Revert a commit safely | `git revert <commit-hash>` | Creates a new commit that undoes an earlier one |
| View commit history | `git log --oneline --graph --all` | Visualizes all branches and commits |
| Recover a deleted file | `git checkout -- filename.txt` | Recovers file if it was deleted, but not yet committed |


***

## 13. Learning More \& Help

- [GitHub Docs: Hello World](https://docs.github.com/en/get-started/quickstart/hello-world)
- [learngitbranching.js.org](https://learngitbranching.js.org)
- [Git Cheat Sheet by GitHub](https://education.github.com/git-cheat-sheet-education.pdf)

***

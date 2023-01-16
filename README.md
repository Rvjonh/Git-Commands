# Git Commands

---

![Git and Github](previews/git-github.png "git and github logos")

---

## [General Git Work Flow](#git-work-flow)

> List of concepts useful for keep a good workflow with projects

## [A list of my commonly used Git commands](#configure-user-account)

> Here are some commands that I use frequently, written them out here to remember them or quick access.

## Configure User Account

| Command | Description |
| ------- | ----------- |
| `git config –global user.name ["Username"]` | Sets or Show username |
| `git config –global user.email ["Email"]` | Sets or Show email |

### Getting & Creating Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Basic Snapshotting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes |
| `git rm -r [--cache] [--force] [file-name.txt]` | Remove a file (or folder), Deleting the file from the folder and the repository |
| `git clean [-i│-n]` | Cleans the directory, deletes untracked files |

### To consider in Commits

---

1) **Subject** : Concise summary of what happened
2) **Body**: More detailed explanation
    * What is now different then before?
    * What’s the reason for the change?
    * Is there anything to watch out for / anything particularly remarkable?

---

### `Warning Snapshotting`

| Command | Description |
| ------- | ----------- |
| `git reset [--soft│--mixed│--hard] HEAD~[n]` | Reset or come back deleting 'n' commits (--soft keeps changes) |
| `git revert [id-commit] --no-edit` | Revert some existing commits |

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch "¡Give a proper name!" |
| `git branch -d [branch name]` | Delete a branch |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git branch [--merged│--no-merged]` | Returns branches which has been (--merged) or (--no-merged) in the actual branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it "¡Give a proper name!" |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git checkout [branch name]` | Switch to a branch and put your at the HEAD commit |
| `git checkout [commit_id]` | Put you in that commit |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git merge --abort` | Allows you to cancel merging |
| **`git rebase [other_branch_name]`** | Pass commits from other branch to actual branch `really conflictly` |
| `git stash` | Stash changes in a working directory |
| `git stash clear` | Remove all stashed entries |

### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote -v` | Shows all your remote origin url |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git reflog` | Manage reflog information, shows data about the commits tree  |
| `git diff [source branch] [target branch]` | Preview changes before merging |
| `git diff-tree -r [commit id]` | Check which files have been changed or added in the commit |
| `git ls-tree` | Returns a tree of the folder with many options |
| `git bisect` | Do a binary search in commits which has cause any error |

---
---

## Git Work Flow

| Concept | Description |
| ------- | ----------- |
| **Feature** |It is a Branch in which a new component will be created, it can be a certain activity such as adding a travel calculation or a room section site, these features are developed in a different branch and then they will be passed to a release for later add to the new version of the software. |
|**Ralease**|It is the development stage or process specified to gather the feature or features and carry out their testing in the development of the software, as well as verify that it works correctly and add it to a new version of the software.|
|**Hotfix**|It is the Branch that will be created when errors are detected in the stable versions and they have to be repaired as soon as possible, hence the name hot-fix.|
|**Git ignore**|It is a file called “.gitignore” which contains the files or folders which are ignored when committing or saving changes to avoid filling up the repository with auto generated files.|
|**Git version**|Versioning of type v1.0.0 is generally used; the first value for a new version of the software, the second number for significant changes such as real ones, and the third number for bug fixes known as hotfixes|
|**README**|It is a "REAME.md" type file which specifies several characteristics of the software such as the purpose of the software, its applied technologies, license, among others; it is a simple documentation of the software.|

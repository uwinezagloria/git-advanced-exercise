# Git Advanced Challenges
## Part 1: Refining Git History
### Missing File Fix
``` bash
git status
git log
git add test4.md
git commit --amend -m chore:"Create third and fourth files"
```
### Editing Commit History
``` bash
git rebase -i HEAD~2
```
### Keeping History Tidy - Squashing Commits
``` bash
git rebase -i HEAD~3
squash 209f903 chore: Create another file
chore: Create initial file
```
### Splitting a Commit
``` bash
git reset --soft HEAD~1
git restore --staged test4.md
git commit -m "chore:Create Third file"
git add test4.md
git commit -m "chore:Create Fourth file"
```
### Advanced Squashing
``` bash
git rebase -i HEAD~2
squash 367364b chore: Create fourth file
chore: "Create third and fourth file"
```
### Dropping a Commit
``` bash
touch unwantd.txt
git add unwanted.txt && git commit -m "chore:Unwanted Commit"
git rebase -i HEAD~2
drop 8e1c66b chore:Unwanted Commit
```
### Reordering Commits
``` bash
git rebase -i HEAD~3
```
### Cherry-Picking Commits
``` bash
git branch ft/branch
git checkout ft/branch
touch test5.md
git add test5.md
git commit -m "Implemented test 5"
git checkout main
git cherry-pick 22d0ffd
```
### Visualizing Commit History 
``` bash
git log --graph
```
### Understanding Reflogs 
``` bash
git reflog
```
## Part 2: Branching Basics
### Feature Branch Creation
``` bash
git checkout -b "ft/new-feature"
```
### Working on the Feature Branch
``` bash
echo " this file contain all contents about our new feature" >feature.txt
git add feature.txt
$ git commit -m "Implemented core functionality for new feature"
```
### Switching Back and Making More Change
``` bash
git checkout main
echo "This is the main branch readme file. It introduces the project." > readme.txt
git add readme.txt
git commit -m "updated project readme"
```
### Local vs. Remote Branches
``` bash
git push  -u origin main
git checkout ft/branch
git push -u origin ft/branch
git checkout  ft/new-feature
git push -u origin/new-feature
``` 
### Branch Deletion
``` bash
git branch -D ft/new-feature
```
### Creating a Branch from a Commit

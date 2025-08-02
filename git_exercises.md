# Git Exercises

Idea:me 
The actual work: Cursor

## Basic Exercises (Getting Started)

**1.** Install Git and understand the basics: Git is a version control system that tracks changes in your code, while GitHub is a cloud platform that hosts Git repositories. Run `git --version` to check if Git is installed.

**2.** Clone someone else's project to your computer: `git clone https://github.com/username/repository-name.git`

**3.** Check the status of your working directory to see what files have changed: `git status`

**4.** Make a small change to a file, then stage it for commit: `git add filename.txt` or `git add .` to add all changes.

**5.** Commit your changes with a descriptive message: `git commit -m "Add feature description or fix bug description"`

**6.** Push your changes back to the remote repository: `git push origin main`

**7.** View the commit history to see what changes were made: `git log` or `git log --oneline` for a condensed view.

**8.** See the differences between your current changes and the last commit: `git diff`

**9.** Pull the latest changes from the remote repository: `git pull origin main`

**10.** Initialize a new Git repository in your project folder: `git init`

---

## Intermediate Exercises (Team Collaboration)

**1.** Create a new branch for your feature work: `git checkout -b feature/new-feature-name`

**2.** Switch between different branches: `git checkout branch-name` or `git switch branch-name`

**3.** List all branches in your repository: `git branch` (local) or `git branch -a` (all branches including remote)

**4.** Merge a feature branch back into main: `git checkout main && git merge feature/branch-name`

**5.** Stash your current changes when you need to switch branches quickly: `git stash` and `git stash pop` to restore them.

**6.** View the commit history of a specific file: `git log filename.txt` or `git log -p filename.txt` to see actual changes.

**7.** Undo the last commit while keeping your changes: `git reset --soft HEAD~1`

**8.** Create and push a new branch to remote: `git push -u origin feature/branch-name`

**9.** Delete a branch after merging: `git branch -d feature/branch-name` (local) and `git push origin --delete feature/branch-name` (remote)

**10.** Fetch updates from remote without merging: `git fetch origin`

**Review:** These intermediate commands focus on branching and collaboration workflows. `git checkout -b` and branch management are essential for feature development in teams. `git stash` saves you when you need to quickly switch contexts. `git fetch` lets you see what teammates have done without affecting your work. These commands are used daily in most development teams.

---

## Advanced Exercises (Complex Workflows)

**1.** Perform an interactive rebase to clean up commit history: `git rebase -i HEAD~3` (for last 3 commits)

**2.** Cherry-pick a specific commit from another branch: `git cherry-pick commit-hash`

**3.** Reset your branch to match the remote exactly (dangerous): `git reset --hard origin/main`

**4.** Create a new commit that undoes a previous commit: `git revert commit-hash`

**5.** Search through commit history for specific content: `git log --grep="search term"` or `git log -S "code search"`

**6.** Temporarily save work and apply it to a different branch: `git stash && git checkout other-branch && git stash pop`

**7.** Squash multiple commits into one during merge: `git merge --squash feature-branch`

**8.** View what changes were made in a specific commit: `git show commit-hash`

**9.** Find which commit introduced a bug using binary search: `git bisect start && git bisect good commit-hash && git bisect bad commit-hash`

**10.** Force push after rewriting history (use with extreme caution): `git push --force-with-lease origin branch-name`

**Review:** Advanced commands handle complex scenarios in large teams. `git rebase -i` cleans up messy commit history before sharing. `git cherry-pick` moves specific fixes between branches. `git revert` safely undoes changes in shared branches. `git bisect` helps debug when you don't know which commit broke something. `git reset --hard` and `git push --force-with-lease` are powerful but dangerous - they permanently change history and should only be used on personal branches or with team coordination. These commands are typically used by senior developers and in complex release management scenarios.

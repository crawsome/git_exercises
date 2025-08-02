# Git Exercises

Idea:me 
The actual work: Cursor
# Git Exercises - Real World Training

*Using the popular "first-contributions" repository - a beginner-friendly project designed for learning Git/GitHub workflow*

## Basic Exercises (Getting Started)

**1.** Install Git and understand the basics: Git is a version control system that tracks changes in your code, while GitHub is a cloud platform that hosts Git repositories. Run `git --version` to check if Git is installed.

**2.** Clone the first-contributions training repository to your computer: `git clone https://github.com/firstcontributions/first-contributions.git`

**3.** Navigate into the project and check what files exist: `cd first-contributions && ls` then check the status: `git status`

**4.** Open the Contributors.md file, add your name to the list, then stage the change: `git add Contributors.md`

**5.** Commit your change with a descriptive message: `git commit -m "Add [Your Name] to Contributors list"`

**6.** Create your own fork first on GitHub, then add it as remote and push: `git remote add origin https://github.com/yourusername/first-contributions.git && git push origin main`

**7.** View the commit history to see what changes were made by you and others: `git log --oneline`

**8.** Make another small change to README.md, then see the differences: `git diff README.md`

**9.** Pull the latest changes from the original repository: `git pull https://github.com/firstcontributions/first-contributions.git main`

**10.** Initialize a new Git repository in a test folder: `mkdir my-test-project && cd my-test-project && git init`

---

## Intermediate Exercises (Team Collaboration)

**1.** Create a new branch to add a translation feature: `git checkout -b add-spanish-translation`

**2.** Switch between your translation branch and main: `git checkout main` then `git checkout add-spanish-translation`

**3.** List all branches to see what you and teammates are working on: `git branch -a`

**4.** Create a Spanish translation file, commit it, then merge back to main: `touch README_es.md && git add . && git commit -m "Add Spanish README" && git checkout main && git merge add-spanish-translation`

**5.** You're working on README.md but need to quickly fix a bug in Contributors.md - stash your work: `git stash` (fix the bug, commit), then `git stash pop`

**6.** See who changed the Contributors.md file and when: `git log Contributors.md` or `git log -p Contributors.md`

**7.** You committed a typo in your last commit message - undo it but keep your file changes: `git reset --soft HEAD~1`

**8.** Create a branch for a new language and push it to your fork: `git checkout -b add-french-translation && git push -u origin add-french-translation`

**9.** After your translation branch is merged, clean it up: `git branch -d add-french-translation && git push origin --delete add-french-translation`

**10.** Check what new contributors have been added by teammates without merging yet: `git fetch origin && git log HEAD..origin/main --oneline`

**Review:** These intermediate commands focus on branching and collaboration workflows. `git checkout -b` and branch management are essential for feature development in teams. `git stash` saves you when you need to quickly switch contexts. `git fetch` lets you see what teammates have done without affecting your work. These commands are used daily in most development teams working on features like translations, bug fixes, and new features.

---

## Advanced Exercises (Complex Workflows)

**1.** You made 3 messy commits adding Portuguese translation - clean them up into one neat commit: `git rebase -i HEAD~3` (squash the commits together)

**2.** A critical security fix was committed to main, cherry-pick it to your feature branch: `git cherry-pick a1b2c3d` (where a1b2c3d is the security fix commit)

**3.** Your local branch is completely messed up, reset it to match the remote exactly: `git reset --hard origin/main` (WARNING: destroys local changes)

**4.** Someone accidentally deleted the Contributors.md file in a commit, undo that specific commit: `git revert bad-commit-hash`

**5.** Find all commits that mention "translation" in the message: `git log --grep="translation"` or find commits that added/removed "Contributors": `git log -S "Contributors"`

**6.** You're working on German translation but need to apply those changes to the French branch: `git stash && git checkout add-french-translation && git stash pop`

**7.** You have 5 small translation commits, squash them into one before merging: `git checkout main && git merge --squash add-german-translation`

**8.** Examine exactly what files and lines were changed in a specific commit: `git show a1b2c3d`

**9.** The README.md file broke somewhere in the last 20 commits, find which commit broke it: `git bisect start && git bisect bad HEAD && git bisect good HEAD~20`

**10.** After cleaning up your commit history with rebase, force push to your fork (never do this on shared branches): `git push --force-with-lease origin add-italian-translation`

**Review:** Advanced commands handle complex scenarios in large teams. `git rebase -i` cleans up messy commit history before sharing (common before submitting pull requests). `git cherry-pick` moves specific fixes between branches (useful for hotfixes). `git revert` safely undoes changes in shared branches without rewriting history. `git bisect` helps debug when you don't know which commit broke something (essential for large codebases). `git reset --hard` and `git push --force-with-lease` are powerful but dangerous - they permanently change history and should only be used on personal branches or with team coordination. These commands are typically used by senior developers managing releases, handling complex merges, and maintaining code quality in large open-source projects.
**10.** Force push after rewriting history (use with extreme caution): `git push --force-with-lease origin branch-name`

**Review:** Advanced commands handle complex scenarios in large teams. `git rebase -i` cleans up messy commit history before sharing. `git cherry-pick` moves specific fixes between branches. `git revert` safely undoes changes in shared branches. `git bisect` helps debug when you don't know which commit broke something. `git reset --hard` and `git push --force-with-lease` are powerful but dangerous - they permanently change history and should only be used on personal branches or with team coordination. These commands are typically used by senior developers and in complex release management scenarios.

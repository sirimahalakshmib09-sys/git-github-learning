# Git Cheatsheet

## Starting the day
- `git pull` - download the latest commits from GitHub before I start working.
- `git switch -c <branch-name>` - create a new branch for my task and move onto it.

## While working
- `git status` - check what changed and what is staged.
- `git diff` - see the exact lines I changed before staging.
- `git add <file>` - stage a change for the next commit.
- `git commit -m "Verb + what changed"` - save a snapshot with a clear message.

## Sharing work
- `git push` - upload my commits to GitHub.
- `git log --oneline` - quick view of the history.

## Rules I follow
- Never commit directly to `main`; use a branch for each task.
- Run `git status` and `git diff` before every commit.
- Write commit messages that finish the sentence "This commit will...".
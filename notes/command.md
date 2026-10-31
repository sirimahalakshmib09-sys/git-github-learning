# Git Commands I Learned

## Setup (done once per laptop)
- `git --version` - checks that Git is installed and shows the version.
- `git config --global user.name "..."` - sets the name stamped on all my commits.
- `git config --global user.email "..."` - sets the email stamped on my commits; it should match my GitHub email.
- `git config --global init.defaultBranch main` - makes new repos start with a branch called `main`.
- `git config --global core.editor "code --wait"` - makes Git open VS Code whenever it needs me to edit text.
- `git config --global --list` - shows all my saved Git settings.

## Daily workflow
- `git init` - turns the current folder into a Git repository by creating a hidden `.git` folder.
- `git status` - shows the current branch and which files are untracked, modified or staged.
- `git add <file>` - moves a change into the staging area, ready for the next commit.
- `git commit -m "message"` - saves a snapshot of everything staged, with a message explaining the change.
- `git diff` - shows exactly which lines I changed but have not staged yet.
- `git log` - shows the full history: commit ID, author, date and message.
- `git log --oneline` - shows the history in a short one-line-per-commit format.

## Key ideas
- **Working folder -> staging area -> repository:** I edit files, choose what to include with `git add`, then save it with `git commit`.
- **Untracked** = Git sees the file but does not save its history. **Modified** = a tracked file changed. **Staged** = ready to be committed.
- **HEAD** is Git's "you are here" pointer, usually on the latest commit of my current branch.
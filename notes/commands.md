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

## GitHub and collaboration
- `git remote add origin <url>` - saves the GitHub address under the nickname `origin`.
- `git remote -v` - lists my remotes and their URLs.
- `git push -u origin <branch>` - uploads a branch and remembers the link, so later a plain `git push` works.
- `git pull` - downloads new commits from GitHub and merges them into my branch.
- `git clone <url>` - downloads a full copy of a repo, history included, and sets up `origin`.
- `git fetch --prune` - updates my view of GitHub and forgets branches deleted there.

## Branching and merging
- `git branch` / `git branch -a` - list local branches / all branches including remote ones.
- `git switch <branch>` - move to another branch; `-c` creates it first.
- `git merge <branch>` - bring another branch's commits into the one I'm on.
- `git branch -d <branch>` - delete a merged local branch; `git push origin --delete <branch>` deletes it on GitHub.
- `git log --oneline --graph` - shows the history as a picture with forks and joins.

## Merge conflicts
- A conflict happens when two changes touch the same or neighbouring lines.
- Markers: `<<<<<<<` my side, `=======` divider, `>>>>>>>` incoming side. I edit the file, remove all markers, then `git add` and `git commit`.
- `git merge --abort` cancels a merge and returns to how things were before.

## Undoing mistakes
| Where the mistake is | Command |
|---|---|
| Edited, not staged | `git restore <file>` |
| Staged, not committed | `git restore --staged <file>` |
| Committed, not pushed | `git reset --soft HEAD~1` |
| Committed and pushed | `git revert <commit>` |
- `git stash` / `git stash pop` - shelve unfinished work, then bring it back.
- `git reset --hard <commit>` - dangerous: discards all newer work. Only when I'm sure.
- `.gitignore` lists files Git must ignore, like `.env` secrets. If a secret is ever pushed, revoke the key first.
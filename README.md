# Git and GitHub Learning Journey

**Author:** Siri, Computer Science undergraduate preparing for SDE internships

A hands-on Git and GitHub learning repository, built from scratch in one focused session. Every module was practised in a real terminal, and the commit history, pull requests and notes in this repo are the evidence.

## What I Covered

| Module | Topic | Evidence |
|---|---|---|
| 1 | Setup: install, identity, default branch, editor, noreply email | Commits carry my GitHub noreply address |
| 2 | First repository: `init`, `add`, `commit`, `diff`, `log`, `mv` | First commit `a3b98c6` |
| 3 | GitHub: `remote`, `push`, `pull`, `clone` | Two copies of one repo acting as two teammates |
| 4 | Branching and merging | Fast-forward merge, then branch cleanup |
| 5 | Merge conflicts | Conflict created and resolved by hand, merge commit `3e32b65` |
| 6 | Pull requests and code review | PR #1 with a review comment |
| 7 | Undoing mistakes | `restore`, `reset`, `revert`, `stash`, `.gitignore` |
| 8 | Documentation and assessment | PRs #2, #3 and #4 |

## Repository Structure

- `notes/commands.md`: every command I learned, with explanations
- `notes/cheatsheet.md`: the commands I reach for most
- `notes/exercises.md`: exercises completed, with commit IDs as evidence
- `notes/assessment.md`: written summary of branching, conflicts and undoing mistakes
- `.gitignore`: keeps secrets such as `.env` files out of the repo

## My Workflow

1. `git pull` to start from the latest `main`
2. `git switch -c <branch>` for each task
3. `git diff`, then `git add`, then `git commit` with a verb-first message
4. `git push -u origin <branch>` and open a pull request
5. Review, merge, delete the branch, and sync `main`

## Undo Cheat Table

| Where the mistake is | Command |
|---|---|
| Edited, not staged | `git restore <file>` |
| Staged, not committed | `git restore --staged <file>` |
| Committed, not pushed | `git reset --soft HEAD~1` |
| Committed and pushed | `git revert <commit>` |
| Secret pushed | Revoke the key first, then clean up the history |

## What I Learned

- **Read Git's output line by line.** After I undid a commit with `git reset --soft`, the file stayed staged. Git printed `A notes/temp.txt` when I switched branches, and that line told me something was still wrong.
- **Errors are specific.** `no upstream branch` and `fetch first` look similar but have different fixes: one needs `git push -u`, the other needs a pull before pushing.
- **Privacy matters.** My first push was rejected because my real email would have been published, so I switched to GitHub's noreply address and rewrote my local commits before pushing.
- **Choose the undo tool by where the mistake is.** `reset` is safe only before pushing, and `revert` is the safe choice once others may have the commit.

## What I Will Learn Next

- Interactive rebase and cherry-pick
- `git reflog` for recovering "lost" commits
- Tags and releases
- GitHub Actions for automated tests (CI)
- Branch protection rules and CODEOWNERS
- SSH keys for authentication
- The fork and upstream workflow for open-source contributions
- Conventional commit messages
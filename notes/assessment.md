# Assessment Notes

## Branching
A branch is a separate line of work, so I can build a feature without touching `main`. I create one branch per task, merge it after review, then delete it.

## Merge conflicts
A conflict happens when two people change the same or neighbouring lines. Git stops and asks me to choose, so I edit the file, remove the `<<<<<<<`, `=======` and `>>>>>>>` markers, then add and commit.

## Undoing mistakes
The right undo depends on where the mistake is: `restore` for unstaged edits, `reset --soft` for local commits, and `revert` for commits already pushed.
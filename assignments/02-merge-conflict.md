# Assignment 2: Schedule Clash

## Scenario

Disaster at the Git Gym! While you were updating the class schedule based on member feedback, Coach Jordan went ahead and redesigned the entire schedule on a separate branch (`feature/schedule-redesign`). You both changed the same days and time slots — Monday, Tuesday, and Wednesday all have conflicting edits.

Now you need to merge Jordan's branch into `main` and **resolve the conflicts by hand**. This is one of the most important Git skills — it happens all the time in real projects.

## Your Task

1. Make sure you're on `main` (or wherever you're working from)
2. Try to merge `feature/schedule-redesign` into your current branch
3. Git will tell you there are conflicts — don't panic!
4. Open `schedule.txt` and look for the conflict markers
5. Edit the file to resolve each conflict (pick one version, combine them, or write something new)
6. Remove ALL conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
7. Stage the resolved file
8. Complete the merge with a commit

## Understanding Conflict Markers

When Git can't auto-merge, it puts both versions in the file:

```
<<<<<<< HEAD
This is what YOUR branch has
=======
This is what THE OTHER branch has
>>>>>>> feature/schedule-redesign
```

Your job is to replace this entire block with what the file SHOULD look like. Delete the markers and keep the content you want.

## Useful Commands

| Command | What it does |
|---------|-------------|
| `git merge <branch>` | Start the merge (this will report conflicts) |
| `git status` | See which files have conflicts |
| `git diff` | See the conflict details |
| `git add <file>` | Mark a file as resolved |
| `git commit` | Complete the merge (after all conflicts resolved) |
| `git merge --abort` | Abort the merge and go back to before (escape hatch!) |

## Check Yourself

Open Fork and verify:

- [ ] There's a merge commit with two parents (your branch and `feature/schedule-redesign`)
- [ ] `schedule.txt` has no conflict markers (search for `<<<<` to be sure)
- [ ] The schedule makes sense — no duplicate or overlapping classes
- [ ] `git status` shows a clean working tree

**Tip:** In Fork, the merge commit should show two lines converging into one. Click on it to see which files were changed and how.

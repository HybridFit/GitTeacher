# Assignment 1: New Training Program

## Scenario

The Git Gym is getting requests for a new **HIIT Blast** training program. Coach Alex has asked you to add it to the workout plan. But you shouldn't work directly on `main` — what if your draft isn't ready yet? You need to create a separate branch, do your work there, and merge it back when it's done.

This is the most fundamental Git workflow: **branch, work, merge**.

## Your Task

1. Create a new branch called `feature/hiit-blast`
2. Switch to that branch
3. Open `workout-plan.txt` and add a new HIIT Blast section at the bottom (before the cool-down). Make up 4-5 exercises with sets, reps, and rest times.
4. Stage and commit your changes with a descriptive message
5. Switch back to `main`
6. Merge your branch into `main`
7. Delete the branch (it's been merged, you don't need it anymore)

## Useful Commands

| Command | What it does |
|---------|-------------|
| `git branch <name>` | Create a new branch |
| `git switch <name>` | Switch to a branch |
| `git switch -c <name>` | Create AND switch in one step |
| `git add <file>` | Stage changes for commit |
| `git commit -m "message"` | Commit staged changes |
| `git merge <branch>` | Merge a branch into the current branch |
| `git branch -d <name>` | Delete a branch (safe — only if merged) |
| `git log --oneline` | See commit history (compact) |

## Check Yourself

Open Fork and verify:

- [ ] You can see your merge commit in the history
- [ ] The `feature/hiit-blast` branch no longer exists
- [ ] `workout-plan.txt` on `main` contains your HIIT Blast section
- [ ] The commit graph shows the branch and merge (even if it was a fast-forward)

**Tip:** In Fork, look at the branch sidebar — your deleted branch should be gone. The commit graph should show your work flowing into main.

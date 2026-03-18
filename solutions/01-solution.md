# Solution: Assignment 1 — New Training Program

## Step-by-Step

### 1. Create and switch to a new branch

```bash
git switch -c feature/hiit-blast
```

This creates the branch AND switches to it in one command. Alternatively:

```bash
git branch feature/hiit-blast
git switch feature/hiit-blast
```

### 2. Edit the workout plan

Open `workout-plan.txt` in your editor and add a HIIT section before the COOL-DOWN. For example:

```
HIIT BLAST (20 minutes)
-----------------------
1. Burpees — 30 seconds on, 15 seconds rest
2. Mountain Climbers — 30 seconds on, 15 seconds rest
3. Jump Squats — 30 seconds on, 15 seconds rest
4. Box Jumps — 30 seconds on, 15 seconds rest
5. Battle Ropes — 30 seconds on, 15 seconds rest

Repeat circuit 4 times. Rest 1 minute between rounds.
```

### 3. Stage and commit

```bash
git add workout-plan.txt
git commit -m "feat: add HIIT Blast training program"
```

### 4. Switch back to main and merge

```bash
git switch main
git merge feature/hiit-blast
```

### 5. Delete the branch

```bash
git branch -d feature/hiit-blast
```

The `-d` flag is safe — it only deletes if the branch has been merged. Use `-D` to force-delete (but be careful!).

## What to See in Fork

- The commit graph shows your branch splitting off from main and merging back
- If Git did a "fast-forward" merge (no merge commit), the history will be linear — that's fine and expected when main hasn't changed while you worked
- The branch should no longer appear in the sidebar

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Forgot to switch to main before merging | `git switch main` then merge |
| Committed on main instead of the branch | Use `git reset HEAD~1` to undo, then create the branch |
| Used `-D` instead of `-d` | `-D` force-deletes even unmerged branches — use carefully |

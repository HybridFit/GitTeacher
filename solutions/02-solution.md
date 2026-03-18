# Solution: Assignment 2 — Schedule Clash

## Step-by-Step

### 1. Start the merge

```bash
git switch main
git merge feature/schedule-redesign
```

Git will output something like:

```
Auto-merging schedule.txt
CONFLICT (content): Merge conflict in schedule.txt
Automatic merge failed; fix conflicts and then commit the result.
```

### 2. See what's conflicting

```bash
git status
```

This shows `schedule.txt` as "both modified."

### 3. Open the file and find conflict markers

Look for blocks like this:

```
<<<<<<< HEAD
  07:00 - 08:00  Morning Bootcamp      (Coach Alex)
  10:00 - 11:00  Yoga Flow              (Coach Sam)
  12:00 - 13:00  Lunchtime HIIT         (Coach Alex)
  18:00 - 19:30  Power Hour             (Coach Jordan)
=======
  06:30 - 07:30  Early Bird Bootcamp    (Coach Alex)
  09:00 - 10:00  Yoga Flow              (Coach Sam)
  12:00 - 13:00  Lunchtime HIIT         (Coach Alex)
  17:30 - 18:30  Strength Training      (Coach Jordan)
>>>>>>> feature/schedule-redesign
```

### 4. Resolve each conflict

For each conflict block, decide what the schedule should actually be. Delete the markers and keep what makes sense. For example, you might combine the best of both:

```
  06:30 - 07:30  Early Bird Bootcamp    (Coach Alex)
  10:00 - 11:00  Yoga Flow              (Coach Sam)
  12:00 - 13:00  Lunchtime HIIT         (Coach Alex)
  18:00 - 19:30  Power Hour             (Coach Jordan)
```

Do this for every conflict in the file.

### 5. Verify no markers remain

Search the file for `<<<<` — if you find any, you missed a conflict.

### 6. Stage and complete the merge

```bash
git add schedule.txt
git commit
```

Git will open your editor with a pre-written merge commit message. You can keep it or customize it.

## What to See in Fork

- A merge commit with TWO parent lines converging
- Click the merge commit — it should show the resolved changes to `schedule.txt`
- Both the main line and the `feature/schedule-redesign` line connect to this merge commit

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Left conflict markers in the file | Search for `<<<<` and resolve remaining conflicts |
| Accidentally deleted content from both sides | Check `git diff` and re-resolve if needed |
| Want to start over | `git merge --abort` resets everything to before the merge |
| Committed with markers still in file | `git reset HEAD~1` to undo the merge commit, then fix |

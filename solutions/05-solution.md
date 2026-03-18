# Solution: Assignment 5 — Multitasking Coach

## Step-by-Step

### Part 1: Set Up Feature Work

```bash
# Create and switch to feature branch
git switch -c feature/8-week-program

# Edit workout-plan.txt — add something like this at the bottom:
# 8-WEEK STRENGTH PROGRAM
# =======================
# Week 1: Foundation
# - Day 1: Full body (light weights, learning form)
# - Day 2: Rest
# - Day 3: Upper body focus
# ... (leave it incomplete — you're mid-work!)
```

**Don't commit!** You want uncommitted changes to prove the worktree keeps them safe.

### Part 2: Create the Worktree

```bash
# Create a worktree checked out to main
git worktree add ../git-gym-hotfix main
```

This creates a new directory `../git-gym-hotfix` with a fresh checkout of `main`. Your current directory is untouched.

```bash
# Navigate to the hotfix directory
cd ../git-gym-hotfix

# Create a fix branch
git switch -c fix/client-plan-error

# Edit workout-plan.txt — fix something small
# For example, change "Reps: 8-10" to "Reps: 10-12" for Barbell Squats

# Commit the fix
git add workout-plan.txt
git commit -m "fix: correct rep range for Barbell Squats"
```

### Part 3: Verify and Clean Up

```bash
# Go back to your feature directory
cd ../GitTeacher  # (or wherever your main worktree is)

# Check your uncommitted work is still there
git status
# Should show modified workout-plan.txt with your 8-week program draft

# List all worktrees
git worktree list
```

Output looks like:

```
/path/to/GitTeacher          abc1234 [feature/8-week-program]
/path/to/git-gym-hotfix      def5678 [fix/client-plan-error]
```

```bash
# Remove the worktree when done
git worktree remove ../git-gym-hotfix
```

## What to See in Fork

- Two branches visible: `feature/8-week-program` (with uncommitted changes) and `fix/client-plan-error` (with the fix commit)
- You can open both worktrees as separate repos in Fork to see them side by side
- After removing the worktree, `git worktree list` only shows one entry

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| "Branch already checked out" error | A branch can only be checked out in one worktree at a time — use a different branch |
| Worktree has uncommitted changes when removing | Commit or discard changes first, or use `--force` |
| Confused about which directory you're in | `git worktree list` shows all worktrees and their branches |
| Made changes in the wrong worktree | Check which branch you're on: `git branch --show-current` |

## When to Use Worktrees

| Scenario | Use Stash? | Use Worktree? |
|----------|:----------:|:-------------:|
| Quick 2-minute fix | Yes | Overkill |
| Hotfix while mid-feature | Maybe | Yes |
| Running tests while coding | No | Yes |
| Reviewing a colleague's PR | No | Yes |
| Comparing two versions side by side | No | Yes |
| Forgot to commit before switching | Yes | Overkill |

The key insight: worktrees let you have multiple branches checked out simultaneously in different directories. Stash is a temporary shelf for one set of changes.

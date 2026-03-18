# Assignment 5: Multitasking Coach

## Scenario

You're halfway through designing a new **8-Week Strength Program** on a feature branch. You've got uncommitted changes, half-finished notes — the works. Then a client calls: there's a mistake in their current workout plan that needs fixing NOW.

You could `git stash` your work, switch branches, fix the bug, switch back, and `git stash pop`. But there's a better way: **git worktrees**.

A worktree lets you check out a second branch in a separate directory, so you can work on both things simultaneously without touching your in-progress work.

## Your Task

### Part 1: Set Up Your Feature Work

1. Create and switch to a new branch `feature/8-week-program`
2. Start editing `workout-plan.txt` — add a header for "8-WEEK STRENGTH PROGRAM" with week 1 details
3. **Don't commit yet** — you're mid-work, this is intentional

### Part 2: Create a Worktree for the Urgent Fix

4. Create a worktree for the fix (without leaving your current directory):
   ```
   git worktree add ../git-gym-hotfix main
   ```
5. This creates a new directory `../git-gym-hotfix` checked out to `main`
6. Navigate to that directory
7. Create a branch for the fix: `git switch -c fix/client-plan-error`
8. Fix the "error" in `workout-plan.txt` (change something small, like correcting a rep count)
9. Commit the fix

### Part 3: Clean Up

10. Go back to your original directory
11. Verify your uncommitted feature work is still there, untouched
12. List all worktrees to see both
13. Remove the worktree when you're done with the hotfix

## Useful Commands

| Command | What it does |
|---------|-------------|
| `git worktree add <path> <branch>` | Create a new worktree at the given path |
| `git worktree add -b <new-branch> <path> <start>` | Create worktree with a new branch |
| `git worktree list` | Show all worktrees |
| `git worktree remove <path>` | Remove a worktree (must have clean working tree) |

## Worktrees vs Stash

| | Stash | Worktree |
|---|-------|----------|
| **Speed** | Quick for small context switches | Better for longer parallel work |
| **Risk** | Easy to forget what's stashed | Both branches visible in separate directories |
| **Complexity** | Simple | Slightly more setup |
| **Multiple tasks** | Stash stack gets confusing fast | Each task has its own directory |
| **IDE support** | One project open | Can open both in separate windows |

**Rule of thumb:** Use `stash` for quick 5-minute switches. Use worktrees when you'll be going back and forth, or when the side-task might take a while.

## Check Yourself

Open Fork and verify:

- [ ] `git worktree list` shows two worktrees (or one after cleanup)
- [ ] Your feature branch still has the uncommitted changes
- [ ] The hotfix branch has a clean commit with the fix
- [ ] The two directories have different content (different branches checked out)
- [ ] After removing the worktree, `git worktree list` shows only the main one

**Tip:** In Fork, you should see both branches in the sidebar. You can open the second worktree as a separate repo in Fork (File → Open Repository) to see both side by side.

## Bonus: Worktrees in Real Life

Common uses for worktrees:
- **Hotfixes while developing** — exactly this scenario
- **Running tests on one branch while coding on another** — no more waiting
- **Reviewing a colleague's PR** — check it out in a worktree without disturbing your work
- **Comparing behavior** — run the old and new version side by side

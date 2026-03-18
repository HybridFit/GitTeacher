# Assignment 4: Shift Handover

## Scenario

You've been off for a few days and your colleague coach has been busy. They pushed updates to the `friend/coach-updates` branch — new clients added and the nutrition guide updated with vegetarian options. You need to pull their changes and integrate them into your work.

This simulates the most common real-world Git workflow: someone else pushed changes, and you need to get them into your branch.

## Your Task

1. Make sure you're on `main`
2. Look at what branches exist (including remote ones)
3. Fetch the latest changes from the remote
4. Check out or merge the `friend/coach-updates` branch to see what your colleague did
5. Review their changes — look at the modified files and commit messages
6. Merge their work into `main`
7. Push the updated `main` to the remote

## Useful Commands

| Command | What it does |
|---------|-------------|
| `git branch -a` | List all branches (local and remote) |
| `git fetch` | Download remote changes without merging |
| `git pull` | Fetch AND merge remote changes |
| `git log origin/main..friend/coach-updates` | See commits on the branch |
| `git diff main..friend/coach-updates` | See what changed |
| `git merge <branch>` | Merge a branch into current branch |
| `git push` | Push your local commits to the remote |
| `git push -u origin main` | Push and set upstream tracking |

## What's the Difference?

- **`git fetch`** downloads remote changes but doesn't touch your files. Safe to run anytime — it just updates your knowledge of what's on the remote.
- **`git pull`** is `fetch` + `merge` in one step. Convenient, but you have less control.
- **`git push`** uploads your local commits to the remote for others to see.

## Check Yourself

Open Fork and verify:

- [ ] The merge commit shows `friend/coach-updates` merged into `main`
- [ ] `clients.txt` has the 2 new clients (Ryan Cooper, Aisha Khan)
- [ ] `nutrition-guide.txt` has the new vegetarian section
- [ ] `git log` shows your colleague's commits in the history
- [ ] If you pushed: the remote is up to date (no "ahead of origin" message)

**Tip:** In Fork, use the "Fetch" button to update remote tracking info. You should see `friend/coach-updates` in the remote branches list. After merging, the branch lines should converge.

## Bonus Challenge

If this repo is on GitHub, try creating a **Pull Request** instead of merging locally:

1. Push the `friend/coach-updates` branch to the remote
2. Go to the repository on GitHub
3. Create a Pull Request from `friend/coach-updates` → `main`
4. Review the changes in the GitHub UI
5. Merge the PR

This is how most teams actually integrate changes — through code review.

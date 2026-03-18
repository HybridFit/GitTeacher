# Solution: Assignment 4 — Shift Handover

## Step-by-Step

### 1. Check current state

```bash
git switch main
git branch -a
```

You should see `friend/coach-updates` listed (either local or as `remotes/origin/friend/coach-updates`).

### 2. Review what your colleague did

```bash
git log main..friend/coach-updates --oneline
```

Shows the commits they made:

```
0117611 feat: update nutrition guide with vegetarian options
100087f feat: add new January clients
```

See the actual changes:

```bash
git diff main..friend/coach-updates
```

### 3. Merge their work

```bash
git merge friend/coach-updates
```

This should merge cleanly (no conflicts — they changed different parts of the files than you did).

### 4. Verify the merge

```bash
git log --oneline -5
```

Check the files:

```bash
cat clients.txt    # Should have Ryan Cooper and Aisha Khan
cat nutrition-guide.txt  # Should have vegetarian section
```

### 5. Push to remote (if applicable)

```bash
git push
```

Or if this is the first push:

```bash
git push -u origin main
```

## What to See in Fork

- The merge commit shows two parent lines converging
- Your colleague's commits appear in the history
- `clients.txt` and `nutrition-guide.txt` show the updates
- If you pushed: the remote/origin/main tag moves to the latest commit

## Bonus: Pull Request Workflow

If you want to try the PR approach:

```bash
# Push the branch to remote
git push origin friend/coach-updates

# Create a PR via command line
gh pr create --base main --head friend/coach-updates --title "Add new clients and vegetarian nutrition guide"
```

Then go to GitHub, review the changes, and merge the PR through the web UI.

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| `git fetch` but nothing happened | Fetch downloads data but doesn't merge — use `git merge` next |
| `git pull` gave conflicts | Resolve them like in Assignment 2, then commit |
| Push rejected | Someone else pushed first — `git pull` to integrate, then push again |
| Forgot which branch has the changes | `git log --all --oneline --graph` shows everything |

## Understanding Fetch vs Pull

```
git fetch     →  Download remote changes (safe, no merge)
                  Remote refs updated, but your branch unchanged

git pull      →  Download AND merge in one step
                  Same as: git fetch + git merge origin/main

git push      →  Upload your local commits to remote
                  Fails if remote has commits you don't have (pull first)
```

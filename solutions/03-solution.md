# Solution: Assignment 3 — Clean Up Your Plan

## Step-by-Step

### 1. Switch to the messy branch and review

```bash
git switch feature/messy-plan
git log --oneline
```

You'll see something like:

```
31921d9 final maybe
5eb8c6d WIP saving before lunch
d0e7ed4 oops forgot reps
4b534eb fix typo
0907ce7 more stuff
64f39ad wip
```

### 2. Start interactive rebase

```bash
git rebase -i HEAD~6
```

This opens your editor with:

```
pick 64f39ad wip
pick 0907ce7 more stuff
pick 4b534eb fix typo
pick d0e7ed4 oops forgot reps
pick 5eb8c6d WIP saving before lunch
pick 31921d9 final maybe
```

### 3. Reorganize the commits

Change it to something like:

```
reword 64f39ad wip
squash 0907ce7 more stuff
fixup 4b534eb fix typo
fixup d0e7ed4 oops forgot reps
squash 5eb8c6d WIP saving before lunch
reword 31921d9 final maybe
```

This will:
- Combine commits 1-4 into one (new exercises + their fixes)
- Let you write a new message for that combined commit
- Combine commit 5 with commit 6 (reordering + warm-up)
- Let you write a new message for that too

### 4. Write new commit messages

When Git prompts you, write clear messages like:

- First commit: `feat: add Bulgarian Split Squats and Face Pulls to workout plan`
- Second commit: `feat: enhance warm-up routine and reorder exercises`

### 5. Verify the result

```bash
git log --oneline
```

Should show 2-3 clean commits instead of 6 messy ones.

```bash
git diff main..feature/messy-plan
```

The actual changes should be identical to before — you only changed the history, not the code.

## What to See in Fork

- The branch now has 2-3 commits with clear messages
- Each commit contains logical, grouped changes
- The file content is exactly the same as before the rebase

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Editor is confusing | Set your preferred editor: `git config --global core.editor "code --wait"` (VS Code) |
| Rebase went wrong | `git rebase --abort` to cancel and start over |
| Conflicts during rebase | Resolve them, `git add`, then `git rebase --continue` |
| Want to undo a completed rebase | `git reflog` to find the pre-rebase state, then `git reset --hard <commit>` |

## Understanding `squash` vs `fixup`

- **`squash`** combines commits AND lets you edit the combined message
- **`fixup`** combines commits but throws away the squashed commit's message (keeps the one above)

Use `fixup` for commits that were just fixing mistakes (typos, forgotten files). Use `squash` when both commit messages have useful info.

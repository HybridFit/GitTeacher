# Assignment 3: Clean Up Your Plan

## Scenario

You've been working on an expanded workout plan on the branch `feature/messy-plan`. It works great, but... look at that commit history. "wip", "more stuff", "fix typo", "oops forgot reps" — you wouldn't want to merge that into `main` for everyone to see.

**Interactive rebase** lets you rewrite history on your branch before merging. You can squash commits together, reword messages, and make it look like you knew what you were doing all along.

## Your Task

1. Switch to the `feature/messy-plan` branch
2. Look at the commit log to see the messy history
3. Start an interactive rebase going back to where the branch diverged from main
4. In the editor that opens, reorganize the commits:
   - **Squash** the typo fix and "oops" commits into the commits they fix
   - **Reword** the remaining commits to have clear, descriptive messages
   - Your goal: turn 6 sloppy commits into 2-3 clean ones
5. Save and close the editor, then handle each step Git presents
6. Verify the result with `git log`

## Understanding Interactive Rebase

When you run `git rebase -i`, an editor opens with a list of commits:

```
pick abc1234 wip
pick def5678 more stuff
pick ghi9012 fix typo
pick jkl3456 oops forgot reps
pick mno7890 WIP saving before lunch
pick pqr1234 final maybe
```

Change the word before each commit:

| Action | What it does |
|--------|-------------|
| `pick` | Keep the commit as-is |
| `reword` | Keep the commit but change its message |
| `squash` | Combine with the commit above (you'll edit the combined message) |
| `fixup` | Like squash but discard this commit's message |
| `drop` | Delete the commit entirely |

You can also reorder lines to change commit order.

## Useful Commands

| Command | What it does |
|---------|-------------|
| `git log --oneline` | See commit history (before and after) |
| `git rebase -i <commit>` | Start interactive rebase from a commit |
| `git rebase -i HEAD~6` | Rebase the last 6 commits |
| `git rebase --continue` | Continue after editing a commit message |
| `git rebase --abort` | Abort and go back to the original state |

## Check Yourself

Open Fork and verify:

- [ ] The `feature/messy-plan` branch has 2-3 commits instead of 6
- [ ] Each commit message clearly describes what changed
- [ ] No "wip", "fix typo", or "oops" messages remain
- [ ] The actual file changes are the same (same final state of `workout-plan.txt`)
- [ ] `git diff main..feature/messy-plan` shows the same changes as before the rebase

**Tip:** In Fork, click on each commit in the cleaned-up branch. The changes should be logical groupings — for example, one commit for "add new exercises" and one for "enhance warm-up routine."

**Warning:** Never rebase commits that have been pushed and shared with others. Rebase rewrites history — that's fine for your local branches, but it causes problems for anyone who has already based work on the original commits.

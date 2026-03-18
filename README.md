# The Git Gym

Welcome to **The Git Gym** — a hands-on Git training course disguised as a gym management repo.

You'll work through 5 assignments that teach you essential Git skills by managing workout plans, class schedules, and client records for a fictional gym. Each assignment is a realistic scenario that you might encounter in a real project.

## Prerequisites

- Git installed on your machine
- A terminal you're comfortable with
- A GitHub account (for assignment 4)
- [Fork](https://git-fork.com/) (your favorite Git GUI — use it to visualize what's happening!)

## Getting Started

```bash
# Clone this repository
git clone <this-repo-url>
cd GitTeacher

# Verify everything works
git status
git log --oneline
```

Open the repo in **Fork** so you can see branches and commits as you work.

## Assignments

Work through these in order — each one builds on skills from the previous:

| # | Assignment | What You'll Learn |
|---|-----------|-------------------|
| 1 | [New Training Program](assignments/01-branching.md) | Creating and merging branches |
| 2 | [Schedule Clash](assignments/02-merge-conflict.md) | Resolving merge conflicts |
| 3 | [Clean Up Your Plan](assignments/03-rebase.md) | Interactive rebase |
| 4 | [Shift Handover](assignments/04-collaboration.md) | Push, pull, and remote collaboration |
| 5 | [Multitasking Coach](assignments/05-worktrees.md) | Git worktrees for parallel work |

## How It Works

1. Read the assignment scenario
2. Try to complete the task using the command hints provided
3. Use Fork to visualize what happened after each step
4. Check the `solutions/` folder if you get stuck

## Tips

- **Use Fork alongside the terminal** — seeing the visual representation helps you understand what each command does
- **Don't peek at solutions first** — struggle a bit, that's how you learn
- **Experiment freely** — if you break something, you can always re-clone the repo
- **Read error messages** — Git's error messages are actually helpful once you know what to look for

## Files in This Repo

| File | Description |
|------|-------------|
| `workout-plan.txt` | The gym's current workout program |
| `schedule.txt` | Weekly class timetable |
| `nutrition-guide.txt` | Meal plans for clients |
| `clients.txt` | Client roster with goals |

These are the files you'll be editing, merging, and rebasing throughout the assignments. They're plain text so you can focus on Git, not code.

Good luck, and enjoy your workout!

---
name: git-push
description: Stage, commit, and push changes to remote repo
user_invocable: true
---

Stage all modified/new files (excluding StableESM/ directory and sensitive files), commit, and push to the remote:

1. Run `git status` to see what changed.
2. Run `git diff --stat` to summarize changes.
3. Run `git log --oneline -3` to see recent commit style.
4. Stage the relevant changed files by name. Never stage the `StableESM/` directory, `.env`, or credential files.
5. Write a concise commit message summarizing the changes.
6. Commit and push to origin on the current branch.
7. Show the user the commit hash and confirm the push succeeded.

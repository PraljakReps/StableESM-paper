---
name: git-push
description: Stage, commit, and push changes to origin main
user_invocable: true
---

Push current changes to the remote repository:

1. Run `git add -A` to stage all changes.
2. Ask the user for a commit message, or suggest one based on recent changes.
3. Run `git commit -m "<message>"`.
4. Run `git push origin main`.
5. If push fails, show the error and suggest a fix.

---
name: todo
description: Review TODO.md against current paper state, update completed/new items
user_invocable: true
---

Review the TODO.md checklist against the current state of the paper and update it:

1. Read `TODO.md` to get the current checklist.
2. Read `main.tex` and `appendix.tex` to check the current state of the paper.
3. For each TODO item, check whether it has been completed:
   - Sections marked empty: check if they now have content
   - Placeholder values (XXX): check if they've been filled in
   - Fixes (typos, broken citations): check if they've been corrected
   - Figures: check if the figure files exist in `figures/`
4. Update `TODO.md`:
   - Mark completed items with `[x]`
   - Add any new TODOs discovered (e.g., new XXX placeholders, new empty sections, new `\textcolor{red}` TODO markers, missing figure files referenced in tex)
   - Move newly completed items to the appropriate "Already Written/Done" section if one exists
5. Show the user a summary of what changed: items completed, new items found.

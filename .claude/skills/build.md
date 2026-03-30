---
name: build
description: Compile main.tex to PDF and open it
user_invocable: true
---

Compile the LaTeX paper and open the resulting PDF:

1. Run `latexmk -pdf main.tex` in the project root directory. Use a timeout of 120 seconds.
2. If compilation succeeds, run `open main.pdf` to open the PDF.
3. If compilation fails, show the error output to the user.

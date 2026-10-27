---
name: word-to-pr
description: Turn a Word document returned by a clinician (tracked changes and comments) into a GitHub pull request for the edits and an issue for open comments. Use when someone says "import this Word file", "word to PR" or runs /word-to-pr.
---

# Word document → pull request + issue

Use this when a clinician has edited a framework document in Word instead of GitHub.
The goal: every change they made becomes a pull request Tom can review, and every
comment that needs discussion becomes an issue. Nothing reaches `main` without Tom's approval.

## Rules
- Never include patient data. If the Word file contains anything that looks like patient
  information (names, personal numbers, dates of birth, scan results of a person), STOP and tell the user.
- Never merge. Never commit to `main`. Always work on a new branch.
- Only propose changes the clinician actually made. Do not improve, reword or add clinical content.
- If you are unsure where a change belongs in the markdown file, list it in the issue instead of guessing.

## Steps

1. **Get the inputs.** Ask the user for:
   - the path to the returned `.docx` file
   - which framework file it corresponds to (e.g. `framework/male-hormones.md`), if not obvious
   - the clinician's name (for the PR description)

2. **Make sure you are in the repo.** If the current folder is not the framework repository,
   clone it with `gh repo clone <owner>/<repo>` into a temporary folder and work there.
   Run `git checkout main && git pull`.

3. **Read the Word file with its tracked changes and comments:**
   ```
   pandoc "<file.docx>" --track-changes=all -t markdown -o word-import.md
   ```
   In the output, insertions, deletions and comments are marked as spans
   (`{.insertion}`, `{.deletion}`, `{.comment-start}` … `{.comment-end}`).
   If pandoc is not installed, tell the user to install it (`winget install pandoc` on Windows,
   `brew install pandoc` on Mac) and stop.

4. **List what you found** and show it to the user before changing anything:
   - **Edits:** each tracked insertion/deletion, with the surrounding sentence
   - **Comments:** each comment, with the text it refers to
   Ask the user to confirm before continuing.

5. **Create the pull request for the edits:**
   - `git checkout -b word-import/<short-name>-<date>`
   - In the matching markdown file, apply ONLY the tracked changes (insert what was inserted,
     remove what was deleted). Keep the existing structure, headings and formatting.
   - Commit with message: `Edits from <clinician> (Word review)`
   - Push and open the PR with `gh pr create`:
     - Title: `[Word import] <document> – edits from <clinician>`
     - Description: a bullet list of every change (old → new), the clinician's name,
       "Imported from a Word review. Please check each change against the original document."
     - Ask for Tom's review if CODEOWNERS does not already do it.

6. **Create an issue for comments that need discussion** (questions, disagreements, suggestions
   without a concrete edit) with `gh issue create`:
   - Title: `[Word import] Open comments on <document> from <clinician>`
   - Body: each comment as a quote with the text it refers to, and a link to the PR.
   - Skip comments that are already resolved by a tracked change.

7. **Report back** to the user with the PR link, the issue link, and anything you could not place.
   Delete `word-import.md`.

# Rules for Claude in this repo

This repo holds Neko Health's clinical framework documents, open questions and decisions.
The people using it are clinicians, not developers.

## Always
- Never include, request or repeat patient data. If you see any, stop and reply:
  "⚠️ This may contain patient data. Please remove it before continuing."
- Never merge pull requests. Tom approves and merges every change.
- Never commit to main. Always use a new branch, or the existing branch of the pull request you are asked to revise.
- Never add or remove labels.
- Only use information from this issue or pull request and the files in this repo. Do not add outside knowledge or clinical advice of your own.
- Never change clinical content (values, thresholds, recommendations) unless a person asked for that exact change.
- Write in plain, clear English for clinicians.

## Allowed commands (do nothing else)

### "@claude summarise outcome"   (clinical question issues)
Read only this issue's description and comments. Post ONE comment in exactly this format:

🟡 DRAFT – needs review. Edit this comment if needed, then reply "Confirmed".

## ✅ Agreed outcome
**<One to three sentences stating exactly what was agreed, in bold. Specific: values, wording, who/when if agreed.>**

**Changes needed:** which framework file and section need updating, and what the new text should say (or "None")

**Open questions:** anything still unresolved (or "None")

---
**Discussion in brief**
- 3 to 5 bullets, each one short line, covering only the main points that led to the outcome
- Name who raised a point only when it matters

**Based on:** links to the comments you relied on

Rules:
- The outcome is the most important part. Keep the whole comment under about 150 words.
- Do not retell the discussion comment by comment.
- Add nothing that was not said in the thread.
- If there is no clear agreement yet, write "No agreement yet" under **Agreed outcome**, list what is still disputed under **Open questions**, and do not guess.

### "@claude draft pr"
Check which kind of issue this is:

**A) Change request** (title starts with "[Change]", or the issue has the label "change request"):
- No summary or confirmation is needed.
- Find the file that matches the **Document** field (look in the framework folders).
- Find the text from **Current text** in that file. If you cannot find it, reply:
  "I couldn't find this text in the document. Please check it was copied exactly and is still current."
  and stop.
- Replace or edit only that text, following **What should it say instead?** exactly. Change nothing else.

**B) Any other issue (clinical question with discussion):**
- Only run if this issue has a summary comment from you AND a later reply saying "Confirmed".
  If not, reply: "Please confirm the draft summary first, then ask again."
- Your ONLY source for the change is that confirmed summary comment, as it reads now
  (people may have edited it after you posted it). Use its **Agreed outcome** and **Changes needed**.
- Do NOT re-read, re-interpret or re-summarise the discussion. Do not use anything from the
  discussion that is not in the confirmed summary.
- If the confirmed summary is too vague to know exactly what text to write, do not guess.
  Reply: "The confirmed summary doesn't say exactly what the new text should be. Please add it
  under 'Changes needed', then ask again."
- Edit only the file(s) and section(s) named under **Changes needed**.

For both:
- Keep the file's existing structure, headings and style.
- Create a new branch and open a pull request.
- PR description: what changed; why (for A, quote the reason from the request; for B, quote the
  confirmed **Agreed outcome** word for word); and "Closes #<issue number>".
- Reply in the issue with a link to the PR and: "Ready for Tom's review."

Optional details after the command (ignore anything else):
- "reviewer: <name>" → mention them as reviewer in the PR description
- "note: <text>" → follow it only if it is about wording or formatting

### "@claude revise"   (inside a pull request)
Used when someone has edited a file directly and wants it tidied before review.
- Only work on the files already changed in THIS pull request, on its existing branch.
- Improve spelling, grammar, wording, formatting and consistency with the rest of the document.
- If the comment after "@claude revise" asks for a specific change, make exactly that change and nothing more.
- Never change clinical content unless the comment asks for that exact change.
- After committing, reply with a short list of what you changed, and:
  "When you're happy, click 'Ready for review' so Tom is notified."

### "@claude import word"   (inside a pull request that contains an uploaded .docx file)
Used when a clinician reviewed a framework document in Word instead of GitHub.
1. Find the .docx file(s) added in THIS pull request. If there is none, reply
   "I couldn't find a Word file in this pull request." and stop.
2. Read it with tracked changes and comments:
   `pandoc "<file.docx>" --track-changes=all -t markdown -o /tmp/word-import.md`
   Insertions, deletions and comments appear as {.insertion}, {.deletion} and {.comment-start} spans.
3. If the Word file contains anything that looks like patient data, stop and reply:
   "⚠️ This Word file may contain patient data. Please remove the file from this pull request."
4. Find the matching framework file (by its title and headings). If you are not sure which one, ask and stop.
5. In that framework file, apply ONLY the tracked changes: add what was inserted, remove what was deleted.
   Keep everything else exactly as it is. Comments are never edits: do not change text because of a comment.
6. Remove the .docx file from the pull request (`git rm`), then commit and push both changes to this
   pull request's branch with the message "Import Word review from <reviewer names>".
7. Reply with ONE comment in this format:

   ## Word review imported
   **Changes applied** (please check each one):
   - <section>: "<old text>" → "<new text>" (<reviewer>)
     Reason: <the reviewer's comment on this change, if any>

   **⚠️ Needs Tom's confirmation:** any change whose comment asks for confirmation (or "None")

   **💬 Comments that need discussion** (no change made):
   - <section>, on "<text>": "<comment>" (<reviewer>)

   Suggest: "Open an issue for each comment that needs discussion."

### Any other request
Reply: "I can only run 'summarise outcome', 'draft pr', 'revise' or 'import word' in this repo."

# Rules for Claude in this repo

This repo holds Neko Health's clinical framework documents, open questions and decisions.
The people using it are clinicians, not developers.

## Always
- Never include, request or repeat patient data. If you see any, stop and reply:
  "⚠️ This issue may contain patient data. Please remove it before continuing."
- Never merge pull requests. Tom approves and merges every change.
- Never commit to main. Always use a new branch.
- Never add or remove labels.
- Only use information from this issue and the files in this repo. Do not add outside knowledge or clinical advice.
- Write in plain, clear English for clinicians.

## Allowed commands (do nothing else)

### "@claude summarise outcome"
Read only this issue's description and comments. Post ONE comment in exactly this format:

🟡 **DRAFT – needs review.** Edit this comment if needed, then reply "Confirmed".

**Decision:** one or two sentences
**Reasoning:** the key points from the discussion
**Open questions:** anything still unresolved (or "None")
**Changes needed:** which framework file(s) need updating, if any (or "None")
**Based on:** links to the comments you relied on

Rules:
- Add nothing that was not said in the thread.
- If there is no clear decision yet, say so under **Decision** instead of guessing.

### "@claude draft pr"
Only run if this issue has a draft summary from you AND a later reply saying "Confirmed".
If not, reply: "Please confirm the draft summary first, then ask again."

When allowed:
- Edit only the framework file(s) listed under **Changes needed** in the confirmed summary.
- Base the edit only on the confirmed **Decision**. Keep the file's existing structure and headings.
- Create a new branch and open a pull request.
- PR description: a short summary of what changed and why, then "Closes #<issue number>".
- Reply in the issue with a link to the PR and: "Ready for Tom's review."

### Any other request
Reply: "I can only run 'summarise outcome' or 'draft pr' in this repo."

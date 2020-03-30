---
description: >-
  Writing clear and concise git commit messages is important to the overall
  health of a project and the team that is working on the project.
---

# Git commit messages

Good commit messages have 3 critical benefits:

1. Help speed up the code review process
2. Help in writing good release notes 
3. Help future maintainers \(and your future self\) understand why a change was made, or what exactly a particular bug was

### Sample commit message

```text
 Short (70 chars or less) summary of changes

 More detailed explanatory text, if necessary.  Wrap it to about 80
 characters or so.  In some contexts, the first line is treated as the
 subject of an email and the rest of the text as the body.  The blank
 line separating the summary from the body is critical.

 Further paragraphs come after blank lines.
  - Bullet points are okay, too 
  - A hyphen is used for the bullet, surrounded by a single space
```

* The summary line is written in the imperative voice, and is structured in a way so that the message completes the sentence, “If applied, this commit will…”. For eg:
  * "Split the Rx streams in RecentPatientsViewController"
  * "Add Appium checkstyle task to the git pre-push hook"
  * "Add query in PatientRepository to get count of sync-pending records"
* Summary lines start with words like “Add”, “Update”, and “Fix” instead of Added, Updated and Fixed
* Summary lines never end with a period, just like the subject of an email 
* The explanatory text isn’t required but encouraged, especially when a commit fixes a bug. It’s good practice to explain clearly why a certain issue was occurring and how the commit fixes it. 


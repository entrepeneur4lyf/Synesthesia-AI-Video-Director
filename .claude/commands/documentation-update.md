---
name: documentation-update
description: Workflow command scaffold for documentation-update in Synesthesia-AI-Video-Director.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /documentation-update

Use this workflow when working on **documentation-update** in `Synesthesia-AI-Video-Director`.

## Goal

Updates project documentation, such as README, CLAUDE.md, or release notes, to reflect recent changes or clarify usage.

## Common Files

- `README.MD`
- `CLAUDE.md`
- `RELEASE_NOTES_v*.md`
- `Feature notes.txt`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit documentation file(s) (README.MD, CLAUDE.md, RELEASE_NOTES_*.md, Feature notes.txt)
- Commit with a message referencing the doc change or related feature/fix

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.
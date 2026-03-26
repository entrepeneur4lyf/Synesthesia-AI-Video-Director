---
name: feature-development-with-ui-and-backend
description: Workflow command scaffold for feature-development-with-ui-and-backend in Synesthesia-AI-Video-Director.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-development-with-ui-and-backend

Use this workflow when working on **feature-development-with-ui-and-backend** in `Synesthesia-AI-Video-Director`.

## Goal

Implements a new feature or major enhancement, typically involving both backend logic and UI changes, often with supporting config or data files.

## Common Files

- `models.py`
- `llm_logic.py`
- `assembly.py`
- `video.py`
- `config.py`
- `utils.py`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or add backend logic (e.g., models.py, llm_logic.py, assembly.py, video.py, config.py, utils.py)
- Edit or add UI tab(s) or orchestrator (e.g., ui/tabX_*.py, ui/app.py)
- Update or add config/data files if needed (e.g., styles.json, render_calibration.json, global_settings.json)
- Update documentation (README.MD, CLAUDE.md, Feature notes.txt) if the feature is user-visible
- Update requirements or batch files if dependencies/scripts are affected

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.
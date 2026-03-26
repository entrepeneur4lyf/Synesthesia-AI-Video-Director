```markdown
# Synesthesia-AI-Video-Director Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and workflows used in the Synesthesia-AI-Video-Director Python project. You'll learn how to contribute features, fix bugs, update documentation, manage dependencies, and refactor code according to the established practices of this repository. The guide includes code style examples, step-by-step workflow instructions, and suggested commands for common tasks.

## Coding Conventions

**File Naming**
- Use `snake_case` for all Python files.
  - Example: `llm_logic.py`, `video.py`, `tab1_project.py`

**Import Style**
- Use *relative imports* within packages.
  - Example:
    ```python
    from .utils import some_helper_function
    from .tab2_storyboard import StoryboardTab
    ```

**Export Style**
- Use *named exports* (explicit function/class definitions).
  - Example:
    ```python
    def generate_video(...):
        ...
    class ProjectModel:
        ...
    ```

**Commit Messages**
- Freeform style, typically descriptive, ~60 characters.
  - Example: `Fix bug in video rendering when no audio track present`

**Directory Structure**
- Main logic in root files: `models.py`, `llm_logic.py`, `assembly.py`, etc.
- UI in `ui/` folder, split into tabs: `tab1_project.py`, `tab2_storyboard.py`, etc.
- Configuration and data in `.json` files.

## Workflows

### Feature Development with UI and Backend
**Trigger:** When adding a new user-facing feature or major enhancement  
**Command:** `/new-feature`

1. Edit or add backend logic (`models.py`, `llm_logic.py`, etc.)
2. Edit or add UI tab(s) or orchestrator (`ui/tabX_*.py`, `ui/app.py`)
3. Update or add config/data files if needed (`styles.json`, etc.)
4. Update documentation (`README.MD`, `CLAUDE.md`, `Feature notes.txt`) if the feature is user-visible
5. Update requirements or batch files if dependencies/scripts are affected

**Example:**
```python
# In llm_logic.py
def generate_synesthetic_prompt(text):
    # New feature logic here
    ...
```
```python
# In ui/tab3_video.py
from ..llm_logic import generate_synesthetic_prompt
...
```

---

### Documentation Update
**Trigger:** When updating user or developer documentation  
**Command:** `/update-docs`

1. Edit documentation file(s) (`README.MD`, `CLAUDE.md`, `RELEASE_NOTES_*.md`, `Feature notes.txt`)
2. Commit with a message referencing the doc change or related feature/fix

**Example:**
- Update `README.MD` to explain a new feature or clarify usage.

---

### Dependency or Install Script Update
**Trigger:** When fixing install issues, pinning dependencies, or updating install/launch scripts  
**Command:** `/update-deps`

1. Edit `requirements.txt` and/or `install.bat`, `update.bat`, `run.bat`
2. Update `README.MD` if install instructions change
3. Commit with a message referencing dependency or install changes

**Example:**
```txt
# In requirements.txt
moviepy==1.0.3
openai==0.27.0
```
```bat
:: In install.bat
pip install -r requirements.txt
```

---

### Bugfix or Small Improvement
**Trigger:** When fixing a bug or making a minor improvement  
**Command:** `/bugfix`

1. Edit the affected code file(s) (often `app.py` or `ui/tabX_*.py`)
2. Optionally update documentation if user-facing
3. Commit with a message referencing the bug or fix

**Example:**
```python
# In ui/tab3_video.py
def render_video(...):
    # Fixed issue with missing audio
    if not audio_track:
        audio_track = generate_silence()
```

---

### Release Notes Creation
**Trigger:** When preparing or publishing a new release  
**Command:** `/release-notes`

1. Add or update `RELEASE_NOTES_vX.Y.Z.md`
2. Commit with a message referencing the release version

**Example:**
- Create `RELEASE_NOTES_v1.2.0.md` summarizing new features and fixes.

---

### Modularization or Refactor
**Trigger:** When reorganizing code for scalability or clarity  
**Command:** `/refactor`

1. Create new module files (e.g., move from `app.py` to `ui/tabX_*.py`, `assembly.py`, etc.)
2. Update imports and orchestrator files (`ui/app.py`)
3. Remove or shrink monolithic files
4. Update documentation to reflect new structure

**Example:**
```python
# Before: in app.py
def handle_project():
    ...

# After: in ui/tab1_project.py
def handle_project():
    ...
# In ui/app.py
from .tab1_project import handle_project
```

## Testing Patterns

- Test files follow the pattern `*.test.*` (e.g., `video.test.py`)
- Testing framework is unknown; check for `assert` statements or custom test runners.
- Place tests alongside the code or in a dedicated `tests/` directory if present.

**Example:**
```python
# In video.test.py
from .video import generate_video

def test_generate_video():
    result = generate_video("test_input")
    assert result is not None
```

## Commands

| Command         | Purpose                                           |
|-----------------|--------------------------------------------------|
| /new-feature    | Start a new feature with backend and UI changes  |
| /update-docs    | Update documentation files                       |
| /update-deps    | Update dependencies or install scripts           |
| /bugfix         | Fix a bug or make a small improvement            |
| /release-notes  | Create or update release notes                   |
| /refactor       | Modularize or refactor code structure            |
```

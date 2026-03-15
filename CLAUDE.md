# Synesthesia AI Video Director — Project Context

## Architecture

Single-file Gradio application (`app.py`) that orchestrates:
- **LM Studio** (local LLM) — generates video prompts and plot summaries via OpenAI-compatible API
- **LTX Desktop** (local AI video engine) — generates video clips from prompts
- **moviepy 1.x** — assembles clips into final video with audio

## Critical: LTX Desktop Resolution Handling

LTX Desktop generates videos at resolutions that are **multiples of 32** for optimal GPU processing. The actual output resolutions do NOT match standard video resolutions:

| Preset | Standard | LTX Actual |
|--------|----------|------------|
| 540p   | 960x540  | 960x512    |
| 720p   | 1280x720 | 1280x704   |
| 1080p  | 1920x1080| 1920x1088  |

The `RESOLUTION_MAP` in `app.py` must use the LTX actual values. Using standard resolutions causes the assembly `resize` to distort frames, producing visible tearing artifacts.

## Dependencies

- **moviepy must be < 2.0** — the codebase uses `from moviepy.editor import ...` which was removed in moviepy 2.x. Version is pinned in `requirements.txt`.
- **pydub** requires FFmpeg installed on the system PATH.
- **keyboard** is used for the Ctrl+R restart hotkey.

## Key Domain Concepts

- **Shot Types**: "Vocal" (singing/performance) and "Action" (narrative/visual). These control prompt generation strategy and audio attachment during video generation.
- **LTX duration snapping**: Shot durations are locked to 1-5 second increments at 24 fps for LTX compatibility.
- **Intercut mode**: Default mode that scans vocal audio for silence gaps to create alternating Vocal/Action shots.

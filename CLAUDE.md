# CLAUDE.md

Marshal custom integration for Home Assistant (HACS): Assist conversation entity, AI Task entity
(`POST /api/v1/ai-tasks`), reauth flow. It talks to [Marshal](https://github.com/lGruenzweilHTL/marshal) only over its
public API v1. uv project (Python 3.14 via `.python-version`); tests in `tests/` (`uv sync`, `uv run pytest`).

- Commits: Conventional Commits. Never add a `Co-Authored-By` trailer or other AI attribution.
- Tests never need a running Marshal or Home Assistant instance: mock Marshal, use the pytest HA fixtures.

## Package index

| Package | Purpose |
|---|---|
| `pytest-homeassistant-custom-component` | Tests for the HA custom integration (`uv run pytest`); pins the HA version tested against. The component itself has no requirements (it uses HA's shared aiohttp session) |
| `hassil`, `home-assistant-intents`, `gazetteer-matcher`, `pymicro-vad`, `pyspeex-noise`, `mutagen`, `ha-ffmpeg`, `PyTurboJPEG` (dev) | Requirements of the HA components the tests set up (`conversation`, `assist_pipeline`, `tts`, `ai_task` with `camera`); keep in step with the pinned HA release |

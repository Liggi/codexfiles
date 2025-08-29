codexfiles — Codex CLI config and tools

Overview
- Personal setup for Codex CLI.
- Centralizes global instructions (AGENTS.md), Codex config (config/config.toml), small helper tools (bin), and local artifact folders.

What’s included
- AGENTS.md: Collaboration preferences and working guidelines.
- config/config.toml: Defaults for high‑reasoning usage and example profiles.
- bin/: `gpt5-mini` (quick prompts) and `gpt5-search` (search + summarize).
- codebase-reports/ and code-search/: Destinations for AI-created artifacts.
- scripts/install: Symlinks config into `~/.codex` and adds `bin/` to PATH.

Install
```bash
cd ~/codexfiles
./scripts/install
```

After install
- `~/.codex/config.toml` and `~/.codex/AGENTS.md` point to this repo.
- `~/codexfiles/bin` is added to PATH (restart your shell or `source ~/.zshrc`).

Prerequisites for helper tools
- `python3` and the OpenAI Python package for `bin/gpt5-mini` and `bin/gpt5-search`.
- If needed: `python3 -m pip install --user --upgrade openai`.

Profiles and defaults
- Defaults in `config/config.toml`:
  - `model = "gpt-5"`
  - `model_reasoning_effort = "high"`
  - `model_verbosity = "medium"`
  - `model_reasoning_summary = "detailed"`
- A `fast` profile uses `gpt-5-mini` for quick iterations: `codex -p fast`.

Notes
- This does not replace your entire `~/.codex` directory; it only links `config.toml` and `AGENTS.md`.
- Artifact outputs live under `~/codexfiles` so they can be kept local or versioned as you prefer.

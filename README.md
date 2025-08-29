codexfiles — Personal Codex CLI configuration and global instructions

Purpose
- Mirrors your Claude Code setup and dotfiles conventions for Codex CLI.
- Centralizes global instructions (AGENTS.md), Codex config (config/config.toml), helper tools (bin), and artifact dirs.

What’s included
- AGENTS.md: Global guidance tailored to your collaboration preferences (no tmux/subagents/search).
- config/config.toml: High‑reasoning defaults (GPT‑5) + optional MCP example and profiles.
- bin/: gpt5-mini and gpt5-search helpers (same behavior you use in Claude).
- codebase-reports/ and code-search/: Destinations for AI-created artifacts.
- scripts/install: Safe symlink installer for ~/.codex/config.toml and ~/.codex/AGENTS.md and PATH setup.

Install
```bash
cd ~/codexfiles
./scripts/install
```

After install
- In Codex CLI, use /approvals to choose Auto, Read-Only, or Full Access as needed.
- Global instructions merge order: ~/.codex/AGENTS.md → <repo>/AGENTS.md → nearest subdir AGENTS.md (nearest wins).
- Helper tools are available on PATH at next shell startup (or run: `source ~/.zshrc`).

Prerequisites for helper tools
- `python3` and the OpenAI Python package for `bin/gpt5-mini` and `bin/gpt5-search`.
- If missing, install later: `python3 -m pip install --user --upgrade openai`.

High‑reasoning by default
- This repo’s `config/config.toml` sets:
  - `model = "gpt-5"`
  - `model_reasoning_effort = "high"`
  - `model_verbosity = "medium"`
  - `model_reasoning_summary = "detailed"`
- A `fast` profile uses `gpt-5-mini` for quick iterations: `codex -p fast`.

Notes
- This does not replace your entire ~/.codex directory (which contains history/sessions). It only symlinks config.toml and AGENTS.md.
- Artifact output paths are under ~/codexfiles to keep outputs versionable and consistent with your Claude layout.

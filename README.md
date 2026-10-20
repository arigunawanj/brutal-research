# Brutal Research

Adversarial deep research for product, business, and technical ideas — in Indonesian Gen Z voice. No yes-man, no ngarang: bantah ide pakai bukti terkini, bandingkan alternatif nyata, lalu putuskan BUILD / VALIDATE FIRST / PIVOT / INTEGRATE / KILL.

Portable agent skill (`SKILL.md` standard). Works in **Claude Code, Codex, Gemini CLI, Antigravity, Cursor, GitHub Copilot, Windsurf, ChatGPT Projects**, and any agent that can read a markdown instruction file.

## Install

### One command, all agents (recommended)

```bash
curl -fsSL https://raw.githubusercontent.com/arigunawanj/brutal-research/main/install.sh | sh
```

Installs globally to:

| Agent | Path |
|---|---|
| Claude Code | `~/.claude/skills/brutal-research/` |
| Codex (and other `.agents`-aware agents) | `~/.agents/skills/brutal-research/` |
| Gemini CLI | `~/.gemini/skills/brutal-research/` |
| Antigravity | `~/.gemini/antigravity/skills/brutal-research/` |

Per-project instead (run inside your repo; writes `.claude/`, `.agents/`, `.gemini/`, `.agent/` skill folders):

```bash
curl -fsSL https://raw.githubusercontent.com/arigunawanj/brutal-research/main/install.sh | sh -s -- --project
```

Or with the [skills CLI](https://skills.sh) (detects installed agents):

```bash
npx skills add arigunawanj/brutal-research
```

### Per agent

- **Claude Code (plugin)**: `/plugin marketplace add arigunawanj/brutal-research` then `/plugin install brutal-research@brutal-research`.
- **Gemini CLI (extension)**: `gemini extensions install https://github.com/arigunawanj/brutal-research`.
- **Codex**: copy `skills/brutal-research/` to `~/.agents/skills/` (or `.agents/skills/` in a repo). Optionally merge [`adapters/AGENTS.md`](adapters/AGENTS.md) into your `AGENTS.md`.
- **Antigravity**: copy `skills/brutal-research/` to `~/.gemini/antigravity/skills/` (global) or `.agent/skills/` (workspace).
- **Cursor**: copy [`adapters/.cursor/rules/`](adapters/.cursor/rules) and `skills/` into your repo.
- **GitHub Copilot**: copy [`adapters/.github/`](adapters/.github) and `skills/` into your repo.
- **Windsurf**: copy [`adapters/.windsurf/rules/`](adapters/.windsurf/rules) and `skills/` into your repo.
- **ChatGPT Projects**: paste [`CHATGPT_PROJECT_INSTRUCTIONS.md`](CHATGPT_PROJECT_INSTRUCTIONS.md) into Project Instructions and attach `skills/brutal-research/SKILL.md`.
- **Anything else**: paste or attach [`skills/brutal-research/SKILL.md`](skills/brutal-research/SKILL.md) as system / custom instructions.

Adapters in `adapters/` (`AGENTS.md`, `CLAUDE.md`, `GEMINI.md`) are project-level pointers to the skill — merge them into existing files, don't overwrite.

## Usage

Invoke by name (`/brutal-research` where slash-skills are supported) or just ask naturally:

> Pakai Brutal Research: saya ingin bikin SaaS QA Testing untuk software house Indonesia. Bongkar asumsi saya, bandingkan kompetitor terkini dengan URL sumber, jelaskan apakah lebih baik build, pivot, atau integrasi, lalu tanya satu pertanyaan yang paling menentukan.

For agents without skill support, use the fill-in template [`prompts/RESEARCH_PROMPT.md`](prompts/RESEARCH_PROMPT.md).

## Notes

- Output language is Indonesian (casual, Gen Z tone). It roasts decisions, not people.
- The skill never claims tests or research it didn't do. Live research requires the agent to have web/browser tools of its own.
- Skill discovery paths vary by agent version; if auto-activation doesn't kick in, reference the skill explicitly.

## License

MIT

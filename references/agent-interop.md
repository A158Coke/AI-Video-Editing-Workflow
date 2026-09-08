# Agent interoperability

The repository is intentionally plain-text and tool-neutral.

## Canonical files

- `WORKFLOW.md` is the canonical vendor-neutral workflow.
- `references/` contains conditional guidance; load only what the current task needs.
- `SKILL.md` is an optional skill-loader entrypoint. Agents without skill discovery should read its Markdown body or use `WORKFLOW.md` directly.
- `AGENTS.md` and `CLAUDE.md` are lightweight adapters for agents that automatically load those filenames. They must point back to the canonical workflow rather than fork its rules.

## Capability mapping

| Need | Portable contract | Possible implementation |
|---|---|---|
| discover files | recursive listing/search | `rg`, PowerShell, Bash, Python, agent file API |
| edit text | preserve UTF-8 and make reviewable changes | patch tool, editor, scripted rewrite |
| inspect media | read metadata and sample frames/audio | `ffprobe`, `ffmpeg`, MediaInfo, NLE preview |
| render | reproducible command or project export | FFmpeg, NLE, editor CLI |
| validate | observable checks and reported evidence | shell commands, player preview, manual review |

No implementation in this table is mandatory. An adapter may translate the commands or file operations to the host agent, but it must preserve the same invariants and report missing evidence.

## Portability rules

- Prefer relative paths rooted at the project directory.
- Put machine-specific binaries, fonts, credentials, and network settings in configuration or environment variables.
- Do not require hidden conversation memory, a particular MCP server, a specific plugin, or a vendor-only UI.
- Do not assume a skill will be auto-loaded; explicitly point the agent to `WORKFLOW.md` when starting a task.
- Keep Markdown examples shell-neutral where possible; label PowerShell, Bash, Python, or JavaScript snippets clearly.
- If a host cannot support a step, preserve the manifest and mark the step `unverified` instead of silently skipping it.

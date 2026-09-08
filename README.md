# AI Video Editing Workflow

Reusable, project-agnostic guidance for planning, editing, synchronizing, mixing, and validating video projects.

This repository intentionally contains no team-specific footage, event timecodes, private assets, finished videos, or platform account material. Keep those in a local project directory and commit only the project brief/manifest when appropriate.

The workflow is designed to be agent-neutral. It can be consumed as ordinary Markdown by Claude Code, DSH, Codex, shell-based agents, or human editors. No specific model, plugin, MCP server, UI, or hidden conversation state is required.

## Contents

- [`WORKFLOW.md`](WORKFLOW.md) — canonical vendor-neutral workflow
- [`SKILL.md`](SKILL.md) — optional skill-loader entrypoint; also readable as Markdown
- [`AGENTS.md`](AGENTS.md) — generic agent adapter
- [`CLAUDE.md`](CLAUDE.md) — Claude Code adapter
- [`references/shared-timeline.md`](references/shared-timeline.md) — multi-source event-time alignment
- [`references/audio-bgm.md`](references/audio-bgm.md) — voice/source/BGM roles and loop checks
- [`references/storyboard-and-brief.md`](references/storyboard-and-brief.md) — briefs, shot manifests, and narrative structure
- [`references/rendering-and-compositing.md`](references/rendering-and-compositing.md) — predictable staged rendering
- [`references/text-and-captions.md`](references/text-and-captions.md) — multilingual copy and caption safety
- [`references/quality-gates.md`](references/quality-gates.md) — render and review gates
- [`references/project-layout.md`](references/project-layout.md) — project isolation and manifests
- [`references/material-capture.md`](references/material-capture.md) — web/application material capture
- [`references/radar-chart.md`](references/radar-chart.md) — reusable chart guidance
- [`references/agent-interop.md`](references/agent-interop.md) — portability and adapter contract

## Design principle

Project facts belong to the project brief and storyboard. The skill contains only reusable decisions and validation rules. A match edit may choose an official-feed opening/ending policy; a product promo or chart animation may choose a different policy and record it explicitly.

## Validation

The package is plain Markdown. Systems that support YAML-frontmatter skills may validate and install `SKILL.md`; other agents can use `WORKFLOW.md` and the references directly. The frontmatter is not required to execute the workflow.

---
name: video-editing-workflow
description: Plan, edit, and verify reusable video projects, especially multi-source or multi-camera edits that require a shared timeline, explicit audio policy, and repeatable technical QA.
metadata:
  short-description: Reproducible video editing and multi-camera timeline workflow
---

# Video Editing Workflow

Use this skill when a video task needs more than a one-off trim: multiple source videos, a storyboard, synchronized viewpoints, narration/BGM mixing, repeatable rendering, or delivery validation.

The goal is a reproducible project, not merely a visually plausible export. Keep project facts in the project brief/storyboard; keep this skill limited to decisions that generalize across projects.

## Operating rules

1. Inspect the workspace before editing. Separate immutable sources, project assets, generated intermediates, previews, and deliverables.
2. Write a short brief before rendering: target, audience, duration, aspect ratio, output format, required/forbidden content, audio priority, source permissions, and acceptance tests.
3. Treat the storyboard or shot manifest as the single source of truth. Every generated segment should have a stable ID, source, in/out time, target duration, camera role, audio role, and review status.
4. For multiple viewpoints of the same event, create one logical event timeline first. Align sources using an observable shared signal (HUD clock, slate, score change, waveform, or verified marker), then select cameras on that timeline. Never play the same event once from each source as separate blocks.
5. Keep source time and event time distinct. A fixed offset is only valid after it has been checked at more than one point; otherwise use anchors or a mapping table.
6. Make editorial boundaries explicit. Do not let ads, sponsor beds, studio commentary, interviews, post-event talk, or unrelated transitions enter a section merely because they are adjacent in the source.
7. Render in stages and validate each stage. Never trust an old output just because its filename says “final”; use versioned outputs or a temporary file followed by an atomic replacement.

## Choose the relevant reference

- General project layout and manifests: [references/project-layout.md](references/project-layout.md)
- Briefs, storyboards, and shot manifests: [references/storyboard-and-brief.md](references/storyboard-and-brief.md)
- Multi-camera or match edits: [references/shared-timeline.md](references/shared-timeline.md)
- Voice, source audio, BGM, looping, and silence checks: [references/audio-bgm.md](references/audio-bgm.md)
- Rendering and compositing: [references/rendering-and-compositing.md](references/rendering-and-compositing.md)
- Text, captions, and multilingual graphics: [references/text-and-captions.md](references/text-and-captions.md)
- Boundary and delivery QA: [references/quality-gates.md](references/quality-gates.md)
- Web or application material capture: [references/material-capture.md](references/material-capture.md)
- Radar or multi-dimensional chart visuals: [references/radar-chart.md](references/radar-chart.md)

## Minimum completion gate

Do not call the edit complete until:

- the output was rendered from the current manifest;
- source-to-event alignment was checked at the beginning, middle, and ending boundaries;
- the audio policy was checked, including BGM continuity and requested voice removal;
- representative frames were inspected at every section boundary;
- `ffprobe` confirms the intended duration, streams, dimensions, frame rate, pixel format, sample rate, and channels;
- the result was played in at least one target player or preview surface.

When a gate fails, fix the manifest or source mapping first, then re-render. Do not patch a stale output by hand.

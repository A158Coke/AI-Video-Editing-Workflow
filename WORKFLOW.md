# Portable AI video editing workflow

This is the vendor-neutral source of truth for the repository. Any agent or human editor may use it: Codex, Claude Code, DSH, a shell-only assistant, or a manual editor. It does not require a particular agent API, plugin, model, operating system, or project name.

## 1. Inspect and define the project

Before editing, identify the project root, available files, media tools, and output requirements. Create or update a brief containing:

- target, audience, platform, aspect ratio, duration, and delivery format;
- required and forbidden content;
- source permissions and privacy constraints;
- voice, live sound, effects, BGM, and silence policy;
- acceptance tests and the current output version.

Keep project facts in the project brief and storyboard. Do not put team names, event timecodes, absolute machine paths, account names, or one project's visual rules into this shared workflow.

## 2. Isolate files

Use separate locations for immutable sources, approved assets, scripts, generated work, previews, and deliverables. Keep large/private media local or track only a manifest with relative paths, durations, technical metadata, and optional checksums.

## 3. Build a shot manifest

The storyboard or shot manifest is the single source of truth. Each row should identify:

```text
id | source | source_in | source_out | event_time | duration | camera | audio | treatment | status | notes
```

Use stable IDs and versioned outputs. Never infer that an old file is current from a filename such as `final.mp4`.

## 4. Align multiple sources

When sources show the same event, create one logical event timeline before selecting shots. Use observable anchors such as a HUD clock, slate, score change, waveform, or verified marker. Record the mapping and validate it at an early, middle, and late point.

Do not show the same event once from each source as separate blocks. Select camera changes on the shared event timeline. A 5–10 second chunk is a useful starting range for fast edits, not a universal limit.

Editorial boundary rules are project policies and must be written in the brief. For a broadcast match, a common policy is official/master feed at section opening and ending, with POV only in the middle; ads, sponsor beds, studio commentary, interviews, and post-event talk are excluded when the brief requires it.

## 5. Define the audio mix

Separate picture selection from audio selection. Explicitly decide which source supplies narration, commentary, live sound, effects, and BGM. Record BGM source, permission, selected range, loop strategy, gain, sample rate, and channels.

For continuous music, use a verified non-silent loop source, normalize it before mixing, and check the loop boundary. A gain such as `0.15` is a project setting, never a global default. Remove unwanted source speech or advertising at the source-selection stage rather than hiding it under music.

## 6. Render in stages

Normalize clips first, create reviewable segments, assemble the timeline, mix audio, and encode the deliverable. Keep dimensions, frame rate, SAR, timestamps, pixel format, audio sample rate, and channels explicit. Use the tools available in the environment; `ffmpeg`/`ffprobe` are common options, not mandatory agent dependencies.

Write to a temporary or versioned output, then promote it only after validation. Never claim success based only on a command exit message from a stale or uninspected file.

## 7. Validate

Check both content and technology:

- inspect first/last frames, every section boundary, every source switch, and every accelerated segment;
- verify event order, source alignment, forbidden material, decisive endings, crops, subtitles, and logos;
- inspect duration, streams, codec, dimensions, frame rate, pixel format, sample rate, and channels with the available media inspector;
- listen for gaps, clipping, unwanted voices, sponsor audio, and BGM discontinuities;
- play the result in at least one target player or preview surface.

If a gate fails, fix the manifest or source mapping and render again. Do not hand-patch a stale export.

## 8. Agent interoperability contract

Agents should:

1. Read this file and the relevant reference before acting.
2. Use the host's normal file and shell tools, or an equivalent capability.
3. Treat relative project paths and environment/configuration values as portable; never assume the original author's absolute paths.
4. Preserve user files, avoid destructive cleanup, and report any skipped validation.
5. Keep project-specific decisions in project files and reusable decisions here.

An agent that cannot inspect media, execute commands, or verify output must stop at the appropriate gate and say what remains unverified.

See [references/agent-interop.md](references/agent-interop.md) for adapter guidance.

# Video editing quality gates

## Before rendering

- The source manifest identifies current files and verified timecodes.
- The brief states what must be included and excluded.
- Output settings are configuration, not hidden script constants.
- The output path is versioned or temporary; an old export cannot be mistaken for the new one.

## After rendering

Use `ffprobe` to inspect:

- duration;
- video codec, width, height, frame rate, profile, and pixel format;
- audio codec, sample rate, channel count, and stream presence.

Extract frames at:

- the first and last frame;
- every chapter or game opening and ending;
- every source switch;
- BP/intro/outro acceleration boundaries;
- title, chart, subtitle, or logo appearances.

For multi-camera work, label each checked frame with both output time and source/event time. This makes a timing error diagnosable instead of subjective.

At minimum, inspect the export in the target player for:

- stale or duplicated content;
- audio gaps, unwanted ads, or voice leakage;
- black frames, frozen frames, bad crops, or subtitle collisions;
- event order and decisive endings;
- BGM continuity and speech clarity.

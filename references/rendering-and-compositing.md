# Rendering and compositing

Render in predictable stages: normalize source clips, generate reviewable segments, assemble the timeline, mix audio, then encode the deliverable. Keep dimensions, frame rate, SAR, timestamps, pixel format, and audio format explicit.

Before using transitions, make all inputs compatible. For a simple sequence of clips, calculate transition offsets from measured durations instead of hand-counting frames. Start with hard cuts or a basic fade to prove the timeline, then add stylized transitions.

For static images or transparent text:

- choose a canvas and crop/letterbox policy before rendering;
- keep text and graphic layers separate from the base image when practical;
- parameterize font, position, duration, motion, and opacity;
- protect safe areas and inspect the result on the target aspect ratio.

Typical delivery defaults are H.264 video, `yuv420p`, and AAC audio, but the target platform is authoritative. Verify the actual output with `ffprobe`; do not infer it from command-line arguments.

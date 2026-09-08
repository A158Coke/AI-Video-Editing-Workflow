# Audio and BGM policy

Define audio roles before rendering:

```text
primary voice / commentary > required live sound > effects > BGM
```

The project brief may change this priority, but the choice must be explicit.

## Separate source roles

- Keep video selection and audio selection independent when a POV voice, replay explanation, sponsor bed, or camera noise must be removed.
- Use the approved narration/commentary source as the audio master for aligned multi-camera clips when appropriate.
- Mute source ranges that contain ads, sponsor music, unrelated commentary, or unwanted speech; do not rely on a later BGM layer to hide them.

## BGM

Record source, permission, selected range, loop strategy, gain, sample rate, and channel layout in the project configuration. A gain value such as `0.15` is a project parameter, not a universal default.

For a loop:

1. Find a continuous, non-silent section.
2. Trim it to a stable loop source, optionally with short fades.
3. Normalize the loop's sample rate and channel layout before mixing.
4. Loop it beneath the complete edit, including silent-picture sections if the brief requires continuous music.
5. Check the loop boundary with `silencedetect`, waveform inspection, or a short listening test.

Example pattern:

```bash
ffmpeg -i source.m4a -ss 0 -t 120 \
  -af "aresample=48000:async=1:first_pts=0" \
  -ar 48000 -ac 2 -c:a pcm_s16le loop.wav

ffmpeg -i picture.mp4 -stream_loop -1 -i loop.wav \
  -filter_complex "[1:a]volume=GAIN[bgm];[0:a][bgm]amix=inputs=2:duration=first:dropout_transition=0[a]" \
  -map 0:v:0 -map "[a]" -shortest output.mp4
```

Replace `GAIN` with the project value. Check for clipping, long unintended silence, and voice intelligibility after the final mix.

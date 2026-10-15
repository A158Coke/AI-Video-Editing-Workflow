---
name: video-bgm-selection
description: Cross-cutting skill for choosing background music. Matches the track's energy curve to the case's structure, derives the cut grid from tempo, sets the vocal policy against narration, and records the permission decision. Covers choosing only; mixing stays in references/audio-bgm.md.
metadata:
  short-description: BGM selection policy, energy curve and tempo matching
---

# BGM selection

Layers on top of any case skill. It never replaces one.

Scope boundary: this skill covers **choosing** a track. Loop construction, normalisation,
gain, mixing, and silence checks stay in
[references/audio-bgm.md](../../references/audio-bgm.md). Record the chosen track there,
in the project configuration, using that file's fields.

## When to choose

After the narrative structure exists, before the fine cut.

Choosing earlier makes the music dictate a structure the material cannot support. Choosing
later means the cut is already locked and the track can only be stretched or faded over it,
which is where loop seams and limp endings come from.

## Match the energy curve to the case

The track's own shape must match the case's shape. This is the single decision that most
often fails, and no amount of mixing repairs it.

| Case | Required shape | Rejects |
|---|---|---|
| [product-update](../product-update/SKILL.md) | Low and flat, then a **step** at the turning point, then sustained | Tracks that build gradually: a slow build cannot land a single cut |
| [product-promo](../product-promo/SKILL.md) | Gradual build, peak inside the proof section, short resolve | Tracks that peak in the first quarter |
| [team-promo](../team-promo/SKILL.md) | A statement at the open, build, peak at the invitation | Tracks that fade out before the close |
| [highlight-montage](../highlight-montage/SKILL.md) | A staircase that only rises | Tracks with a mid-track lull, however good the opening |

Listen to the whole track before deciding. A track is chosen on its shape, not on its
first fifteen seconds.

## Derive the cut grid from tempo

Beat interval is `60 / BPM` seconds. A phrase is normally 4 or 8 beats.

| BPM | Beat | 4-beat phrase | 8-beat phrase |
|---|---|---|---|
| 90 | 0.667 s | 2.67 s | 5.33 s |
| 110 | 0.545 s | 2.18 s | 4.36 s |
| 128 | 0.469 s | 1.88 s | 3.75 s |
| 140 | 0.429 s | 1.71 s | 3.43 s |
| 174 | 0.345 s | 1.38 s | 2.76 s |

Choose the tempo so that a phrase matches the intended average shot length for the section.
A quick-cut section of 4-6 seconds per item sits naturally on 8-beat phrases at 128 BPM
(3.75 s) or 4-beat phrases at 90 BPM (2.67 s), and fights a 174 BPM track.

Cut on phrase boundaries, not on every beat. Cutting on every beat reads as a metronome and
exhausts the viewer within twenty seconds.

Where the case gives pacing authority to the operation rather than the music
(product-update), the grid is a guide only: the operation wins every conflict. If the
conflict keeps happening, the track is wrong.

## Place the drop

The drop lands **on** the turning point, not before it and not after.

A drop that arrives early makes the turning point an anticlimax. A drop that arrives late
makes the result feel unearned. If the track's drop cannot be moved to the turning point by
trimming the head, reject the track rather than moving the turning point.

Silence before the drop is part of the selection, not a post-production trick: a track that
cannot be cut to silence for half a beat without an audible artefact is a weak choice.

## Vocal policy

- Narration present: instrumental, or vocals only where no narration plays. Vocals and
  speech in the same language in the same passage are unintelligible together.
- Captions-only cut: vocals are allowed, but lyrics now compete with the reader. Keep them
  out of the sections where a caption must be read.
- Lyrics are content. Check them against the brief's forbidden-content list; a track whose
  lyrics contradict the claim on screen undermines the cut.

## Permission

Record the permission class before the track enters the edit, with the evidence:

| Class | Must record |
|---|---|
| Owned or commissioned | Author, agreement, date |
| Licensed | Licence name, holder, scope, expiry, per-platform limits |
| Free with attribution | Exact attribution text, where it must appear, licence URL |
| Platform library | Which platform, and that the cut will not be published elsewhere |

Two checks that are routinely skipped:

- A licence valid on one platform is not automatically valid on another. Re-check per
  publication target named in the brief.
- Automated rights matching may flag a track the project is entitled to use. That is a
  delivery risk to plan for, not a statement about the licence. Record the expected
  outcome in the brief so a claim is not mistaken for a mistake later.

This is a record-keeping policy, not legal advice. When the rights position is unclear,
escalate to the project owner rather than guessing.

## Rejection list

Reject a track, regardless of how good it sounds alone, when:

- its best moment is at 0:00, leaving nothing to build to;
- it has a false ending mid-track that reads as the video ending;
- its drop cannot be aligned to the turning point by trimming the head;
- it has no section quiet enough to carry narration or a caption;
- its loop point is audible and the cut needs continuous music;
- its lyrics contradict, date, or distract from the claim on screen.

## Hand-off

Once chosen, record the track in the project configuration using the fields in
[references/audio-bgm.md](../../references/audio-bgm.md): source, permission, selected
range, loop strategy, gain, sample rate, channels. Gain is a project value, decided against
the actual mix, never copied from another project.

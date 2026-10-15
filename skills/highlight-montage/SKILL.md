---
name: video-case-highlight-montage
description: Policy set for a highlight montage. Builds a rising intensity curve from decisive moments, enforces one shared event timeline so no event is replayed once per source, and ends on the most decisive clip. Use together with WORKFLOW.md.
metadata:
  short-description: Highlight montage policy set
---

# Highlight montage

Use when compiling decisive moments into a single rising curve. Do not use when the subject
is who a group of people are; that is [team-promo](../team-promo/SKILL.md), which may borrow
shots from a montage but answers a different question.

This file sets only the policies `WORKFLOW.md` delegates. The workflow steps and quality
gates are unchanged. Record every override in the project brief.

## Not an arc, a curve

This case does not use the general `problem -> turning point -> result` arc. It uses an
intensity curve that only rises:

| Section | Share | Purpose |
|---|---|---|
| Statement | 10% | One clip that sets the floor, already above ordinary |
| Build | 60% | Each clip raises at least one dimension over the previous one |
| Peak | 20% | The most decisive moment in the whole set |
| Release | 10% | One beat to land, then stop |

## The escalation rule

Every clip must raise at least one of: **stakes, speed, scale, or improbability** over the
clip before it. A clip that raises none of them is filler and comes out, however good it is
on its own.

This forces the order. Sort candidates by the dimension each one raises, then place the
single most decisive clip last. Never open with the peak: after it, every later clip reads
as a decline.

## Clip selection

- Decisive moments only. Setup that does not pay off is cut, even when it explains the play.
- Enter late, leave early. The clip starts at the last possible moment that still reads.
- A clip that needs a caption to be impressive is not impressive; it belongs in a different
  case.

## One event timeline, always

This is the case where [shared-timeline](../../references/shared-timeline.md) is mandatory,
not conditional.

When several sources show the same event, build the shared event timeline first and select
viewpoints on it. Showing the same event once from each source as separate blocks is
forbidden by `WORKFLOW.md` and is the most common failure of this case: it reads as padding
and it breaks the curve, because the repeat cannot raise any dimension.

Record the anchor used for alignment and validate it early, mid, and late.

## Audio policy

Priority: `music > source impact audio > effects > commentary`

- Music leads the pacing. Cut on transients and phrase boundaries, not on every beat.
- Source audio is raised only for impact moments, then returned under the music.
- Commentary is usually removed: it dates the clip, drags in sponsor reads, and fights the
  music ([audio-bgm](../../references/audio-bgm.md)).
- The peak clip may drop the music entirely for its duration. Decide this in the brief, not
  at mix time.

## Forbidden

- The same event replayed once per source as separate blocks.
- Speed ramps used to make an ordinary moment look decisive.
- Reordering clips in a way that implies a sequence of events that did not happen.
- Opponent identifiers shown in a way that invites harassment.
- A clip whose source permission is not recorded in the brief.

## Acceptance tests

- Event order in the export is verifiable against the shared timeline mapping.
- No event appears twice, from any viewpoint.
- Every clip raises at least one named dimension over its predecessor; the brief records
  which one.
- The last clip is the most decisive in the set.
- Every accelerated segment boundary was inspected frame by frame
  ([quality-gates](../../references/quality-gates.md)).
- The cut ends decisively: no trailing filler after the release beat.

## References to load

Required: [shared-timeline](../../references/shared-timeline.md),
[storyboard-and-brief](../../references/storyboard-and-brief.md),
[audio-bgm](../../references/audio-bgm.md),
[quality-gates](../../references/quality-gates.md),
[rendering-and-compositing](../../references/rendering-and-compositing.md).

Conditional: [text-and-captions](../../references/text-and-captions.md) when clips are
labelled; [material-capture](../../references/material-capture.md) when identifiers must be
masked at capture time.

---
name: video-case-product-update
description: Policy set for a product update video. One hero feature gets a complete demonstration, every other change gets a quick cut, and the viewer leaves with a version identifier and exactly one action. Use together with WORKFLOW.md.
metadata:
  short-description: Product update video policy set
---

# Product update video

Use when a released version has changes to show and the viewer is expected to act
(update, install, re-open the tool). Do not use for an evergreen explanation of what the
product is: that is [product-promo](../product-promo/SKILL.md).

This file sets only the policies `WORKFLOW.md` delegates. The workflow steps and quality
gates are unchanged. Record every override in the project brief.

## Narrative structure

`problem -> old flow -> turning point -> result -> next action`

Shares of total duration, so the structure scales:

| Section | Share | Purpose |
|---|---|---|
| Hook | 5% | The result of the hero feature, with no greeting and no explanation |
| Problem | 10% | The old flow, really recorded, really slow |
| Hero | 35% | One feature, demonstrated once, start to finish |
| Quick cuts | 30% | Everything else, one caption line each |
| Close | 20% | Version identifier, how to get it, one action |

## The hero rule

Exactly one change gets a complete, uninterrupted demonstration. A video that demonstrates
three features demonstrates none.

Pick the hero by the **largest gap between old effort and new effort**, not by the largest
feature. A small change that removes a daily irritation beats a large change nobody feels.

Every other change gets 4-6 seconds, one caption line, no narration, and must show an
outcome rather than a menu. A change that cannot show an outcome in 6 seconds either
becomes the hero or leaves the video.

## Picture policy

- Real interface only. A redraw or re-staged screen must be labelled as such
  ([material-capture](../../references/material-capture.md)).
- The old flow must be a recording of the old flow. Slowing down new footage to imitate the
  old one is fabricated evidence; it fails the brief's required/forbidden content check.
- Capture at or above the delivery frame rate.
- Cursor and keyboard choreography is decided before recording. Hesitation, mis-clicks, and
  hunting for a menu cannot be repaired in post; re-record instead.
- Redaction happens at capture time, not afterwards. Account identifiers, other users' data,
  and credentials must never reach the immutable source file.

## Audio policy

Priority: `narration > tool operation sound > effects > BGM`

- Pacing follows the operation, not the music. If the music wants a cut the operation has
  not reached, the music is wrong: go back to [bgm-selection](../bgm-selection/SKILL.md).
- The silence before the turning-point cut is required, not decorative. Cut the music for
  roughly half a beat, land the new flow, bring the music back on the result.
- Narration is optional. Captions-only is a valid choice for this case and must be recorded
  in the brief, because it changes the BGM vocal policy.

## Caption and logo policy

- One line per quick cut. One idea per line.
- The version identifier must appear in the closing section and must be legible at the
  delivery resolution, not only on a desktop monitor.
- No corner labels, watermarks, or channel logos unless the brief requires them
  ([text-and-captions](../../references/text-and-captions.md)).

## Forbidden

- Reading the changelog aloud.
- A feature list where no feature's outcome is shown.
- A stylised transition used to cover a mismatch between the old-flow and new-flow
  recordings. Prove the timeline with hard cuts first
  ([rendering-and-compositing](../../references/rendering-and-compositing.md)).
- Any claim about a change that the footage does not demonstrate.

## Acceptance tests

- A viewer who has never used the tool can state in one sentence what the hero feature does.
- The old flow shown is reproducible from the brief by someone else.
- Every quick cut shows an outcome, not a menu being opened.
- The version identifier is present and legible at delivery resolution.
- The close names exactly one action.
- No unredacted account identifier or third-party data in any frame.

## References to load

Required: [material-capture](../../references/material-capture.md),
[storyboard-and-brief](../../references/storyboard-and-brief.md),
[text-and-captions](../../references/text-and-captions.md),
[quality-gates](../../references/quality-gates.md).

Conditional: [radar-chart](../../references/radar-chart.md) when statistics are shown;
[rendering-and-compositing](../../references/rendering-and-compositing.md) when compositing
overlays onto captures.

Not used by this case: [shared-timeline](../../references/shared-timeline.md).

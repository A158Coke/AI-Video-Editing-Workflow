---
name: video-case-product-promo
description: Policy set for an evergreen product promo. Explains what a product is and why it matters, stays correct after the next release, and is paced by music rather than by an operation. Use together with WORKFLOW.md.
metadata:
  short-description: Evergreen product promo policy set
---

# Product promo

Use when the viewer does not yet know what the product is, or when the cut must keep
working for months. Do not use to announce a release: that is
[product-update](../product-update/SKILL.md).

This file sets only the policies `WORKFLOW.md` delegates. The workflow steps and quality
gates are unchanged. Record every override in the project brief.

## How this differs from product-update

| | product-update | product-promo |
|---|---|---|
| Trigger | A release | Nothing; evergreen |
| Pacing authority | The operation | The music |
| Hero | One new feature | One outcome the product makes possible |
| Version identifier | Required | Forbidden |
| Shelf life | Until the next release | Must survive the next release |

## Narrative structure

`stakes -> what it is -> proof -> next action`

| Section | Share | Purpose |
|---|---|---|
| Stakes | 15% | The situation the viewer recognises, before the product appears |
| What it is | 20% | One sentence, said once, in plain words |
| Proof | 45% | Real outcomes, not a feature tour |
| Close | 20% | One action |

## Proof policy

Proof is an outcome the viewer can judge, not a list of capabilities. Show the product
finishing something, not the product having buttons.

Order proofs by how easily a stranger can judge them, strongest first. A proof that needs
domain knowledge to appreciate goes late or goes out.

## Shelf-life policy

This case is evergreen, so the cut must not date itself.

- No version identifiers, release dates, "new", "just launched", or roadmap claims.
- No seasonal content, event branding, or limited-time offers in the picture.
- Prefer interface areas that change slowly. A screen that is about to be redesigned will
  make the whole cut look stale; note the risk in the brief.
- Re-check before each re-publish: if any frame now shows an old interface, the cut is
  expired, not merely dated.

## Audio policy

Priority: `narration > effects > source audio > BGM`, and music may lead the pacing.

- Music-led cutting is allowed here and is the default. Cut on phrase boundaries, not on
  every beat.
- Source interface sound is decorative in this case and may be dropped entirely.
- If narration exists, it owns the energy ceiling: the track must leave room for it
  ([bgm-selection](../bgm-selection/SKILL.md)).

## Caption and logo policy

- Captions carry meaning, not decoration. If a line only repeats the narration, cut it.
- A product name or logo may appear once, in the close, if the brief requires it.
- Multilingual delivery is decided in the brief, not at render time
  ([text-and-captions](../../references/text-and-captions.md)).

## Forbidden

- A feature tour disguised as proof.
- Claims the footage does not support.
- Stock footage standing in for the product's own interface.
- Borrowed third-party material whose permission is not recorded in the brief.

## Acceptance tests

- A stranger can say what the product does after the "what it is" section alone.
- Every proof shows a finished outcome.
- Nothing on screen implies a date, version, or season.
- The cut still passes these tests after the next release, with no edits.
- The close names exactly one action.

## References to load

Required: [storyboard-and-brief](../../references/storyboard-and-brief.md),
[audio-bgm](../../references/audio-bgm.md),
[text-and-captions](../../references/text-and-captions.md),
[quality-gates](../../references/quality-gates.md).

Conditional: [material-capture](../../references/material-capture.md) when interface
material is captured; [radar-chart](../../references/radar-chart.md) when statistics appear.

---
name: video-case-team-promo
description: Policy set for a team promo featuring real people. Consent and identifier handling are gates rather than courtesies, roster order is an explicit decision, and the cut ends on an invitation. Use together with WORKFLOW.md.
metadata:
  short-description: Team promo policy set, consent-gated
---

# Team promo

Use when the subject is a group of real people: identity, recruiting, or a sponsor-facing
introduction. Do not use to compile decisive moments; that is
[highlight-montage](../highlight-montage/SKILL.md), which this case may borrow shots from.

This file sets only the policies `WORKFLOW.md` delegates. The workflow steps and quality
gates are unchanged. Record every override in the project brief.

## Consent is a gate, not a courtesy

Every identifiable person in the cut needs recorded consent before the first render.
"Identifiable" includes a face, a voice, a display name, a tag, an account identifier, or a
handle visible in a scoreboard or chat panel.

The brief must carry, per person: who, what footage, which identifier is shown, consent
obtained on which date, and the withdrawal path.

A person appearing without a recorded consent entry is a **failed gate**. Do not render,
do not publish, and do not resolve it by blurring at the last minute: re-select the shot.

Additional rules:

- A former member's footage needs fresh consent before reuse in a new cut.
- Bystanders in a shared lobby, chat, or scoreboard are not consenting participants; mask
  their identifiers at capture time ([material-capture](../../references/material-capture.md)).
- Never show account identifiers, emails, or anything that could be used to locate a person
  off-platform, even with consent.

## Roster order is a decision

How people appear implies a hierarchy whether or not one is intended. Choose a rule, state
it in the brief, and apply it without exception:

alphabetical, by role, by join date, or by an order the team itself ratified.

Equal screen time per person is a separate decision and must also be stated. If screen time
is deliberately unequal, say why in the brief so it is a choice, not an accident.

## Narrative structure

`identity -> proof -> invitation`

| Section | Share | Purpose |
|---|---|---|
| Identity | 30% | Who this group is, in its own words |
| Proof | 50% | Play that supports the identity claim |
| Invitation | 20% | What the viewer is invited to do |

The proof section must support the identity claim specifically. A team that calls itself
patient should not be proven with a highlight reel of aggression.

## Audio policy

Priority: `member voice > music > source audio > effects`

- Music-led pacing is the default; member voice, where it exists, overrides it.
- Source comms audio is high risk: it carries unconsented voices, real names, and language
  the team may not want published. Mute it by default and clear any exception in the brief.
- Do not use music to cover removed speech; remove the speech at source selection
  ([audio-bgm](../../references/audio-bgm.md)).

## Forbidden

- Any identifiable person without a consent record.
- Opponent identifiers shown in a way that invites harassment.
- Implying a result, ranking, or sponsorship the team does not hold.
- Reusing a departed member's footage without fresh consent.

## Acceptance tests

- Every identifiable person has a consent record, checked against the rendered frames and
  not only against the shot list.
- The roster order rule is stated in the brief and holds in the export.
- No account identifier, email, or off-platform locator is visible in any frame.
- No unconsented voice is audible, including under music.
- The proof section supports the specific identity claim made in the opening.
- The close names exactly one action.

## References to load

Required: [storyboard-and-brief](../../references/storyboard-and-brief.md),
[material-capture](../../references/material-capture.md),
[audio-bgm](../../references/audio-bgm.md),
[quality-gates](../../references/quality-gates.md).

Conditional: [shared-timeline](../../references/shared-timeline.md) when the proof section
uses several viewpoints of one match; [text-and-captions](../../references/text-and-captions.md)
when names or tags are rendered as graphics.

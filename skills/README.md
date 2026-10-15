# Case skills

`WORKFLOW.md` deliberately refuses to decide narrative structure, editorial boundaries,
audio roles, and caption policy. It says those are project policy and must be recorded.
This directory holds the reusable default answers, one set per genre of video.

## Three layers, no duplication

| Layer | Lives in | Answers |
|---|---|---|
| Workflow | [`WORKFLOW.md`](../WORKFLOW.md) | **Which** decisions must be made and which gates must pass. Identical for every video. |
| Case skill | `skills/<case>/SKILL.md` | The **default** answers for one genre. Reusable across projects of that genre. |
| Project brief | `<project>/brief/` | The **final** answers for one specific video, plus project facts: URLs, dates, permissions, timecodes, account material. |

A case skill is a policy set, not a second workflow. The same `WORKFLOW.md` steps and the
same quality gates run for every case; only the answers change.

## Rules for a case skill

1. Set only policies that `WORKFLOW.md` explicitly delegates: narrative structure, editorial
   boundary rules, audio role priority, caption and logo policy, pacing, acceptance tests,
   and which references to load.
2. Do not restate, summarize, or override the workflow's steps or gates. Point back to them.
3. Do not contain project facts. No team names, URLs, timecodes, account material, machine
   paths, or one project's brand rules.
4. A project may override any default, but its brief must record the override and the reason.
5. If two cases need the same rule, it belongs in `references/`, not copied into both.

## Choose a case

| Case | Use when | Skill |
|---|---|---|
| Product update | A released version has new features to show and users must act on it | [`product-update/SKILL.md`](product-update/SKILL.md) |
| Product promo | Explaining what a product is and why it matters; evergreen, not version-bound | [`product-promo/SKILL.md`](product-promo/SKILL.md) |
| Team promo | Presenting a group of real people: identity, recruiting, sponsor-facing | [`team-promo/SKILL.md`](team-promo/SKILL.md) |
| Highlight montage | Compiling decisive moments into a rising intensity curve | [`highlight-montage/SKILL.md`](highlight-montage/SKILL.md) |

If a project matches two cases, pick the one whose **acceptance tests** you actually intend
to pass, and record the choice in the brief. Do not merge two cases into one edit.

## Cross-cutting skills

| Skill | Applies to | Purpose |
|---|---|---|
| BGM selection | Any case | Choosing the track: energy curve, tempo against cut rhythm, vocal policy, licence class, where the drop lands | [`bgm-selection/SKILL.md`](bgm-selection/SKILL.md) |

A cross-cutting skill layers on top of a case skill. It never replaces one.
Mixing mechanics (loop, gain, normalisation, silence checks) stay in
[`references/audio-bgm.md`](../references/audio-bgm.md); the BGM skill only covers choosing.

## Adding a case

A new case earns its own skill only when it changes at least two of:
narrative structure, editorial boundary policy, audio role priority, or acceptance tests.
Otherwise it is a project-level override and belongs in that project's brief.

Each case skill carries YAML frontmatter so hosts with skill discovery can install it
individually. The frontmatter is optional metadata, not a runtime dependency; an agent
without skill discovery reads the Markdown body directly.

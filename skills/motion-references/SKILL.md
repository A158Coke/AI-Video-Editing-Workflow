---
name: video-motion-references
description: Optional cross-cutting guidance for choosing and applying numbered Motion Prompt references to an existing video storyboard; preserves renderer portability and verifies adapted visual effects.
metadata:
  short-description: Motion Prompt selection, adaptation and motion QA
---

# Motion references (Motion Prompt)

Use this skill alongside exactly one video case skill **only when a scene needs a specified motion or camera effect**. It does not replace [WORKFLOW.md](../../WORKFLOW.md), the storyboard, or the renderer, and does not install an upstream dependency.

Read [references/motion-prompt.md](../../references/motion-prompt.md) for the complete integration contract. In particular:

1. Respect explicit `#NNN` picks or pasted gallery selections. If there are none, offer the gallery; search only when selection is delegated to the agent.
2. Record the selected ID, scene purpose, source revision, renderer adaptation, and demo URL in the **existing** storyboard `treatment`/`notes` fields.
3. Inspect the upstream element spec and kit before porting. Preserve the existing scene timeline and audio policy, then adapt the motion to the project's existing renderer or describe it for a generative model.
4. Check entrance, hold, exit/loop, scene boundaries and target-frame output as described in [quality-gates.md](../../references/quality-gates.md). Report any missing render validation.
5. Preserve upstream MIT notices when bringing element or kit code into a video project.

The upstream interactive catalog Skill is **optional** and separate from this cross-cutting policy. No catalog code or new service is bundled in this repository.

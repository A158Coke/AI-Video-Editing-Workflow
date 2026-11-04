# Motion Prompt: optional motion-reference integration

[Motion Prompt](https://github.com/showheyohtaki/motion-prompt) by Shohei Ohtaki is an external, MIT-licensed catalog of named visual effects with numbered examples, motion specs, and Canvas reference implementations. Browse the [gallery](https://showheyohtaki.github.io/motion-prompt/). It is **not** a video render engine, editing timeline, licensed stock-footage bundle, or a required dependency of this workflow.

This integration is only a way to specify, implement and verify a chosen visual treatment. The canonical steps remain in [WORKFLOW.md](../WORKFLOW.md), and each video's existing storyboard is the single source of truth.

## When to load it

Use it for a scene that explicitly asks for a named title animation, motion graphic, camera move, transition, or related visual treatment. Do not add effects just because the catalog exists. Respect the project's chosen case skill, timing, editorial boundaries, audio priorities, accessibility, and acceptance tests.

## Choose, then record

1. Read the brief and existing storyboard before selecting anything. Identify the scene's role, start, duration, adjacent cuts, source media, and renderer.
2. If the user supplies IDs (for example `#005`), demo links, or text from the gallery's **Copy picks**, treat them as the chosen set. Keep their order, notes and scene assignments. Do not insert extra effects.
3. When no element has been chosen, invite the user to browse the gallery. If they explicitly delegate selection, search the catalog scene by scene and record the decision. Do not silently invent a selection.
4. Put the reference **in the existing storyboard row**: `treatment: motion-prompt:#005; role: title entrance`; in its `notes` record the demo URL, upstream commit/catalog version at use, any changed values, and the intended render method. Keep the normal source in/out, duration, and audio fields. Do not create another effects manifest or timeline.
5. A generated-video-model prompt that borrows the named move is **based on** a reference, not a faithful code port. Label it accordingly.

Example (illustrative, not a default effect):

```text
shot id: intro-title
treatment: motion-prompt:#005 (title appearance)
notes: demo=https://showheyohtaki.github.io/motion-prompt/#005;
       upstream_revision=<resolved commit or catalog version>;
       target=existing scene duration; text/logo=project brief;
       method=Canvas port; QA=pending
```

## Optional catalog access

The repository works as plain Markdown without installing anything. To enable the upstream interactive skill in a **consuming editing project** with a compatible agent and Node.js 18+, follow the [official installation instructions](https://github.com/showheyohtaki/motion-prompt#skill-reference):

```sh
npx skills add showheyohtaki/motion-prompt
```

That command is optional and changes the agent environment/project where it is run; review the resulting files before committing them. It must not be required by `WORKFLOW.md` or run automatically by this integration.

With the upstream Skill installed, the script at `<skill-dir>/scripts/motion-prompt.mjs` supports:

```sh
node <skill-dir>/scripts/motion-prompt.mjs info
node <skill-dir>/scripts/motion-prompt.mjs list --pack motion,motion2
node <skill-dir>/scripts/motion-prompt.mjs get 005
node <skill-dir>/scripts/motion-prompt.mjs kit motion
node <skill-dir>/scripts/motion-prompt.mjs prompt 005
node <skill-dir>/scripts/motion-prompt.mjs pick --pack camera,camera2
```

The upstream `pick` handoff uses a temporary localhost listener and browser. It may be unavailable in remote agents, sandboxes, or environments without a browser. In that case, open the public gallery separately, choose the elements and paste **Copy picks** or their numbers into the editing task. An agent without the upstream CLI can still follow links and specs when accessible, or flag missing evidence rather than improvising timings. No project footage should be sent to the catalog.

## Port the reference into the existing editor

Before implementing, read the upstream [Skill](https://github.com/showheyohtaki/motion-prompt/blob/main/skills/motion-prompt/SKILL.md), the selected element's exact spec, its required `kit <pack>`, and [porting guidance](https://github.com/showheyohtaki/motion-prompt/blob/main/skills/motion-prompt/references/porting.md).

- **Canvas or frame-driven rendering:** derive animation time from the existing scene/frame clock (not wall time or randomness). Load the matching kit once per pack and isolate multiple kits in separate scopes/modules. Preserve the actual movement timings, easing, and distances.
- **Remotion, CSS/SVG/Lottie, or After Effects:** translate source timing, easing, and geometry to the renderer's own primitives. Preserve the scene's length and its cuts; adjust the hold first instead of changing the movement's speed.
- **FFmpeg/NLE edits:** produce any needed graphics in the existing render pipeline and composite them at the storyboard-defined timestamp. Do not add a separate render service or new state store just for the reference.
- **Veo/Sora/other generation models:** use the named move and its timing description as a prompt, then verify generated output independently. Do not claim pixel-accurate reproduction.

Keep project text, imagery, color, brand, aspect ratio and safe areas authoritative. A numbered sample's design is illustrative, not a command to replace the brief.

## Provenance and quality

When code is adapted, preserve the upstream MIT copyright/license notice on the element and kit according to the upstream porting guidance; include applicable attribution in distributed source. Record the source revision and demo link in the existing project notes for reproducibility. Avoid vendoring the full catalog or copying preview media into this workflow repository: doing so creates drift and unnecessary update costs.

For each referenced scene, independently inspect the first frame, mid-motion, hold, exit (or loop seam), and both adjacent cuts in a render from the current storyboard. Compare easing/timing and appearance with the chosen example when possible; verify text fit, fonts, crops, safe area, and target frame rate. If there is no runnable renderer or no media to check, report **unverified**; a documented reference is not proof of a correct final video.

For the general delivery gates, see [quality-gates.md](quality-gates.md).

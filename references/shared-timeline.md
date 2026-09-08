# Shared timeline for multi-source edits

This reference applies when two or more videos show the same event from different viewpoints.

## Build the mapping

1. Identify the event-time signal visible or audible in the sources.
2. Record at least two verified anchors per source where possible.
3. Express each source clip in event time, not only file playback time.
4. Validate the mapping at an early, middle, and late point. If the mapping drifts, model drift or use local anchors instead of one global offset.

Use a table like:

```text
event_id | event_time | source_a_time | source_b_time | selected_camera | audio_source | evidence
```

## Select cameras without duplicating the event

The normal shape is one event timeline with short intercuts. A 5–10 second chunk is a useful starting range for fast edits, but the story and action determine the final length.

For a match or broadcast edit, camera policy should be configurable. A common policy is:

```text
section opening  -> official/master feed
section middle   -> official and POV intercut on the same event time
section ending   -> official/master feed
```

This is a policy, not an assumption. If a project requires a different policy, write it in the brief and test it at every boundary.

## Boundary discipline

- Determine the true end of an event by inspecting frames around the transition, not by guessing a fixed offset from the next segment.
- If the source continues into commentary, studio, ads, interviews, or a result discussion, mark that boundary explicitly and exclude the unwanted range.
- If a decisive ending must be visible, choose an official segment that contains the ending or its verified official transition, then cut before the unwanted post-event content.
- After an event ends, the next event should begin from its own verified opening anchor; never let a POV clip or post-event commentary leak across the boundary.
- Inspect the first and last frame of every event section in the rendered output.

## Common failure patterns

- **Separate-block replay:** official footage is shown once, then POV repeats the same action. Fix by selecting both from one event-time axis.
- **Offset drift:** the first anchor matches but later action is early or late. Fix with multiple anchors or a drift model.
- **End contamination:** a late chunk enters studio commentary or an ad. Fix with a manually verified finish boundary.
- **Timeline backtracking:** a later output segment uses an earlier event time than the preceding segment. Fix the manifest ordering before rendering.

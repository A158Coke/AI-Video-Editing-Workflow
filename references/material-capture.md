# Material capture

Use this reference when a project needs screenshots, web UI, charts, or other application material.

- Record source URL, capture date, viewport, login/state assumptions, license, and output path.
- Prefer stable observable readiness signals over arbitrary sleeps.
- Use semantic, ARIA, or data-test selectors; avoid generated CSS classes and language-specific text when automating.
- Preserve the original capture separately from any crop, annotation, or redraw.
- Do not capture credentials, private data, or unrelated user information.
- If a dynamic chart is unstable, save the authorized source data first; only redraw after documenting the data and transformation.

# Radar and multi-dimensional chart visuals

Use a radar chart only for a small number of comparable dimensions, not for time series or raw values with incompatible units.

- Define metric meaning, direction, units, normalization, missing-value treatment, and weights before drawing.
- Use the same axis order, scale, and maximum for every compared object.
- Keep source data and formulas traceable; visual area is not the underlying fact.
- Show numeric labels or a companion table when exact reading matters.
- Mark missing values explicitly instead of silently treating them as zero.
- For dynamic web charts, prefer authorized source data or a verified screenshot; label an offline redraw as a redraw.

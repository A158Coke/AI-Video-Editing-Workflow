# Reusable project layout

Use a project-local layout so that one project can be archived or deleted without touching another:

```text
project/
├─ README.md                 # project scope and current status
├─ brief/                    # requirements, permissions, acceptance tests
├─ storyboard/               # shot list, timeline map, review notes
├─ assets/                   # approved logos, covers, fonts, music
├─ sources/                  # immutable originals or documented external paths
├─ scripts/                  # project-specific render/analysis code
├─ work/                     # proxies, extracted frames, temporary segments
├─ previews/                 # review exports and contact sheets
└─ deliverables/             # versioned exports only
```

Keep shared tools and reusable skills outside project directories. A project may reference a shared asset library, but its brief must say which version was used.

For large or private media, track a manifest rather than the binary itself. Record relative path, duration, dimensions, codec, source URL or license note, and optionally a checksum.

Recommended manifest fields:

```text
id | role | path | source_in | source_out | duration | camera | audio | status | notes
```

Do not use names such as `final.mp4` as the only version identifier. Prefer `project_v03_review.mp4` or a dated release name.

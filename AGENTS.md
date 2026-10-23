# AGENTS.md

## codebase-memory-mcp
- Indexed as project `sports_turf` (mode: full). The index auto-refreshes; re-run `index_repository` with `name: "sports_turf"` only to force a refresh.
- Graph contains HTML modules and `<section>` nodes for `index.html` and `mockup/booking-mockup.html`. Inline `<script>` JavaScript functions are NOT extracted, so use grep for JS logic.
- Images (`assets/images/*.jpg`, `mockup/*.png`) are excluded by design.

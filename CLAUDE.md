# CLAUDE.md -- Canada Post Training Reference

---

## Project Overview (stable context)

Personal on-the-job reference tool for a new Canada Post delivery employee (letter carrier). Michael completed the 5-day National Delivery Employee Training Program 4.0 classroom portion on 2026-06-05 and starts depot/route training with a trainer the week of 2026-06-09. The project is a single-file HTML app that serves as a searchable, offline-capable procedural reference built from the training manual content (Days 1-5 + Appendices). It needs to work equally well on phone and desktop.

- Source material lives in `Training Material/` (9 PDFs, not to be modified)
- The app is `index.html` at project root, single-file, works offline
- Hosted at **https://fargrove.github.io/Training-Manual/** (public repo: `Fargrove/Training-Manual`, training PDFs excluded)
- Michael's depot is a **sequenced depot** (Burnaby LCD North Fraser 2, LC0110, Step Van, Wave 2)
- Focus on procedures and operational content, not classroom exercises
- Use Canada Post terminology exactly as it appears in the training materials
- **See `prd.md` for full project specification.**
- **Prior handoffs archived in** `ARCHIVED_HANDOFFS.md`.

---

## SESSION HANDOFF [2026-06-05–06] (condensed):
- Built reference app from scratch (170+ pages of PDFs, 17 topic sections, full-text search)
- Added inline SVG diagrams: header board, PDT device, scanning rules, delivery label types
- Created PDT Device section; rebuilt header board to match actual LC0110 layout
- Set up GitHub Pages at (old URL now defunct, see new URL above)
- App: **Done (v2)**

---

## SESSION HANDOFF [2026-06-16]:

### What happened
- Restructured local directory: `Canada Post/` is now a local parent folder only (no repo)
- Moved all project files into `Canada Post/Training Manual/` — its own git repo
- Deleted old `Fargrove/Canada-Post` GitHub repo
- Created new repo `Fargrove/Training-Manual`, pushed fresh history, re-enabled GitHub Pages
- New live URL: **https://fargrove.github.io/Training-Manual/**
- Updated CLAUDE.md and prd.md to reflect new repo name and URL

### Deliverable status
- Reference app: **Done (v2)**, hosted at https://fargrove.github.io/Training-Manual/

### Open issues
- GitHub Pages first build may take a few minutes to go live after repo creation

### Next 3 priorities
1. Add content from the Appendices PDF (job aids, dog hazard handouts, vehicle supply checklist, parcel prep, safety rules)
2. Update app based on what Michael actually needed to look up most during depot training
3. Consider a "favourites/bookmark" feature for frequently used procedures

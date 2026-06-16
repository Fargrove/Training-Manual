# CLAUDE.md -- Canada Post Training Reference

---

## Project Overview (stable context)

Personal on-the-job reference tool for a new Canada Post delivery employee (letter carrier). Michael completed the 5-day National Delivery Employee Training Program 4.0 classroom portion on 2026-06-05 and starts depot/route training with a trainer the week of 2026-06-09. The project is a single-file HTML app that serves as a searchable, offline-capable procedural reference built from the training manual content (Days 1-5 + Appendices). It needs to work equally well on phone and desktop.

- Source material lives in `Training Material/` (9 PDFs, not to be modified)
- The app is `index.html` at project root, single-file, works offline
- Hosted at **https://fargrove.github.io/Canada-Post/** (public repo, training PDFs excluded)
- Michael's depot is a **sequenced depot** (Burnaby LCD North Fraser 2, LC0110, Step Van, Wave 2)
- Focus on procedures and operational content, not classroom exercises
- Use Canada Post terminology exactly as it appears in the training materials
- **See `prd.md` for full project specification.**
- **Prior handoffs archived in** `ARCHIVED_HANDOFFS.md`.

---

## SESSION HANDOFF [2026-06-05]:
- Built the entire project from scratch: read all 5 days of training PDFs (170+ pages), built the HTML reference app with 17 topic sections, full-text search, category filters
- App marked Done (v1)

---

## SESSION HANDOFF [2026-06-06]:

### What happened
- Added inline SVG diagrams to the app (header board, PDT device, scanning rules, delivery label types)
- Created a new **PDT Device (CT40/CT45)** section with hardware diagrams, PDT screen mockups (At Depot / En Route), SSINA/recovery info, key functions by phase, PDT acronyms, and POCUR app reports
- Rebuilt the header board diagram to closely match the actual printed LC0110 header board layout (row-by-row recreation with colour-coded Park & Loop sections, NM colour days, stop data)
- Added **Delivery Label Types** subsection to Scanning with visual mockups of Regular Parcel, FlexDelivery, DTPO, and vehicle labels
- Added **Four Scanning Rules visual guide** with label type examples and RaCHEL breakdown
- Renamed `canada-post-reference.html` to `index.html` for GitHub Pages compatibility
- Set up GitHub repo (Fargrove/Canada-Post), removed training PDFs from history, made repo public
- Enabled GitHub Pages at https://fargrove.github.io/Canada-Post/
- Renamed `/sync-cowork` skill to `/sync-to-github` (general-purpose, not Cowork-specific)
- Saved global memory: Michael's default browser is Chrome, not Safari

### Deliverable status
- Reference app: **Done (v2)** with SVG diagrams, hosted on GitHub Pages

### Next 3 priorities
1. Add content from the Appendices PDF (job aids, dog hazard handouts, vehicle supply checklist, parcel prep and loading, delivery accommodation program, safety rules)
2. After first few days of training, update the app based on what Michael actually needed to look up most
3. Consider adding a "favourites/bookmark" feature for frequently used procedures

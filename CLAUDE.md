# CLAUDE.md -- Canada Post Training Reference

---

## Project Overview (stable context)

Personal on-the-job reference tool for a new Canada Post delivery employee (letter carrier). Michael completed the 5-day National Delivery Employee Training Program 4.0 classroom portion on 2026-06-05 and starts depot/route training with a trainer the week of 2026-06-09. The project is a single-file HTML app that serves as a searchable, offline-capable procedural reference built from the training manual content (Days 1-5 + Appendices). It needs to work equally well on phone and desktop.

- Source material lives in `Training Material/` (9 PDFs, not to be modified)
- The app is `index.html` at project root, single-file, works offline
- Hosted at **https://fargrove.github.io/Training-Manual/** (public repo: `Fargrove/Training-Manual`, training PDFs excluded)
- **Classroom training** was at a sequenced depot (Burnaby LCD North Fraser 2, LC0110), all-residential route. The OTJ Checklist section reflects that depot.
- **Actual assigned depot** is **333 Woodland Drive** (Vancouver East), routes LCD 1 (high-rise/downtown) or LCD 2 (Gastown/Chinatown/DTES). These are **SSD depots** (Separate Sort from Delivery): a *router* sorts manual mail during the day, the *delivery agent* (Michael) delivers it the next day and does NOT case/tie out their own mail. Step Van, Wave 2, motorized.
- Focus on procedures and operational content, not classroom exercises
- Use Canada Post terminology exactly as it appears in the training materials
- **See `prd.md` for full project specification.**
- **Prior handoffs archived in** `ARCHIVED_HANDOFFS.md`.

---

## SESSION HANDOFFS [2026-06-05 → 06-16] (condensed):
- Built the reference app from scratch: 170+ pages of PDFs, ~17 topic sections, client-side full-text search, inline SVG diagrams (header board, PDT device, scanning, delivery labels). App reached **v2**.
- Restructured repo: `Canada Post/` is now a local parent folder only; project lives in `Canada Post/Training Manual/` as its own repo. Created `Fargrove/Training-Manual`, hosted on GitHub Pages at https://fargrove.github.io/Training-Manual/.

---

## SESSION HANDOFF [2026-06-19]:

### What happened
- Discovered Michael's **actual assigned depot is 333 Woodland Drive** (LCD 1 / LCD 2), not the Burnaby depot he trained at. Burnaby was all-residential; Woodland is high-rise (LCD 1) and DTES/storefronts (LCD 2).
- Confirmed mid-session that **LCD 1/LCD 2 are SSD depots** (Separate Sort from Delivery). This materially changed the work: in SSD a router sorts the mail, the delivery agent delivers it next day and does NOT case/tie out their own mail.
- Built a new **"Morning Routine: Woodland Drive"** section (first in the `DATA` array), grounded in the official Inside Duties Steps 1–28 and SSD job aids (Appendices p.193–202, Day 1 p.12, Day 3 p.81). Written for Step Van / Wave 2 motorized.
- Then **revised it to SSD**: rewrote the mail step to the DA packet-prep flow (C-52/C-48), replaced tie-out with C-44 missort/RTS handling + POCUR (tie-out kept as marked fallback), added SSD loading rule (Stop & Go LFT in driver's compartment), and added a separate **"If You're Called in as a Router"** card.
- Added a **generic SSD floor-map diagram** (inline SVG) to section 1, numbered to the morning steps, clearly labelled as generic until the real Woodland floor is known.
- New CSS classes for depot content: `.lcd1` (blue, high-rise), `.lcd2` (purple, DTES), `.ask` (green dashed, supervisor questions), `.fillin` (amber inline blank). Reuse these for future depot-specific content.
- Verification approach that works here: extract the `DATA` literal and run it through `new Function(...)` in Node to confirm template literals parse; render via headless Chrome (`--remote-debugging-port=9222`) for visual checks; standalone-HTML render is the reliable way to screenshot a single SVG. Kept to the no-em-dash style rule throughout.
- 3 commits pushed to `main`: `cdf0486` (Morning Routine), `74384f4` (SSD revision), `65a3bfc` (floor map).

### Deliverable status
- Reference app: **Done (v3)**, hosted at https://fargrove.github.io/Training-Manual/
- Morning Routine section: **Done**, but LCD 1/LCD 2 delivery subs (9 & 10) and the floor map are intentional skeletons/generic, awaiting Michael's on-route experience.

### Open issues
- Unconfirmed: whether ALL Woodland routes are SSD or it varies (written SSD-primary with caveat).
- LCD 1/LCD 2 delivery workflows (high-rise master keys/mailrooms; SRO/community mailrooms/awareness) are skeletons with `.fillin` blanks + "Ask at the depot" boxes.
- Floor-map diagram is generic SSD, not Woodland's actual layout.

### Next 3 priorities
1. Once Michael starts at Woodland: replace the LCD 1/LCD 2 skeleton blanks with the real procedures he learns on-route, and redraw the floor map to match the actual depot layout.
2. Confirm the SSD-everywhere question and adjust the routine if some routes are non-SSD.
3. Update the app based on what Michael actually needs to look up most often on the job (and revisit the "favourites/bookmark" idea).

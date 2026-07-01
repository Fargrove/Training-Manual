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

## SESSION HANDOFF [2026-06-19] (condensed):
- Discovered actual assigned depot is **333 Woodland Drive** (LCD 1 high-rise / LCD 2 DTES), confirmed **SSD** (router sorts, delivery agent delivers next day, no self case/tie-out). Built the **"Morning Routine: Woodland Drive (SSD)"** section (first in `DATA`), grounded in Inside Duties Steps 1–28 + SSD job aids (Appendices p.193–202, Day 1 p.12, Day 3 p.81); DA packet-prep (C-52/C-48), C-44 missort/RTS + POCUR, Stop & Go LFT loading, separate Router card, generic SSD floor-map SVG.
- Reusable depot CSS classes: `.lcd1` (blue), `.lcd2` (purple), `.ask` (green dashed supervisor Qs), `.fillin` (amber inline blank). LCD 1/LCD 2 delivery subs + floor map are intentional skeletons awaiting on-route detail.
- App is **v3**, hosted at https://fargrove.github.io/Training-Manual/.

---

## SESSION HANDOFF [2026-07-01]:

### What happened
- New, separate deliverable: a **Claude Project setup kit** so Michael (a **relief carrier**, different route each day) can run per-route chats grounded in the raw training PDFs. This is conversational Q&A over the PDFs, complementary to the offline `index.html` lookup app.
- Created 3 files in `External Documents/`:
  - `CLAUDE-PROJECT-INSTRUCTIONS.md` — text to paste into the Project's custom-instructions box (role, the route-header protocol, answer-from-manuals-then-labelled-guess rule, cite sources, no em-dashes, SSD-vs-standard guardrail).
  - `CLAUDE-PROJECT-SETUP.md` — human setup guide (create Project, upload the 9 PDFs + fact sheet, daily route-header routine, chat naming).
  - `DEPOT-FACT-SHEET.md` — upload file capturing carrier/Woodland/SSD/LCD 1/LCD 2 context so every chat has it without re-typing.
- Key design decisions (confirmed with Michael): **one Project, not one-per-depot** — a pasted route header handles the relief-carrier "different route daily" problem; instructions make Claude ask for the header if missing. **When manuals don't cover it:** answer from manuals first, then a clearly-labelled best guess + "confirm with trainer/supervisor." Did **not** upload `index.html` (200 KB markup = noise); folded its key facts into the fact sheet instead.

### Deliverable status
- Reference app: **Done (v3)**, hosted (unchanged this session).
- Claude Project kit: **Done** (3 files written). **Not yet committed** — asked Michael if he wants them committed; awaiting answer. Michael still needs to create the Project on claude.ai and upload the files himself (can't be done from Claude Code).

### Open issues
- Files in `External Documents/` are uncommitted pending Michael's go-ahead.
- Still open from before: SSD-everywhere unconfirmed; LCD 1/LCD 2 delivery skeletons + generic floor map await on-route detail.

### Next 3 priorities
1. If Michael says yes, commit the 3 `External Documents/` files. Then he creates the Project on claude.ai and uploads the 9 PDFs + `DEPOT-FACT-SHEET.md` + `LCD 1 and LCD 2 Depots.md`.
2. As Michael learns real Woodland specifics on-route, update `DEPOT-FACT-SHEET.md` (and re-upload to the Project) + fill the app's LCD 1/LCD 2 skeletons and redraw the floor map.
3. Confirm the SSD-everywhere question and adjust both the app routine and the fact sheet if some routes are non-SSD.

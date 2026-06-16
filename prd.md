# PRD: Canada Post Training Reference App

## 1. Project Overview

A single-file HTML reference app that lets Michael quickly look up Canada Post delivery procedures, terminology, and rules during depot and route training. See CLAUDE.md for stable project context.

### 1.1 Premise
Five days of classroom training covers a huge amount of procedural knowledge. Starting real depot/route work the following week, there's no way to recall it all. A fast, searchable, mobile-friendly reference drawn from the actual training materials fills that gap.

### 1.2 Goal
Michael can find the answer to any procedural question from the training material in under 10 seconds, on any device, without internet.

### 1.3 Central Messages
- Accuracy over polish: content must match the training manual exactly.
- Speed over features: fast lookup matters more than extra functionality.

### 1.4 Desired Outcomes
- **Feeling:** Confident on route, not worried about forgetting steps.
- **Knowing:** Exactly what to do in any delivery, sorting, or safety scenario.
- **Doing:** Looking up a procedure on phone between stops, finding the answer fast.

## 2. Your Role in This Project
### 2.1 Background
New Canada Post delivery employee, finished classroom training 2026-06-05.

### 2.2 Positioning
Trainee learning the job. The app is a personal study/reference tool, not shared with Canada Post.

### 2.3 Role
End user. Using the app during on-the-job training to supplement what the trainer teaches.

## 3. Audience / Stakeholder Profile
### 3.1 Who
Michael only. Personal use.

### 3.2 Delivery Context
Used on a phone between delivery stops, or on a laptop at home reviewing procedures. Must work offline (no API calls). Must load fast.

### 3.3 Expected State
Needs quick answers mid-task, not leisurely reading. Interface should minimize taps/clicks to reach content.

## 4. Design Principles
### 4.1 Tone

| Do | Don't |
|----|-------|
| Use exact Canada Post terminology | Paraphrase or simplify official terms |
| Write concise procedural steps | Write long explanatory paragraphs |
| Use tables for comparisons | Use prose where a table works better |
| Match the manual's structure | Reorganize in ways that would confuse |

### 4.2 Things to Explicitly Avoid
- No AI/API dependency. Must work fully offline.
- No unnecessary animations or loading states.
- No content that isn't in the training manual.

### 4.3 Format Principles
- Single HTML file, no external dependencies.
- Mobile-first, responsive to desktop.
- Canada Post red (#e00000) as accent color.

## 5. Content Strategy
### 5.1 Content Balance
Heavy on operational procedures (sorting, delivery, scanning, vehicle loading, CMB/parcel lockers). Lighter on culture/values content. Include all safety content.

### 5.2 Key Decisions Made

| Decision | Choice | Reasoning |
|----------|--------|-----------|
| File format | Single HTML | Opens on any device, no install needed |
| Search approach | Client-side keyword search | Works offline, fast |
| Content source | Training manual PDFs only | Accuracy, consistency with what was taught |

## 6. Structure and Flow
### 6.1 Scope
All procedural content from the 5-day training program, organized by topic rather than by training day.

### 6.2 High-Level Arc
Search bar at top, topic categories below, expandable sections within each topic.

### 6.3 Detailed Flow
Topics organized as:
0. **OTJ Training Checklist** - Full on-the-job checklist with inline procedures for every task, sequenced-depot-aware
1. **Glossary & Acronyms** - Quick term lookup + full CPC acronyms list (100+)
2. **Sorting & Case Work** - A-62 case, sorting procedures, blocking technique, revising the case
3. **Header Board** - How to read it, all 6 sections explained
4. **Tying Out the Mail** - Tie-out process, types of stops
5. **Neighbourhood Mail** - Prep, delivery cycles, DCS, colour days
6. **Delivery Procedures** - Safe drop vs carding, DNC, PCI items, registered mail, deliver to door, FlexDelivery, DTPO
7. **CMB & Parcel Lockers** - Step-by-step CMB delivery, parcel locker procedures, unclaimed items, damage reporting
8. **Vehicle & Loading** - Pre-trip inspection, loading Ford Transit Connect/Step Van/Ford Transit, vehicle safety rules
9. **PDT Device (CT40/CT45)** - Hardware diagrams, PDT screens, key functions by phase, SSINA, POCUR reports, PDT acronyms
10. **Scanning & Barcodes** - Four scanning rules, RaCHEL rule, damaged labels, delivery label types
10. **Pickups & Clearances** - Scheduled/on-demand pickups, RPO clearance, SLB clearance
11. **Safety** - Inside/outside hazards, dog bite prevention, key safety, weather gear, dangerous situations
12. **End of Day** - Return procedures, NM exceptions, key check-in, PDT logout
13. **Customer Service** - Payment collection, customs appeals, delivery scenarios
14. **Equipment & Containers** - LFT, SO-95, C-48, depot carts, letter carrier cart, dual satchel
15. **Postal Codes** - FSA, LDU structure
16. **Mail Forwarding & RTS** - Redirection rules, case cards, return to sender reasons
17. **Case Cards** - Hold mail, quarantine, redirection (orange), expiry rules

## 8. Deliverables

| # | Deliverable | Format | Owner | Status |
|---|-------------|--------|-------|--------|
| 1 | Reference app | Single HTML file | Claude | Done (v2) |

### 8.1 Acceptance Criteria

| Deliverable | Criteria |
|-------------|----------|
| Reference app | All procedural content from 5-day training included; search works across all topics; loads in under 2 seconds; works on mobile and desktop; works offline |

## 12. Timeline

| Milestone | Target |
|-----------|--------|
| App built and usable | 2026-06-05 (done) |
| SVG diagrams + PDT section added | 2026-06-06 (done) |
| Hosted on GitHub Pages | 2026-06-06 (done) |
| Michael starts depot training | 2026-06-09 |

## 13. Open Questions
1. Should additional content from the Appendices PDF be added in a future session?
2. Does Michael want a "favourites" or "bookmark" feature for frequently referenced procedures?

## Appendix A: Decision Log

| Question | Decision | Context |
|----------|----------|---------|
| AI-powered or offline? | Offline smart search | Michael needs it to work on route without internet |
| Phone or desktop? | Both equally | Used on phone between stops and laptop at home |
| Study tool or reference? | Reference | Classroom training is done, needs on-the-job lookup |
| Content priority | Procedures first | Operational knowledge is what's hardest to remember |
| Depot type | Sequenced depot | Michael's training depot is sequenced; non-sequenced tasks de-emphasized |
| OTJ checklist | Inline procedures | Each checklist task has full procedure embedded, not just a link |
| Diagrams | Inline SVG | Vector diagrams stay sharp at any zoom, searchable, no external files |
| Hosting | GitHub Pages (public repo) | Free hosting, accessible from any device via URL |

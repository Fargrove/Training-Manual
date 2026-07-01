# How to set up your Canada Post Claude Project

This is your one-time setup guide plus the routine you'll use every workday. It's for you to read.
None of this goes into the Project except where noted.

---

## Part 1 — Create the Project (one time, ~5 minutes)

1. Go to **claude.ai** and sign in.
2. In the left sidebar, click **Projects**, then **Create project** (or **+ New project**).
3. Name it something like **"Canada Post — Letter Carrier Reference"**.
4. Open **Project instructions** (sometimes labelled "What should Claude know..." or a gear/edit
   icon, depending on the version). Open the file **CLAUDE-PROJECT-INSTRUCTIONS.md** in this folder,
   copy everything between the two `=====` lines, and paste it in. Save.

---

## Part 2 — Upload the knowledge base (one time)

In the Project, find **Project knowledge** (the "+ Add content" / upload area) and upload these.
All of them live in this repo.

**The 9 training PDFs** (from the `Training Material/` folder):
- Canada Post - Day 1 Training.pdf
- Canada Post - Day 2 Training.pdf
- Canada Post - Day 3 Training.pdf
- Canada Post - Day 4 Training.pdf
- Canada Post - Day 5 Training.pdf
- Canada Post - Appendices.pdf
- Canada Post - Header Board.pdf
- Canada Post - acronyms.pdf
- Canada Post - on-the-job training session checklist.pdf

**Your distilled depot content:**
- **DEPOT-FACT-SHEET.md** — see Part 3 below; it's in this folder, ready to upload.
- **LCD 1 and LCD 2 Depots.md** — the area breakdown, already in this folder.

> Note on your reference app: the file `index.html` at the repo root holds your hand-written
> Morning Routine and SSD notes, but it's a 200 KB web app, not clean text. Rather than upload the
> whole HTML, the key facts from it are folded into DEPOT-FACT-SHEET.md so Claude gets the signal
> without the markup noise. If you later want the app's full text in the Project, copy the readable
> text out of the page into a plain .md and upload that.

Tip: re-upload a file whenever you update it. Claude reads the version that's in the Project, not
the one on your disk.

---

## Part 3 — The depot fact sheet to upload

A separate file named **DEPOT-FACT-SHEET.md** sits in this same folder. Upload it to the Project
knowledge base along with everything else. It captures your Woodland Drive / SSD / LCD 1 / LCD 2
context so every chat already knows your situation without you re-typing it. Keep it updated as you
learn the real floor layout, master-key procedures, and route specifics on the job.

---

## Part 4 — Your daily routine (every workday)

For each new route or day, **start a new chat inside the Project** (not a one-off chat outside it).
That keeps each day's questions separate and grounded.

**Paste a route header as your first message.** Copy this template, fill it in, send it:

    DEPOT: 333 Woodland Drive (Vancouver East)
    ROUTE: LCD 1 — route #___    (or LCD 2, or wherever you are today)
    SORT MODEL: SSD              (or "standard" if you case your own mail)
    VEHICLE: Step Van, Wave 2
    NOTES: covering for someone, first time on this route, etc.

Then ask your questions normally, e.g.:
- "What's the order of my inside duties this morning here?"
- "How do I handle a missort on an SSD route?"
- "Customer's parcel needs age-of-majority — what do I check and scan?"
- "Dog at the gate, no safe approach. What's the procedure and what do I report?"

If you forget the header and ask something route-specific, Claude is told to ask you which route
you're on before answering. That's on purpose — SSD vs standard changes the right answer.

**Naming chats:** rename each chat by date + route, like `Jun 30 — LCD 1 rte 12`, so you can find
the day you need later.

---

## Part 5 — Good habits

- **Verify anything safety- or compliance-critical** against your trainer/supervisor. Claude is a
  fast reference, not the final word.
- When Claude says **"Not covered in the manuals"**, treat the rest of that answer as a helpful
  guess, not procedure. Confirm it.
- After you learn something real on the route (the actual floor map, a master-key quirk, a building
  access code policy), add it to DEPOT-FACT-SHEET.md and re-upload. The Project gets smarter every
  week you work.
- One Project is enough even though you're relief. The route header handles "different route every
  day." You don't need a separate Project per depot.

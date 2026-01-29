Writing Live Track
===

A low-level, evidence-oriented writing activity logger for Obsidian.

Writing Live Track is a plugin for recording writing activities in Obsidian, automatically and in real-time, recording actual editing actions (typing, deleting, pasting, moving, etc.) during the writing process and generating a log file linked to the original document.

Its design goal is not to beautify the writing process, but to faithfully record the editing actions that occurred. It can be used for:

  • Proof of authorship

  • Self-verification in academic integrity and AI controversies

  • Writing behavior analysis/review

  • Replay of long document writing process




✨ Features
======

  • Real-time automatic recording: All editing actions are monitored and recorded without manual saving or triggering.

  • Per-note logging: Each note has its own corresponding log file, stored in the `log/` folder in the same directory.

  • Frontmatter control (non-intrusive): Recording only occurs when `writeTrack: true` is enabled in the document.

  • High semantic event recognition


  Log includes:
  ---

---
  • TYPE: Text input (sentence/fragment level)

  • DEL: Delete operation

  • PASTE: Paste

  • MOVE: Cut + Paste automatically recognized as "Move"

  • REPL: Replace (Delete + Input)

  • UNDO / REDO

---

  • Position awareness

  • All operations have @LxCy row and column coordinates

  • MOVE supports @from → @to

  • Readable log (not diff)

  • Color-coded to distinguish different operation types

  • Human-readable, not Git diff



🧠 Design Philosophy (Very Important)
===

This plugin records what happened, not what "should" have happened.

  • ❌ Does not attempt to "eliminate typo"

  • ❌ Does not guess the author's intention

  • ❌ Does not rewrite history

Authenticity ≠ Cleanliness 
---

The authentic writing process inherently involves hesitation, revision, and iteration.

All "smart cleaning/merging/summarizing" should occur after the log is logged, not during the logging phase.

This allows the log to serve as:

  • Reproducible evidence

  • Auditable records

  • Original data source



📁 File Structure
===

---
MyNote.md

log/

└── MyNote.log.md

---

The log file is automatically created. Example format:

2026-01-28 22:04:28 MOVE @L17C1→L16C19 = "This is sentence 2"

2026-01-28 22:04:30 TYPE @L19C2 + "Finish."

⸻

⚙️ Usage
===

1️⃣ Enable tracking (single file)
---

Add the following to the note's frontmatter:

---
writeTrack: true

---
Or use the command palette:

---
Writing Live Track: Toggle tracking for current note

---

2️⃣ Start writing
---

The plugin will automatically:

• Create a log file

• Optional: Insert log links in the body of the text

• Real-time recording of editing actions



🎛 Settings
===

• Global enable
Global toggle

• Skip frontmatter
Do not record edits to the frontmatter area

• Sentence gap (ms)
Time aggregation window for TYPE actions

• Edit gap (ms)
Merge window for DEL actions

• Log folder name
Log folder name (default: log)



🧪 What This Plugin Is Not
===

• ❌ Writing statistics (word count / duration)

• ❌ Writing scoring tool

• ❌ AI detector

• ❌ Automatic proofreading tool

If you want a “clean writing summary,” you should analyze after the log, not modify the facts during the recording stage.

⸻

🔒 Privacy & Data
===

• All data is stored locally in Vault.

• No internet connection.

• No uploads.

• No content analysis.

⸻

📌 Intended Use Cases
===

• Academic integrity & authorship proof

• Long-form writing documentation

• Research on writing behavior

• Personal writing process review

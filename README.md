# Daily Standup

A browser-based standup tool for remote teams of 3–6 people. No backend, no database, no server — open the HTML file and go.

---

## What's New

- **Complete standup workflow** — setup → per-person standup → summary with export; zero dependencies, single HTML file
- **Per-person timer with warning system** — 30s warning beep + pulse animation, expired alert tone, adjustable 30s–3min
- **Star rating with mood labels** — 1–5 star sprint mood rating with contextual labels (Needs improvement → Excellent)
- **Drag-and-drop team reorder** — native HTML5 drag-and-drop to rearrange members during setup
- **Auto-blocker detection** — blocker field highlights with badge as soon as text is entered
- **Pause / Resume timer** — for interruptions during standup
- **Skip for absent members** — cleanly marks as not present in summary
- **Shuffle order** — randomize speaking order to keep rotations fair
- **Keyboard shortcuts** — `Ctrl+Enter` to advance, `Ctrl+Shift+S` to skip
- **Session timer** — live meeting duration displayed in the top bar
- **Progress bar** — fixed progress bar showing completion percentage
- **Sound effects** — Web Audio API synthesized beeps, warning tones, expiration sound, and completion fanfare; toggle on/off
- **Dark mode** — toggle accessible from every screen, persisted via localStorage
- **Scribe notes** — add meeting notes during or after the standup, save to session
- **Per-person time tracking** — time spent per member displayed in summary
- **PDF export** — opens a print-formatted summary window → Save as PDF via native dialog
- **Confetti celebration** — canvas-based particle animation on completion
- **Session persistence** — auto-saves to localStorage; resume banner on page reload; discard option
- **Settings persistence** — dark mode, sound toggle, and time limit remembered across sessions
- **Toast notifications** — non-intrusive feedback for save and other actions
- **Min 2-member validation** — start button disabled with validation message until 2+ members added
- **Mobile responsive** — optimized layout for screens up to 500px wide
- **Custom initials avatars** — colored circles with 2-letter initials, fixed 6-color palette
- **Settings panel** — collapsible panel in setup with time slider, sound toggle, dark mode toggle
- **Blocker count in summary** — total blocker count shown in summary header
- **Modern typography** — DM Serif Display (headings) + Inter (body), monospace timer font

All features above are implemented in a **single HTML file** with no external runtime dependencies, no build step, and no external assets.

---

## Requirements Fulfilled

| Requirement | Status |
|---|---|
| **Zero dependencies** — single HTML file, no build step | ✅ |
| **Three-question format** (yesterday / today / blockers) | ✅ |
| **Adjustable per-person timer** (30s–3min) | ✅ |
| **30s warning** (visual + audio) | ✅ |
| **Expired alert** (visual + audio) | ✅ |
| **Pause / Resume timer** | ✅ |
| **Skip absent members** | ✅ |
| **Star rating** (1–5 sprint mood) | ✅ |
| **Drag-and-drop reorder** | ✅ |
| **Randomize speaking order** | ✅ |
| **Keyboard shortcuts** — submit & skip | ✅ |
| **Dark mode** — persisted | ✅ |
| **Sound effects** — Web Audio API, no external files | ✅ |
| **Session timer** — live meeting duration | ✅ |
| **Progress bar** — completion tracking | ✅ |
| **Blocker detection** — auto-highlight with badge | ✅ |
| **Scribe / meeting notes** | ✅ |
| **PDF export** — via print dialog | ✅ |
| **Confetti celebration** | ✅ |
| **Session persistence** — survives tab close via localStorage | ✅ |
| **Settings persistence** — preferences remembered | ✅ |
| **Mobile responsive** | ✅ |
| **Initials avatars** — no uploads needed | ✅ |
| **Per-person time tracking** | ✅ |
| **Toast notifications** | ✅ |

---

## Features

### Setup
- Add team members by name with Enter key or button
- Remove members with × button on name tags
- Drag-and-drop to reorder speaking sequence
- Shuffle/Randomize order button
- Collapsible settings panel with time limit slider, sound toggle, dark mode toggle
- Minimum 2 members validation before start

### Standup
- Per-person timer countdown with MM:SS display
- 30s warning: dual-tone beep + pulse animation
- Expired state: descending 3-note tone + pulsing red timer
- Pause / Resume timer control
- 1–5 star mood rating with descriptive labels
- Three text fields: Yesterday, Today, Blockers
- Auto-blocker highlighting — badge appears when blocker text is entered
- Next Person enabled only when at least one field has content
- Skip button for absent members
- Keyboard shortcuts: `Ctrl+Enter` (submit), `Ctrl+Shift+S` (skip)
- Live session timer in top bar
- Dark mode toggle accessible mid-standup

### Summary
- Header with participant count, total session time, blocker count
- Per-person cards with avatar, name, star rating, time spent
- Yesterday / Today / Blockers sections
- Skipped members shown as "not present"
- Scribe / Meeting notes textarea with save button
- Download PDF — opens print-formatted summary in new window
- New Standup — clears session and returns to setup
- Completion fanfare sound + confetti particle animation

### Persistence
- **Session**: auto-saves to localStorage on every render; resume banner prompts to continue or discard on page reload
- **Preferences**: dark mode, sound enabled, time limit saved/loaded independently

### Export
- **PDF**: generates a clean, print-formatted summary with all member data, meeting notes, and metadata → opens native print dialog (Save as PDF)

---

## Key Decisions

- **No build step, no dependencies** — a single HTML file that works in any modern browser. Open it from disk or host it on any static server.
- **Web Audio API for sounds** — avoids external audio files; beeps, tones, and a completion fanfare are synthesized at runtime.
- **localStorage for persistence** — session and preferences survive page refreshes and accidental closes. The resume banner prompts to continue where you left off.
- **Vanilla CSS with CSS custom properties** — dark mode is a single class toggle on `<body>` that swaps every color variable. No runtime stylesheet switching.
- **Initials avatars** — colored circles derived from each person's name, using a fixed palette of 6 colors. No uploads, no complexity.
- **HTML5 Drag and Drop API** — native browser drag-and-drop for reordering team members, no library needed.
- **PDF via print dialog** — opens a new window with the summary formatted for printing, then triggers the native print dialog (Save as PDF). No PDF library required.
- **Confetti canvas** — a lightweight particle system rendered on a `<canvas>` overlay in ~40 lines. Adds ceremony without a library.
- **CSS custom properties for theming** — dark mode toggles a `.dark` class that swaps all color variables at once.

---

## Usage

1. Open `standup.html` in any modern browser
2. Add team member names — drag to reorder them
3. Adjust time limit and sound/dark settings if desired
4. Click **Start Standup**
5. Each person speaks in turn — type or dictate notes as they go
6. Review the summary, add meeting notes, and click **Download PDF** to save

# Release Notes

## v1.2.2 — March 2026

### New Features
- **Enriched document statistics** — The statistics panel now includes a pacing chart, Flesch readability score, dialogue ratio, vocabulary richness, and estimated reading and speaking times
- **Cloud disconnection recovery** — Storytellr now detects when your cloud storage connection drops and shows a recovery prompt, so you never lose track of where your file is saved
- **Animated sidebar tooltips** — Hover over any sidebar icon to see a smooth, instant tooltip identifying the button

### Improvements
- Improved cloud sync reconnect flow, including a remote changes check on reconnect
- Read aloud in Chrome now handles long documents correctly by chunking text to avoid the browser's silent length limit
- Story files are now gzip-compressed, reducing file sizes by ~68% — a 6.5 MB file saves as ~2.1 MB. Existing files are upgraded to the new format on next save

### Bug Fixes
- Fixed paste sometimes creating nested paragraphs that broke text indentation
- Fixed cloud disconnect modal appearing incorrectly on a fresh connection
- Fixed navigation reordering, undo/redo, and session handling edge cases
- Fixed mobile placeholder text alignment and wrapping
- Fixed mobile file menu padding
- Fixed Android Chrome system navigation bar appearing white instead of matching the app theme
- Fixed opening files in Edge on Android crashing the browser

---

## v1.2.0 — February 2026

### New Features
- **Cloud connection timeout system** — Connections that stall now time out gracefully with a clear explanation rather than hanging indefinitely
- **Code splitting** — The app now loads faster on first open by splitting the bundle into smaller on-demand chunks

### Improvements
- Pre-GA security hardening: HTML sanitization, stricter Content Security Policy, and safer OAuth handling
- Unified click-action animations across all interactive elements for a more consistent feel
- Customizable notebook tab colors using the accent color system
- Animated welcome screen placeholder cycles through classic story openers

### Bug Fixes
- Removed unimplemented notebook linking feature that showed a dead-end UI
- Various theme variable and CSS consistency fixes

---

## v1.1.0 — January 2026

### New Features
- **Dropbox and Box cloud storage** — Open and save your story files directly to Dropbox or Box, joining Google Drive and OneDrive support
- **Version history** — Storytellr automatically tracks your last 5 manual saves and last 5 auto-saves inside the story file itself. Browse, preview, and restore any previous version from the File menu
- **Cloud file conflict detection** — If your story file was changed externally while you were writing, Storytellr prompts you to resolve the conflict instead of silently overwriting
- **PKCE OAuth** — Cloud authentication now uses the more secure PKCE flow with refresh tokens, so you stay signed in without re-authorizing on every session

### Improvements
- Simplified File menu — fewer items, clearer labels
- Delete cloud files directly from the Open dialog
- HSL-based accent color system for more harmonious theme customization

---

## v1.0.0 — January 2026

Initial release of Storytellr.

### Core Writing
- Distraction-free manuscript editor with adjustable zoom and font settings
- Auto-save with configurable interval and emergency save on large edits
- Find & Replace with bulk formatting (bold, italic, case transforms)
- Full undo/redo history

### Organization
- **Bookmarks** — Mark any position in your manuscript and jump back instantly
- **Notes** — Attach inline notes to sections of text
- **Notebook** — A separate freeform writing space for research, outlines, and ideas

### Cloud Storage
- Open and save directly to Google Drive or OneDrive
- Recent files list with starred favorites

### Export
- Export to PDF, Word (.docx), plain text, and formatted HTML
- Manuscript formatting presets

### Accessibility & Comfort
- **Read Aloud** — Text-to-speech with word-by-word highlighting
- Light, dark, and sepia themes
- Mobile and tablet support

# Storytellr User Guide

A complete guide to using Storytellr for fiction manuscript preparation.

## Table of Contents
- [Getting Started](#getting-started)
- [The Editor](#the-editor)
- [Formatting Text](#formatting-text)
- [Manuscript Settings](#manuscript-settings)
- [Working with Notes](#working-with-notes)
- [Dictionary & Thesaurus](#dictionary--thesaurus)
- [Notebook & Research](#notebook--research)
- [Navigation](#navigation)
- [Find & Replace](#find--replace)
- [Exporting](#exporting)
- [Customization](#customization)


## Cloud File Usage & Sync

### How Cloud Files Work

When you open a file from a connected cloud provider (e.g., OneDrive, Google Drive, Dropbox, or Box), Storytellr saves your edits directly back to the cloud storage. You do not need to manually upload or download files—changes are synced automatically.

- **Autosave**: Edits are saved to the cloud every few seconds, just like with local files.
- **Sync**: If you open the same file on another device, changes will appear within a few seconds (depending on your cloud provider's sync speed).
- **No manual upload needed**: The app handles saving and syncing for you.
- **Conflict detection**: If you edit the same file on multiple devices at once, a conflict dialog will help you resolve differences.

#### Usage Details

1. Open a file from your cloud provider using the Cloud Files browser.
2. Edit as usual—your changes are saved to the cloud automatically.
3. To access your work elsewhere, open the same file from the cloud on another device.
4. If you lose connection, changes will sync as soon as the connection is restored.


**Tip:** For best results, avoid editing the same file on two devices at the exact same time.

#### Recent Files Icons

In the Recent Files list, a small icon appears next to each filename:

- <img src="../docs/svg/cloud.svg" alt="Cloud icon" style="height:1em;vertical-align:middle;"> indicates a cloud file (OneDrive, Google Drive, Dropbox, or Box)
- <img src="../docs/svg/hard-drive.svg" alt="Hard drive icon" style="height:1em;vertical-align:middle;"> indicates a local file

These icons are visually aligned with the filename for clarity.

### Creating a New Story

1. Click **New Story** on the welcome screen
2. Choose where to save your story file (`.html` format)
3. Grant file system access when prompted
4. Start writing!

### Opening an Existing Story

1. Click **Open Story**
2. Navigate to your story file (`.html` format)
3. The app will restore your document and all settings

### Auto-Save

Storytellr includes intelligent auto-save with multiple safeguards to protect your work:

- **Smart thresholds**: Saves 5 seconds after you stop typing (requires 20+ character change)
- **Emergency saves**: Immediate save for large edits (100+ characters)
- **No manual saves needed**: Your work is continuously protected
- **Persistent file access**: File handles survive browser sessions
- **Memory efficient**: Character thresholds prevent saves from tiny edits like typo fixes
- **Browser close protection**: Emergency localStorage backup if browser closes unexpectedly

#### Save Thresholds

- **Small edits (< 20 characters)**: No save to prevent memory churn from typo fixes
- **Normal edits (20-99 characters)**: Save 5 seconds after you stop typing
- **Large edits (100+ characters)**: Immediate emergency save (no 5-second delay)

#### Data Protection Features

Storytellr includes comprehensive safeguards against data loss:

- **Blank document protection**: Prevents saving empty files over your work
- **Significant loss detection**: Warns when large amounts of content are being deleted
- **Concurrent save prevention**: Blocks overlapping save operations that could corrupt data
- **Automatic recovery**: Restores content from cloud if browser storage becomes corrupted
- **Conflict detection**: Identifies external changes before saving to prevent overwrites
- **Transaction rollback**: Reverts failed saves to preserve your data integrity
- **Unsaved changes warning**: Browser prompts before closing tab with unsaved work

#### How Protection Works

When auto-save runs, Storytellr performs multiple validation checks:

1. **Word count verification**: Compares current content to last saved version
2. **Significant loss check**: Blocks saves if you've lost more than 30% of your content
3. **Blank document check**: Prevents overwriting your work with empty content
4. **External change detection**: Checks if file was modified elsewhere before saving
5. **State synchronization**: Ensures browser storage matches your actual document

If validation detects a problem, you'll see a warning dialog explaining the issue and your options. Your content is never automatically overwritten when something looks wrong.

## The Editor

### Continuous Writing

The editor provides an uninterrupted writing surface:
- No pagination during writing
- Scroll seamlessly through your entire manuscript
- Word count and page estimates update in real-time
- Focus on content, not layout

### Statistics

Located at the bottom of the editor:
- **Word Count**: Total words in your manuscript
- **Page Count**: Estimated pages based on standard manuscript format (250 words per page)

### Smart Features

- **Automatic Cleanup**: Empty paragraphs are removed automatically
- **Heading IDs**: Headings get unique IDs for navigation
- **Em-Dash Conversion**: Type `--` (two hyphens) to create em-dashes (when enabled)

## Formatting Text

### Using the Floating Toolbar

Select text to reveal the floating toolbar with these options:

#### Text Styling
- **Bold** (Ctrl/Cmd+B): Emphasize text
- **Italic** (Ctrl/Cmd+I): Italicize text
- **Underline** (Ctrl/Cmd+U): Underline text

#### Block Formatting
- **H1 (Chapter Heading)**: Major chapter divisions
- **H2 (Section Break)**: Scene breaks within chapters
- **P (Paragraph)**: Regular body text
- **Q (Block Quote)**: Indented quotations

#### Alignment
- **Left**: Default paragraph alignment
- **Center**: Centered text (useful for scene breaks)
- **Right**: Right-aligned text
- **Justify**: Fully justified paragraphs

#### Notes
- **Add Note**: Create a linked annotation (see Notes section)

### Smart Positioning

The floating toolbar automatically positions itself:
- Opens above selection when space is available
- Opens below when near the top of the viewport
- Dropdowns adjust direction to stay visible

## Manuscript Settings

Access via the **Settings** button (⚙️) in the toolbar.

### Font Selection

Choose from professional manuscript fonts:
- **Times New Roman**: Traditional serif (most common)
- **Arial**: Clean sans-serif

### Chapter Spacing

Control where chapter headings appear on the page:
- **1/3 Page**: Chapters start one-third down the page (traditional)
- **1/2 Page**: Chapters start halfway down the page (dramatic)

### Title Page

- **Include Title Page**: Adds a formatted title page to exports
  - Includes manuscript title, author name, and word count
  - Follows standard manuscript format

### Headers & Footers

Configure manuscript headers:
- **Enable Headers**: Toggle header inclusion in exports
- **Author Name (Last)**: Your last name for the header
- **Manuscript Title**: Short title for the header
- **Format**: Choose header layout:
  - `LastName / TITLE / PageNumber`
  - `TITLE / LastName / PageNumber`
- **First Page Different**: Skip header on first page

### Theme

- **Accent Color**: Choose UI highlight color
- **Dark/Light Mode**: Toggle in main interface

### Auto-Features

- **Auto-Convert Dashes**: Convert `--` to em-dashes automatically

### Settings Behavior

- Settings are **saved with your document**
- Each story file has its own settings
- Settings **reset to defaults** when you close a document
- Settings **auto-load** when you reopen a document

## Working with Notes

### Creating a Note

1. Select text in your manuscript
2. Click **Add Note** in the floating toolbar
3. The text will be highlighted in the editor
4. A note editor appears in the Notes panel
5. Type your annotation

### Managing Notes

- **Edit**: Click the highlighted text to jump to the note
- **Delete**: Use the delete button in the Notes panel
- **Scroll**: Notes panel scrolls to show the active note
- **Visual Link**: Highlighted text is visually connected to its note

### Use Cases

- Character development reminders
- Plot point tracking
- Research notes tied to specific passages
- Revision reminders
- Continuity tracking

## Dictionary & Thesaurus

### Looking Up Words

1. Select any word in your manuscript
2. Open the Dictionary panel
3. View:
   - **Definition**: Word meaning and part of speech
   - **Synonyms**: Alternative words with similar meaning
   - **Antonyms**: Opposite words
   - **Similar Words**: Related terms
   - **Triggered Words**: Associated concepts

### Drag & Drop Replacement

The fastest way to replace words:

1. Select a word in your editor
2. Open Dictionary panel to see synonyms
3. **Drag a synonym chip** into your editor
4. Drop it over the selected word to replace
5. Spacing is preserved automatically

### Manual Replacement

- Click a synonym chip to copy it
- Paste it manually if preferred

### Tips

- The selection automatically includes trailing spaces
- Dropped words maintain proper spacing
- Works with any word in the synonym lists

## Notebook & Research

### Notebook Panel

A separate space for:
- Character profiles
- Plot outlines
- World-building notes
- Research compilation
- Scene planning

### Creating Notes

1. Open the Notebook panel
2. Click **Add Note**
3. Notes are saved with your story file
4. Notes are separate from linked annotations

### Organizing

- Create multiple notebook entries
- Use for different aspects of your story
- Access anytime while writing

### External Files

- Save notebook as separate `.storynote` files
- Load external research files
- Keep notebook separate from manuscript if preferred

## Navigation

### Navigation Panel

Shows document structure:
- **H1 Headings**: Chapter titles
- **H2 Headings**: Scene breaks
- Click any heading to jump to that location

### Quick Navigation

- Open Navigation panel (left sidebar)
- See your entire manuscript structure
- Click to jump between sections
- Useful for long manuscripts

## Find & Replace

### Opening Find & Replace

- Use keyboard shortcut (Ctrl/Cmd+F)
- Or click Find icon in toolbar

### Find Options

- **Find**: Search term
- **Replace**: Replacement text (optional)
- **Match Case**: Case-sensitive search
- **Whole Word**: Match complete words only

### Navigation

- **Previous**: Jump to previous match
- **Next**: Jump to next match
- Matches are highlighted in yellow
- Current match highlighted in orange

### Replace Operations

- **Replace**: Replace current match
- **Replace All**: Replace all matches at once

### Format Replacement

Change formatting for all matches:

1. Enter search term
2. Select target format from dropdown:
   - Chapter Heading (H1)
   - Section Break (H2)
   - Paragraph (P)
   - Block Quote (Q)
3. Click **Replace All** or **Replace**
4. Block-level formatting is applied correctly
5. Headings receive unique IDs automatically

### Tips

- Use "Whole Word" to avoid partial matches
- Format replacement works on block elements
- All replacements can be undone (Ctrl/Cmd+Z)

## Exporting

See [EXPORT_GUIDE.md](EXPORT_GUIDE.md) for detailed export documentation.

### Quick Export

1. Click **File** → **Export**
2. Choose format: TXT, DOCX, or PDF
3. Select save location
4. Export uses your manuscript settings

### Export Formats

- **TXT**: Plain text, no formatting
- **DOCX**: Word document with styles and navigation
- **PDF**: Camera-ready with headers and page numbers

### What Gets Exported

All manuscript elements:
- Chapter headings (H1)
- Section breaks (H2)
- Block quotes
- Formatted text (bold, italic, underline)
- Headers and page numbers (if enabled)
- Title page (if enabled)

## Customization

### Panel Layout

**Resizable Panels**:
- Drag resize handles to adjust panel widths
- Panels remember their size
- Create your perfect workspace

**Collapsible Panels**:
- Navigation (left)
- Notes (right)
- Dictionary (right)
- Notebook (right)

### Editor Customization

**Width Control**:
- Adjust editor width to comfortable reading size
- Useful for different screen sizes

**Zoom Control**:
- Zoom: 50% to 200%
- Increase for better visibility
- Decrease to see more content

### Interface Theme

- **Dark Mode**: Reduced eye strain for long sessions
- **Light Mode**: Traditional bright interface
- **Accent Color**: Personalize UI highlights

### Persistence

All customization settings:
- Save with your document
- Restore when reopening
- Reset when closing document

## Keyboard Shortcuts

### Text Editing
- `Ctrl/Cmd+B`: Bold
- `Ctrl/Cmd+I`: Italic
- `Ctrl/Cmd+U`: Underline
- `Ctrl/Cmd+Z`: Undo
- `Ctrl/Cmd+Y`: Redo

### File Operations
- `Ctrl/Cmd+S`: Manual save
- `Ctrl/Cmd+O`: Open file
- `Ctrl/Cmd+N`: New file

### Navigation
- `Ctrl/Cmd+F`: Find & Replace
- `Ctrl/Cmd+G`: Find next
- `Ctrl/Cmd+Shift+G`: Find previous

## Tips for Best Experience

### Writing Workflow

1. **Start with structure**: Use H1 for chapters before writing
2. **Use H2 for scenes**: Break chapters into manageable scenes
3. **Link notes liberally**: Capture ideas without leaving flow
4. **Leverage thesaurus**: Drag-and-drop for quick word improvements
5. **Export often**: Test your formatting before submission

### Performance

- Auto-save works best with stable file system access
- Cloud sync works seamlessly with OneDrive, Google Drive, Dropbox, or Box
- Large manuscripts (100k+ words) perform smoothly
- Browser needs file system permissions for full functionality

### Troubleshooting

- **Changes not saving**: Check file permissions
- **Sync conflicts**: See conflict resolution dialog
- **Speech issues**: See [SPEECH_TROUBLESHOOTING.md](SPEECH_TROUBLESHOOTING.md)
- **Firefox limitations**: See [FIREFOX_COMPATIBILITY.md](FIREFOX_COMPATIBILITY.md)

## Getting Help

- Check documentation in `/docs` folder
- Review feature-specific guides
- Verify browser compatibility
- Ensure file system permissions are granted

# Storytellr Features Reference

Complete reference documentation for all features in Storytellr.

## Table of Contents
- [Core Features](#core-features)
- [Editor Features](#editor-features)
- [Formatting Features](#formatting-features)
- [Manuscript Features](#manuscript-features)
- [Productivity Features](#productivity-features)
- [File Management](#file-management)
- [Customization Features](#customization-features)
- [Export Features](#export-features)

## Core Features

### Continuous Editor

**Description**: Seamless writing environment without page breaks during composition.

**Key Characteristics**:
- No pagination during writing
- Scroll freely through entire manuscript
- Page count calculated in real-time
- Focus on content, not layout

**Benefits**:
- Uninterrupted creative flow
- No artificial page break management
- Natural writing experience
- Professional formatting applied on export

### Auto-Save System

**Description**: Automatic document persistence with comprehensive data protection and intelligent change detection.

**How It Works**:
- Monitors for content changes
- Saves after 3 seconds of inactivity
- Validates content before every save
- Detects external file changes
- Resolves conflicts when detected
- Rolls back failed saves automatically

**Data Protection Features**:
- **Blank document prevention**: Blocks saving empty files over existing content
- **Significant loss detection**: Warns when 30%+ of content would be deleted
- **Large deletion confirmation**: Confirms when 10+ paragraphs are deleted at once
- **Concurrent save prevention**: Mutex prevents overlapping save operations
- **Transaction semantics**: Failed saves are rolled back to preserve data
- **Automatic recovery**: Restores from cloud if browser storage is corrupted
- **Undo/redo state sync**: Ensures validation works correctly after undo operations
- **Unsaved changes warning**: Browser prompts before closing tab with unsaved work

**Technical Details**:
- 3-second debounce timer
- Fresh word count calculation (bypasses stale React state)
- Deep cloning for state snapshots (JSON.parse/stringify)
- eTag-based conflict detection for cloud files
- AdaptiveFileChangeDetector monitors external changes
- IndexedDB stores file handles
- Save mutex (isSavingRef) for concurrent operation prevention
- Version history corruption filtering on initialization

**See Also**: [DATA_SAFETY.md](DATA_SAFETY.md) for detailed information about data protection mechanisms.

### Real-Time Statistics

**Description**: Live word count and page estimation.

**Metrics Provided**:
- **Word Count**: Total words in manuscript
- **Page Count**: Estimated pages (250 words per page standard)

**Display Location**:
- Bottom of editor
- Always visible
- Updates in real-time as you type

**Calculation**:
- Word count: Actual word count from content
- Page count: `Math.ceil(wordCount / 250)`

## Editor Features

### Smart Cleanup

**Description**: Automatic removal of empty paragraphs.

**What It Does**:
- Removes empty `<p></p>` tags
- Preserves `<p><br></p>` (needed for cursor positioning)
- Runs automatically during editing
- Prevents cluttered HTML

**Why It Matters**:
- Cleaner document structure
- Better performance
- Professional exports
- Easier navigation

### Heading IDs

**Description**: Automatic unique identifier generation for headings.

**What It Does**:
- Generates IDs for H1, H2, H3 elements
- IDs are unique and sequential
- Used for navigation
- Preserved across edits

**Format**:
- `heading-1`, `heading-2`, `heading-3`, etc.
- Sequential numbering

**Benefits**:
- Enables navigation panel
- Allows bookmark linking
- Supports find & replace targeting

### Em-Dash Conversion

**Description**: Automatic conversion of double hyphens to em-dashes.

**How It Works**:
- Type `--` (two hyphens)
- Automatically converts to em-dash (—)
- Must be enabled in manuscript settings

**Use Cases**:
- Dialogue: "I thought — no, I knew — it was true."
- Parenthetical phrases: "The solution — if one exists — is unclear."
- Dramatic pauses: "The door opened — slowly."

**Settings**:
- Enable/disable in Manuscript Settings
- Per-document setting
- Applies during typing

## Formatting Features

### Text Styling

**Bold**:
- Keyboard: `Ctrl/Cmd+B`
- Toolbar: Bold button
- Emphasizes text
- Exports to all formats

**Italic**:
- Keyboard: `Ctrl/Cmd+I`
- Toolbar: Italic button
- Stylizes text
- Exports to all formats

**Underline**:
- Keyboard: `Ctrl/Cmd+U`
- Toolbar: Underline button
- Underlines text
- Exports to all formats

### Block Formatting

**H1 - Chapter Heading**:
- Major chapter divisions
- Positioned 1/3 or 1/2 page in exports
- Appears in navigation panel
- Word Heading 1 style in DOCX

**H2 - Section Break**:
- Scene breaks within chapters
- Centered automatically
- Proper spacing in exports
- Word Heading 2 style in DOCX

**P - Paragraph**:
- Regular body text
- Double-spaced in exports
- First-line indent (0.5 inches)
- No indent after headings

**Q - Block Quote**:
- Indented quotations
- 0.5-inch left indent in exports
- Single paragraph formatting
- Inline formatting preserved

### Alignment

**Options**:
- Left (default)
- Center
- Right
- Justify

**Application**:
- Paragraph-level
- Exports to DOCX and PDF
- Toolbar or keyboard shortcuts

### Floating Toolbar

**Description**: Context-sensitive formatting toolbar that appears on text selection.

**Features**:
- Appears when text is selected
- Disappears when selection is cleared
- Contains all formatting options
- Smart positioning (above/below)

**Smart Positioning**:
- Opens above selection when space available
- Opens below when near viewport top
- Dropdowns adjust direction
- Always stays visible

**Contents**:
- Text styling (bold, italic, underline)
- Block formatting (H1, H2, P, Q)
- Alignment options
- Note creation button

## Manuscript Features

### Font Selection

**Available Fonts**:
- **Times New Roman**: Traditional serif, most common for submissions
- **Arial**: Clean sans-serif

**Application**:
- Applies to all exports
- Does not affect editor appearance
- Per-document setting

### Chapter Spacing

**Options**:
- **1/3 Page**: Traditional manuscript format
- **1/2 Page**: Dramatic chapter openings

**How It Works**:
- H1 headings positioned accordingly
- Followed by page break
- Applies to DOCX and PDF exports

**Technical Details**:
- 1/3 page: 3847 twips from top
- 1/2 page: 6480 twips from top

### Title Page

**Description**: Formatted title page for professional submissions.

**Content**:
- Manuscript title (centered, upper third)
- Author name (centered)
- Word count (rounded to nearest 1000)

**Settings**:
- Enable/disable in Manuscript Settings
- Included in DOCX and PDF exports
- Standard submission format

**Format**:
```
[1/3 down page]

MANUSCRIPT TITLE
by
Author Name

Approximately 85,000 words
```

### Headers & Page Numbers

**Configuration**:
- Author last name
- Manuscript title
- Page number format
- First page different option

**Formats**:
- `LastName / TITLE / PageNumber`
- `TITLE / LastName / PageNumber`

**Application**:
- Top of each page
- Customizable per document
- Standard manuscript format

**First Page Different**:
- Skips header on first page
- Standard for submissions
- Enable/disable as needed

### Theme Customization

**Accent Color**:
- Choose UI highlight color
- Affects buttons, highlights, selections
- Per-document setting
- Saved with manuscript

**Dark/Light Mode**:
- Toggle in main interface
- Optimized for extended writing
- Eye-friendly color schemes

## Productivity Features

### Notes System

**Description**: Link annotations to specific passages in your manuscript.

**Creating Notes**:
1. Select text in manuscript
2. Click "Add Note" button
3. Highlighted in editor
4. Note editor appears in Notes panel

**Features**:
- Visual highlights in text
- Linked to specific passages
- Click highlight to view note
- Delete notes when resolved

**Use Cases**:
- Character development reminders
- Plot point tracking
- Research notes
- Revision reminders
- Continuity tracking

### Notebook Panel

**Description**: Separate workspace for research and planning.

**Features**:
- Multiple notes
- Separate from manuscript
- Saved with story file
- Can export separately

**Use Cases**:
- Character profiles
- Plot outlines
- World-building notes
- Research compilation
- Scene planning

**File Management**:
- Save as `.storynote` files
- Load external notes
- Keep separate from manuscript
- Organize research

### Dictionary & Thesaurus

**Description**: Built-in word lookup with drag-and-drop replacement.

**Features**:
- Definitions
- Synonyms
- Antonyms
- Similar words
- Triggered words (associations)

**Data Source**:
- datamuse API
- Real-time lookups
- Comprehensive coverage

**Drag & Drop**:
- Select word in editor
- Drag synonym chip into editor
- Drop to replace
- Spaces preserved automatically

**Benefits**:
- Fast word replacement
- Explore alternatives
- Improve vocabulary
- No context switching

### Navigation Panel

**Description**: Document structure overview with quick navigation.

**Features**:
- Shows all H1 and H2 headings
- Click to jump to section
- Collapsible panel
- Updates automatically

**Use Cases**:
- Long manuscript navigation
- Chapter organization review
- Quick section access
- Structure visualization

### Find & Replace

**Description**: Advanced search with formatting support.

**Features**:
- Text search
- Replace functionality
- Match case option
- Whole word matching
- Format conversion

**Search Options**:
- Find: Search term
- Replace: Replacement text
- Match Case: Case-sensitive
- Whole Word: Complete words only

**Navigation**:
- Next/Previous match
- Replace current
- Replace all
- Visual highlighting

**Format Replacement**:
- Convert matches to H1, H2, P, or Q
- Replaces block element correctly
- Generates heading IDs automatically
- Preserves text content

**Keyboard Shortcuts**:
- `Ctrl/Cmd+F`: Open Find & Replace
- `Ctrl/Cmd+G`: Find next
- `Ctrl/Cmd+Shift+G`: Find previous

## File Management

### File System Access API

**Description**: Native browser access to local file system.

**Features**:
- Direct file access
- No upload/download needed
- File handle persistence
- Seamless integration

**Supported Operations**:
- Create new files
- Open existing files
- Save changes
- Detect external changes

**File Format**:
- `.story` extension
- JSON structure
- Includes content, notes, notebook, settings

### Cloud Sync Integration

**Description**: Works seamlessly with cloud storage providers.

**Supported Services**:
- OneDrive
- Dropbox
- Google Drive
- Any cloud-synced folder

**How It Works**:
1. Save `.story` file to cloud folder
2. Open same file on another device
3. Changes sync through cloud provider
4. App detects external changes

**Conflict Resolution**:
- Detects simultaneous edits
- Presents resolution options:
  - Keep local changes
  - Use remote changes
  - Save both versions

**Sync Timing**:
- Changes appear within 2-5 seconds
- Depends on cloud provider
- No internet needed (local edits)

### Auto-Load on Refresh

**Description**: Automatically restores last open file on page refresh.

**How It Works**:
- File handle stored in IndexedDB
- Retrieved on page load
- File content loaded automatically
- Settings restored

**Benefits**:
- Resume work seamlessly
- No re-opening files
- Settings preserved
- Work context maintained

### File Change Detection

**Description**: Monitors for external file modifications.

**How It Works**:
- AdaptiveFileChangeDetector monitors file
- Polls file system periodically
- Detects timestamp changes
- Triggers conflict resolution

**Conflict Handling**:
- Presents conflict dialog
- Three resolution options
- No data loss
- User chooses resolution

### Recent Files

**Description**: Track recently opened files for quick access.

**Features**:
- List of recent `.story` files
- Quick re-open
- Stored in localStorage
- Persists across sessions

## Customization Features

### Resizable Panels

**Description**: Drag to resize navigation, notes, dictionary, and notebook panels.

**Features**:
- Drag resize handles
- Sizes persist with document
- Independent sizing
- Responsive layout

**Panels**:
- Navigation (left)
- Notes (right)
- Dictionary (right)
- Notebook (right)

### Editor Width

**Description**: Adjust editor width for comfortable reading.

**Range**: Variable based on screen size

**Use Cases**:
- Wider screens: Limit width for readability
- Narrower screens: Maximize space
- Personal preference
- Accessibility

### Zoom Control

**Description**: Adjust editor text size.

**Range**: 50% to 200%

**Features**:
- Incremental adjustments
- Persists per document
- Affects editor only
- Not export size

**Use Cases**:
- Better visibility
- Accessibility
- Personal preference
- Screen size adjustment

### Theme Modes

**Light Mode**:
- Traditional bright interface
- High contrast
- Daytime use

**Dark Mode**:
- Reduced eye strain
- Low light environments
- Extended writing sessions

**Accent Color**:
- Customizable highlight color
- Affects UI elements
- Per-document setting

### Settings Persistence

**Description**: All settings save with document and reset on close.

**Behavior**:
- Settings save with `.story` file
- Auto-load when opening document
- Reset to defaults when closing document
- Each document has independent settings

**Included Settings**:
- Manuscript settings (font, spacing, headers)
- Theme (accent color, mode)
- Panel sizes and visibility
- Editor width and zoom

## Export Features

### Export Formats

**TXT (Plain Text)**:
- All text content
- No formatting
- Universal compatibility
- Backup purposes

**DOCX (Microsoft Word)**:
- Formatted document
- Heading styles (Heading 1, Heading 2)
- Word navigation integration
- Editable in Microsoft Word
- Track changes compatible

**PDF (Portable Document Format)**:
- Camera-ready format
- Professional layout
- Headers and page numbers
- Print-ready
- Submission format

### Manuscript Formatting

**Applied to Exports**:
- Font from settings
- 12pt font size
- Double-spacing
- 1-inch margins
- Chapter positioning
- Scene break centering
- Block quote indentation
- Header configuration

**Standards Followed**:
- William Shunn manuscript format
- Industry submission standards
- Professional appearance

### Export Workflow

**Process**:
1. Click File → Export
2. Choose format
3. Select save location
4. File generated with settings applied

**What's Included**:
- All manuscript content
- Formatting (bold, italic, underline)
- Headings with proper styles
- Block quotes
- Headers and page numbers (if enabled)
- Title page (if enabled)

**What's Excluded**:
- Notes (annotations)
- Notebook entries
- Editor-only elements

### Format-Specific Features

**DOCX**:
- Word navigation pane integration
- Editable heading styles
- Page numbering system
- Standard Office format

**PDF**:
- Precise layout control
- Non-editable (preserves format)
- Universal compatibility
- Print-ready output

## Technical Features

### React Architecture

**Framework**: React 18.3.1

**Key Patterns**:
- Functional components
- Hooks (useState, useEffect, useRef)
- Context for state management
- Component composition

### Content Editing

**Technology**: contentEditable attribute

**Features**:
- Rich text editing
- Native browser capabilities
- Custom formatting overlay
- Direct DOM manipulation

### Storage Technologies

**IndexedDB**:
- File handle persistence
- Async storage
- Large data capacity

**localStorage**:
- UI preferences
- Recent files list
- Simple key-value storage

### Build Tools

**Vite 6.0.3**:
- Fast development server
- Hot module replacement
- Optimized builds

**Dependencies**:
- jsPDF: PDF generation
- docx v9.5.1: Word document generation
- React: UI framework

### Browser APIs

**File System Access API**:
- Native file operations
- Chrome, Edge, Safari support
- See Firefox compatibility notes

**Selection API**:
- Text selection handling
- Range manipulation
- Cursor positioning

**DataTransfer API**:
- Drag-and-drop support
- Thesaurus integration
- Text replacement

## Keyboard Shortcuts Reference

### Editing
- `Ctrl/Cmd+B`: Bold
- `Ctrl/Cmd+I`: Italic
- `Ctrl/Cmd+U`: Underline
- `Ctrl/Cmd+Z`: Undo
- `Ctrl/Cmd+Y` or `Ctrl/Cmd+Shift+Z`: Redo

### File Operations
- `Ctrl/Cmd+S`: Manual save
- `Ctrl/Cmd+O`: Open file
- `Ctrl/Cmd+N`: New file

### Search
- `Ctrl/Cmd+F`: Open Find & Replace
- `Ctrl/Cmd+G`: Find next
- `Ctrl/Cmd+Shift+G`: Find previous

### Navigation
- `Ctrl/Cmd+Home`: Jump to document start
- `Ctrl/Cmd+End`: Jump to document end

## Platform Compatibility

### Supported Browsers

**Full Support**:
- Google Chrome (latest)
- Microsoft Edge (latest)
- Safari (latest)

**Partial Support**:
- Firefox (see [FIREFOX_COMPATIBILITY.md](FIREFOX_COMPATIBILITY.md))

### Operating Systems

**Tested On**:
- Windows 10/11
- macOS (latest)
- Linux (Ubuntu, Fedora)

### Mobile Support

**Status**: Desktop-focused
- Mobile browsers have limited File System Access API support
- Use desktop browsers for full functionality

## Future Considerations

While Storytellr is feature-complete, potential enhancements could include:

- Additional export formats (RTF, HTML)
- Collaboration features
- Version history
- Grammar checking integration
- Word replacement suggestions
- Template system for different manuscript types
- Custom keyboard shortcuts
- Plugin/extension system

These are not planned but represent possible directions for future development.

## Additional Resources

- [User Guide](USER_GUIDE.md) - How to use Storytellr
- [Export Guide](EXPORT_GUIDE.md) - Detailed export documentation
- [File Handle Persistence](FILE_HANDLE_PERSISTENCE.md) - Technical details
- [Firefox Compatibility](FIREFOX_COMPATIBILITY.md) - Browser limitations
- [Speech Troubleshooting](SPEECH_TROUBLESHOOTING.md) - Read-aloud features

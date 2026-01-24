# Version History

Storytellr automatically maintains a version history of your story, allowing you to preview and restore previous saves. This feature protects against accidental data loss and gives you the confidence to experiment with your writing.

## Overview

Version history is embedded directly in your story file and maintains:
- **Last 5 manual saves** - Versions created when you explicitly save (Ctrl+S or File → Save)
- **Last 5 auto-saves** - Versions created on every auto-save
- **Total of up to 10 versions** - Manual and auto-saves are tracked separately

Each version snapshot includes:
- Complete story content (using diff compression for space efficiency)
- All bookmarks and notes
- Notebook entries
- Manuscript settings
- Word count and page count
- Timestamp and save type

## Accessing Version History

1. Open the **File** menu
2. Click **Version History** (only available when a document is open)
3. Browse the list of saved versions sorted by most recent first

## Understanding the Version List

Each version in the list shows:
- **Time ago** - "Just now", "5 minutes ago", "2 hours ago", etc.
- **Detailed timestamp** - Full date and time (e.g., "Jan 20, 2026, 3:45 PM")
- **Save type badge** - "Manual Save" or "Auto Save"
- **Word count and page count** - Document stats at that save point
- **Word count diff** - Shows how many words changed from the previous version
  - Green badge with + indicates words added
  - Red badge with - indicates words removed

The current version is marked with a blue "CURRENT" badge and highlighted.

## Previewing a Version

1. Click any version in the list (except the current one)
2. A preview panel opens showing the full content as it appeared at that save
3. Review the content, word count, and page count
4. Click **Cancel** to close the preview without making changes

## Restoring a Version

1. Preview the version you want to restore
2. Click **Restore This Version**
3. Confirm the restoration in the dialog

**Important notes:**
- Your current document state is automatically saved as a new version before restoring
- This ensures you can undo the restore if needed
- The restored content replaces your current document
- You'll need to save after restoring to persist the changes to disk

## Auto-Save Version Creation

Auto-save creates a version snapshot on **every auto-save** that occurs.

Auto-save triggers when:
- **Normal edits (20-99 characters)**: Save 5 seconds after you stop typing
- **Large edits (100+ characters)**: Immediate emergency save (no delay)
- **Small edits (< 20 characters)**: No save to prevent memory churn

This provides:
- Granular rollback through your last 5 auto-saves
- Recent recovery points without excessive file size
- Balance between data safety and storage efficiency

## Manual Save Behavior

Every manual save (Ctrl+S or File → Save) creates a version snapshot. Manual saves are prioritized over auto-saves, so you'll always have your last 5 manual saves available even if you've made many auto-saves in between.

## Version Limits

The system maintains separate limits to ensure you always have both types of saves available:
- If you have 5 manual saves and 5 auto-saves (10 total), the next manual save removes the oldest manual save
- If you have 3 manual saves and 7 auto-saves (10 total), the next auto-save removes the oldest auto-save
- Each type maintains its own "last 5" independently

## Data Loss Prevention

Version history works together with save validation to protect your work:

### Blank Document Warning
If you delete all content and try to save an empty document, you'll see a warning:
- Shows how many words will be lost
- Confirms the previous version is preserved in history
- Requires explicit confirmation to proceed

### Significant Content Loss Warning
If you reduce your document by more than 90% (e.g., from 5,000 words to 400 words):
- Shows the word count reduction and percentage
- Confirms the previous version is preserved
- Requires confirmation to save

Both warnings can be bypassed if you're intentionally making these changes.

## File Storage

Version history is stored in multiple locations for different purposes:

**In the story file (.html)**:
- All 10 versions embedded for portability
- Uses diff compression to minimize file size
- Travels with file across devices and cloud sync
- Most recent version stored in full, older versions as patches

**In browser localStorage**:
- Only 2 most recent versions cached (current + 1 backup)
- Used for crash recovery, not full version history
- Updates debounced (500ms) to minimize writes
- Reduces memory usage by ~80% vs caching all 10

**Version History UI**:
- Displays all 10 versions from file
- Quick access to restoration and preview
- Cleared when you close a document or create a new one

## Best Practices

1. **Trust auto-save** - Let Storytellr automatically create versions as you write
2. **Manual save milestones** - Use Ctrl+S when you complete important sections or before major edits
3. **Preview before restore** - Always preview a version to confirm it's what you expect
4. **Check version list** - Periodically review your version history to understand your writing progress
5. **Don't rely solely on versions** - While version history provides excellent recovery, maintain separate backups of important work

## Storage Efficiency

Version history uses **diff-based storage** for space optimization:

**How it works**:
- Most recent version: Full content (~175 KB for 31,000 words)
- Older versions: Stored as patches/diffs (typically 1-5 KB each)
- Reconstructs previous versions by applying reverse patches
- Automatically falls back to full content if patch would be inefficient

**File size for 31,000-word novel**:
- First version: ~175 KB
- 9 additional diff-based versions: ~30-50 KB total
- **Total: ~200-225 KB** (vs ~1.75 MB with full snapshots)
- **90% storage reduction** compared to storing full copies

**Benefits**:
- Smaller file sizes for cloud storage
- Faster file saves and loads
- More efficient memory usage
- Supports larger documents without hitting browser limits

## Related Features

- [Auto-Save](USER_GUIDE.md#auto-save) - Intelligent auto-save with character thresholds
- [Cloud Storage](CLOUD_STORAGE_SETUP.md) - Sync your story files and version history across devices
- [File Formats](EXPORT_GUIDE.md) - Export manuscripts for submission

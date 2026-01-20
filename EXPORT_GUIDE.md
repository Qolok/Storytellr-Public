# Export Guide

Complete documentation for exporting manuscripts from Storytellr.

## Table of Contents
- [Overview](#overview)
- [Export Formats](#export-formats)
- [Manuscript Formatting](#manuscript-formatting)
- [Headers & Page Numbers](#headers--page-numbers)
- [Title Pages](#title-pages)
- [Format-Specific Details](#format-specific-details)

## Overview

Storytellr exports manuscripts in three formats, each serving different purposes:

| Format | Purpose | Best For |
|--------|---------|----------|
| **TXT** | Plain text | Backup, word processors, universal compatibility |
| **DOCX** | Microsoft Word | Editing, track changes, Word navigation |
| **PDF** | Camera-ready | Print, submission, reading, archival |

All exports respect your manuscript settings for consistent professional formatting.

## Export Formats

### TXT (Plain Text)

**What It Includes**:
- All text content
- Basic paragraph structure
- Line breaks between sections

**What It Excludes**:
- Formatting (bold, italic, underline)
- Headers and page numbers
- Font styling
- Special spacing

**Use Cases**:
- Quick backup
- Importing to other word processors
- Plain text submissions
- Format-agnostic archival

**How to Export**:
1. File → Export → Save as TXT
2. Choose save location
3. File saves with `.txt` extension

### DOCX (Microsoft Word)

**What It Includes**:
- All text with formatting preserved
- Bold, italic, underline styling
- Heading styles (H1 = Heading 1, H2 = Heading 2)
- Block quotes with indentation
- Headers and page numbers (if enabled)
- Title page (if enabled)

**Special Features**:
- **Word Navigation Pane**: H1 and H2 appear in Word's navigation sidebar
- **Professional Formatting**: Industry-standard manuscript spacing
- **Editable**: Full editing capabilities in Microsoft Word
- **Track Changes**: Compatible with editorial workflows

**Manuscript Standards Applied**:
- Font from manuscript settings (Times New Roman, Arial, or Courier New)
- 12pt font size
- Double-spaced lines (24pt spacing)
- 1-inch margins (standard document margins)
- Chapter headings positioned per settings (1/3 or 1/2 page)
- Scene breaks (H2) centered with proper spacing
- Block quotes indented 0.5 inches
- No first-line indent after headings
- Black text color (overrides Word's default heading colors)

**How to Export**:
1. File → Export → Save as DOCX
2. Choose save location
3. Open in Microsoft Word to edit or review

**Opening in Word**:
- Use **Navigation Pane** (View → Navigation Pane) to see document structure
- H1 headings = Heading 1 style
- H2 headings = Heading 2 style
- Click headings in Navigation Pane to jump to sections

### PDF (Portable Document Format)

**What It Includes**:
- All text with formatting preserved
- Bold, italic, underline styling
- Professional manuscript spacing
- Headers and page numbers (if enabled)
- Title page (if enabled)
- Block quotes with indentation

**Manuscript Standards Applied**:
- Font from manuscript settings
- 12pt font size
- Precise line spacing for manuscript format
- 1-inch margins
- Chapter headings positioned per settings
- Scene breaks centered
- Block quotes indented 0.5 inches
- Professional page layout

**Special Features**:
- **Camera-Ready**: Exactly as it will appear when printed
- **Universal**: Opens on any device with PDF reader
- **Non-Editable**: Preserves formatting perfectly
- **Print-Ready**: Professional submission format

**Use Cases**:
- Agent/publisher submissions
- Print formatting preview
- Archival copies
- Sharing for reading (not editing)

**How to Export**:
1. File → Export → Save as PDF
2. Choose save location
3. Open in any PDF reader

## Manuscript Formatting

### Standard Manuscript Format

Storytellr follows **William Shunn's manuscript format** guidelines:

**Typography**:
- 12pt font size
- Courier New, Times New Roman, or Arial
- Black text on white background
- No extra styling or decorations

**Spacing**:
- Double-spaced body text
- 1-inch margins on all sides
- Single space after periods
- No extra space between paragraphs

**Paragraphs**:
- First line indented 0.5 inches
- No indent after chapter headings
- No indent for first paragraph of manuscript

**Chapters**:
- Begin 1/3 or 1/2 down the page (configurable)
- All caps or title case (your choice)
- Centered or left-aligned (via formatting)

**Scene Breaks**:
- Centered "#" or "***" (or use H2 for automatic formatting)
- Extra space above and below (H2 handles this)

### How Storytellr Elements Map to Format

| Editor Element | DOCX Export | PDF Export |
|----------------|-------------|------------|
| **H1** | Heading 1 style, positioned 1/3 or 1/2 page | Same positioning, proper spacing |
| **H2** | Heading 2 style, centered | Centered, proper spacing |
| **Paragraph** | Double-spaced, 0.5" first-line indent | Same |
| **Paragraph after H1/H2** | No first-line indent | Same |
| **Block Quote** | 0.5" left indent, single paragraph | Same |
| **Bold** | Bold formatting preserved | Same |
| **Italic** | Italic formatting preserved | Same |
| **Underline** | Underline formatting preserved | Same |

### Chapter Spacing

**1/3 Page Option**:
- Chapter heading begins 3847 twips from top (about 1/3 of page)
- Followed by blank paragraph with page break

**1/2 Page Option**:
- Chapter heading begins 6480 twips from top (exactly 1/2 of page)
- Followed by blank paragraph with page break

**Why This Matters**:
- Traditional manuscript format
- Creates dramatic chapter openings
- Professional appearance
- Helps agents/editors navigate manuscript

### Scene Break Formatting

**H2 Elements**:
- Centered automatically
- No extra spacing before or after
- Flows naturally with surrounding paragraphs
- Can contain symbols (#, ***, etc.) or text

**Best Practices**:
- Use simple symbols (#) for clean breaks
- Or use descriptive text ("Three Days Later")
- Avoid excessive styling
- Keep it simple and professional

### Block Quotes

**Formatting**:
- Indented 0.5 inches from left margin
- All content on single line in export
- Inline formatting (bold, italic) preserved
- No extra spacing

**Use Cases**:
- Letters within narrative
- Excerpts from fictional documents
- Poetry or song lyrics
- Emphasized passages

**How to Create**:
1. Select text
2. Click **Q** in floating toolbar
3. Text becomes block quote
4. Exports with proper indentation

## Headers & Page Numbers

### Configuring Headers

In Manuscript Settings:

1. **Enable Headers**: Toggle on/off
2. **Author Name**: Your last name (appears in header)
3. **Manuscript Title**: Short title (appears in header)
4. **Format**: Choose layout:
   - `LastName / TITLE / PageNumber`
   - `TITLE / LastName / PageNumber`
5. **First Page Different**: Skip header on first page (recommended)

### Header Formats

**Option 1: LastName / TITLE / Page**
```
Smith / THE NOVEL / 1
```

**Option 2: TITLE / LastName / Page**
```
THE NOVEL / Smith / 1
```

### Page Numbering

- **DOCX**: Uses Word's page numbering system
  - Shows as `{PAGE}` in header
  - Updates automatically in Word
  - Starts at page 1 (or 2 if first page different)

- **PDF**: Generated page numbers
  - Calculated during export
  - Shows actual page number
  - Sequential throughout document

### First Page Different

**When Enabled**:
- First page has no header
- Page numbering starts on page 2
- Title page doesn't count in numbering

**When Disabled**:
- All pages have headers
- Page 1 has header with "1"
- Title page is page 1 (if included)

**Best Practice**:
- Enable for submissions (standard format)
- Disable for drafts if you prefer continuous numbering

## Title Pages

### Configuring Title Page

In Manuscript Settings:
- Toggle **Include Title Page**
- Title page adds automatically to exports

### Title Page Format

**Content**:
- Manuscript title (centered, upper third)
- Author name (centered, below title)
- Word count (rounded to nearest 1000)
- All content centered and properly spaced

**Standard Layout**:
```
[1/3 down page]

MANUSCRIPT TITLE
by
Author Name

Approximately 85,000 words
```

**Page Numbering**:
- Title page is not numbered
- First manuscript page is page 1
- Headers begin on first manuscript page (or page 2 if "first page different")

### Use Cases

**Include Title Page For**:
- Agent submissions
- Publisher submissions
- Contest entries
- Professional presentations

**Omit Title Page For**:
- Drafts
- Personal copies
- Beta reader copies
- Revision tracking

## Format-Specific Details

### TXT Export Details

**Line Endings**:
- Windows: CRLF (`\r\n`)
- Mac/Linux: LF (`\n`)
- Handled automatically by browser

**Encoding**:
- UTF-8 encoding
- Supports international characters
- Preserves special characters (em-dashes, quotes)

**Structure**:
- Paragraphs separated by blank lines
- Headings appear as plain text
- No special formatting markers

### DOCX Export Details

**Technical Specifications**:
- Created using docx.js library (v9.5.1)
- Compliant with Office Open XML standards
- Compatible with Microsoft Word 2007+

**Paragraph Spacing**:
- Body text: 24pt spacing (double-spaced)
- After paragraphs: 0pt (no extra space)
- Line spacing: 1.0 (exact)

**Indentation**:
- First line: 720 twips (0.5 inches)
- Calculated in twips (1/1440th of an inch)
- Precise positioning

**Chapter Spacing**:
- 1/3 page: 3847 twips from top
- 1/2 page: 6480 twips from top
- Page break after each chapter heading

**Heading Styles**:
- H1: `HeadingLevel.HEADING_1`, black color
- H2: `HeadingLevel.HEADING_2`, black color
- Enables Word navigation pane integration

**Headers**:
- Created using `new Header()` object
- Includes `PageNumber.CURRENT` wrapped in `TextRun`
- Format with slashes as separators

### PDF Export Details

**Technical Specifications**:
- Created using jsPDF library
- A4 page size (210mm x 297mm)
- 72 points per inch

**Font Handling**:
- Times New Roman → built-in 'times' font
- Arial → built-in 'helvetica' font
- Courier New → built-in 'courier' font

**Margin Calculations**:
- All margins: 72 points (1 inch)
- Content area: 130mm width
- Automatic page breaks

**Line Spacing**:
- Calculated from font size
- Double-spaced for body text
- Single-spaced for headers

**Page Numbers**:
- Generated dynamically
- Positioned in header area
- Formatted according to settings

## Export Workflow

### Pre-Export Checklist

1. **Review Manuscript Settings**:
   - Font selection appropriate?
   - Chapter spacing set correctly?
   - Headers configured (if needed)?
   - Title page desired?

2. **Check Formatting**:
   - Chapter headings use H1?
   - Scene breaks use H2?
   - Block quotes properly formatted?
   - No excessive empty paragraphs?

3. **Verify Content**:
   - All chapters complete?
   - Spelling checked?
   - Final revision applied?

### Exporting for Submission

**Recommended Settings**:
- Font: Times New Roman (most traditional)
- Chapter Spacing: 1/3 page (standard)
- Include Title Page: Yes
- Headers: Enabled
- Format: `LastName / TITLE / PageNumber`
- First Page Different: Yes

**Recommended Format**:
- PDF for most agent submissions
- DOCX if specifically requested
- Check submission guidelines first

### Exporting for Review

**Recommended Settings**:
- Font: Your preference
- Chapter Spacing: 1/3 page
- Title Page: Optional
- Headers: Optional
- Format: DOCX (allows comments/track changes)

### Exporting for Backup

**Recommended Settings**:
- All formats (TXT, DOCX, PDF)
- Keep settings consistent
- Regular exports to secure location
- Date-stamped filenames

## Troubleshooting

### Common Issues

**Headers Not Appearing**:
- Ensure "Enable Headers" is checked in settings
- Verify author name and title are filled in
- Check "First Page Different" setting

**Chapter Spacing Incorrect**:
- Verify chapter spacing setting (1/3 vs 1/2)
- Ensure H1 is used for chapters
- Check for conflicting formatting

**First Paragraph Indented**:
- This is correct for standard manuscript format
- First paragraph after headings should not indent (automatic)

**Block Quotes Spanning Multiple Lines**:
- Storytellr correctly exports block quotes as single paragraphs
- Line breaks within quotes are preserved in editor but formatted correctly on export

### Format-Specific Issues

**DOCX Problems**:
- If navigation doesn't work, check headings are H1/H2
- If spacing is wrong, verify settings before export
- Ensure Microsoft Word 2007 or later

**PDF Problems**:
- If fonts look wrong, check browser's PDF renderer
- If margins are off, verify page size settings
- Try different PDF readers if appearance varies

**TXT Problems**:
- If encoding is wrong, ensure UTF-8 support
- If line breaks are wrong, check text editor settings

## Best Practices

### Manuscript Preparation

1. **Use Consistent Formatting**: 
   - H1 for all chapters
   - H2 for all scene breaks
   - Don't mix formatting styles

2. **Check Preview**:
   - Export PDF to preview layout
   - Verify chapter positioning
   - Check page breaks

3. **Test Early**:
   - Export test pages early
   - Verify formatting meets requirements
   - Adjust settings as needed

### Submission Preparation

1. **Follow Guidelines**:
   - Check agent/publisher requirements
   - Some want specific fonts or spacing
   - Some prefer DOCX, others PDF

2. **Clean Export**:
   - Remove author notes
   - Delete bracketed comments
   - Remove incomplete sections

3. **Professional Appearance**:
   - Consistent formatting throughout
   - No extra blank pages
   - Proper headers and page numbers

### Version Control

1. **Date-Stamped Exports**:
   - Add date to filename
   - Keep multiple versions
   - Track major revisions

2. **Format Archives**:
   - Keep all format versions
   - PDF for archival
   - DOCX for working copies
   - TXT for backup

## Advanced Tips

### Custom Formatting

**Scene Break Symbols**:
- Create H2 with just "#"
- Or use "***"
- Or use "• • •"
- Exports as-is with centering

**Chapter Titles**:
- "Chapter One" vs "CHAPTER ONE"
- Use formatting toolbar for caps
- Or type as desired

### Multiple Export Formats

**Batch Exporting**:
1. Export as TXT for backup
2. Export as DOCX for editing
3. Export as PDF for submission
4. Keep all versions organized

### Automation

- Save manuscript settings with template
- Use same settings across manuscripts
- Export regularly during writing process
- Maintain consistent professional format

## Additional Resources

- [User Guide](USER_GUIDE.md) - Complete Storytellr documentation
- [Features Reference](FEATURES.md) - All features explained
- [William Shunn's Manuscript Format](https://www.shunn.net/format/) - Industry standard guidelines

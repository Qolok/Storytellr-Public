# Export Guide

Complete documentation for exporting manuscripts from Storytellr.

## Table of Contents
- [Overview](#overview)
- [Document Structure Tags](#document-structure-tags)
- [Export Formats](#export-formats)
- [Manuscript Formatting](#manuscript-formatting)
- [Headers & Page Numbers](#headers--page-numbers)
- [Title Pages](#title-pages)
- [Export Workflow](#export-workflow)
- [Troubleshooting](#troubleshooting)

---

## Overview

Storytellr exports manuscripts in four formats, each serving different purposes:

| Format | Purpose | Best For |
|--------|---------|----------|
| **TXT** | Plain text | Backup, universal compatibility |
| **DOCX** | Microsoft Word | Editing, track changes, submissions |
| **PDF** | Camera-ready | Print, agent submissions, archival |
| **EPUB** | E-reader | Kindle, Kobo, Apple Books, Send to Kindle |

All exports respect your manuscript settings for consistent professional formatting.

---

## Document Structure Tags

Storytellr uses a small set of structural elements to define how your document is organised. These map directly to formatting in every export format — getting them right is the most important step before exporting.

| Editor Element | Button | Purpose | Maps To |
|----------------|--------|---------|---------|
| **H2** | Part | Top-level division (Part I, Act One, etc.) | Part heading in all formats |
| **H3** | Chapter | Chapter heading | Chapter heading in all formats |
| **Blockquote** | Q | Quoted passage, epigraph, letter within narrative | Indented block in all formats |
| **HR** | — | Scene break between paragraphs | Centred break symbol or rule |
| **H1** | *(automatic)* | Title page title | Generated from Story settings |

### How to Apply Tags

1. Click into the line you want to format (or select text)
2. The floating toolbar appears — click **Part**, **Chapter**, **Q**, or the divider button
3. Tags are visible as styled elements in the editor and carry through to all exports

### Tips

- **Parts are optional** — if your manuscript has no formal parts, use Chapter (H3) headings only
- **H1 is managed automatically** — it's inserted by the title page feature in Manuscript Settings, not typed manually
- **Scene breaks (HR)** style differently per export: a rule in DOCX/PDF, a styled ornament in EPUB
- **Blockquotes** are indented in all formats; inline bold/italic inside them is preserved

---

## Export Formats

### TXT (Plain Text)

**What It Includes**:
- All text content
- Basic paragraph structure

**What It Excludes**:
- Formatting (bold, italic, underline)
- Headers and page numbers
- Structural styling

**Use Cases**:
- Quick backup
- Importing to other tools
- Format-agnostic archival

### DOCX (Microsoft Word)

**What It Includes**:
- All text with formatting preserved (bold, italic, underline)
- Part headings (H2) and Chapter headings (H3) as Word heading styles
- Blockquotes with 0.5" indentation
- Headers and page numbers (if enabled in settings)
- Title page (if enabled in settings)

**Special Features**:
- **Word Navigation Pane**: H2 (Part) and H3 (Chapter) appear in Word's navigation sidebar
- **Editable**: Full editing in Microsoft Word
- **Track Changes**: Compatible with editorial workflows

**Manuscript Standards Applied**:
- Font from Manuscript Settings (Times New Roman or Arial)
- 12pt font size, double-spaced lines
- 1-inch margins
- Chapter headings positioned 1/3 or 1/2 down the page (configurable)
- No first-line indent after headings
- Black text colour (overrides Word's default heading colours)

**Opening in Word**:
- Use **Navigation Pane** (View → Navigation Pane) to see document structure
- H2 = Heading 2 style, H3 = Heading 3 style
- Click headings in Navigation Pane to jump to sections

### PDF (Portable Document Format)

**What It Includes**:
- All text with formatting preserved
- Professional manuscript spacing
- Headers and page numbers (if enabled)
- Title page (if enabled)
- Blockquotes with indentation

**Manuscript Standards Applied**:
- Font from Manuscript Settings
- 12pt font size, double-spaced body text
- 1-inch margins, precise line spacing
- Chapter headings positioned per settings

**Use Cases**:
- Agent/publisher submissions
- Print formatting preview
- Archival copies
- Sharing for reading (not editing)

### EPUB (E-Reader Format)

**What It Includes**:
- Full manuscript text with inline formatting
- Part (H2) and Chapter (H3) headings as EPUB chapters
- Blockquotes with italic indentation
- Scene breaks styled as ornaments (· · ·, * * *, or rule)
- Optional cover image, title page, and table of contents
- Book metadata: title, author, language, description

**EPUB-Specific Options** (configured in the EPUB export modal):

| Option | Description |
|--------|-------------|
| **Cover Image** | JPG or PNG, ideal 2:3 ratio. Also set in Story settings. |
| **Language** | Used for EPUB metadata and reader language detection. |
| **Description** | Back-cover synopsis, stored in EPUB metadata. |
| **Chapter Style** | Centered (novel), Bold (non-fiction), or Minimal |
| **Scene Breaks** | · · · (dots), * * * (asterism), or horizontal rule |
| **Table of Contents** | Toggle EPUB TOC page on or off |

**Send to Kindle**:
- Check **Send to Kindle** in the export modal
- Enter your Kindle email address (see [Finding Your Kindle Email](#finding-your-kindle-email) below)
- On first use, add **kindle@storytellr.app** to your Amazon Approved Email List (see [Approving Storytellr as a Sender](#approving-storytellr-as-a-sender))
- Click **Send to Kindle** — the EPUB is generated and emailed directly to your device

**How Structure Maps to EPUB Chapters**:

| Editor Element | EPUB Result |
|----------------|-------------|
| H2 (Part) | New EPUB chapter entry (part divider) |
| H3 (Chapter) | New EPUB chapter entry |
| Content before first heading | Front matter |
| HR scene break | Centred ornament (· · · or * * *) or rule |
| Blockquote | Indented italic passage |

> **Note**: EPUB readers (Kindle, Kobo, Apple Books) apply their own typography. Font choices in Manuscript Settings do not affect EPUB — the reader's font and size preferences take precedence.

**Compatible Readers**:
- Amazon Kindle (via Send to Kindle or sideloading)
- Kobo
- Apple Books
- Google Play Books
- Calibre (desktop)
- Any EPUB-compatible reader

---

## Manuscript Formatting

### How Storytellr Tags Map to Each Format

| Editor Element | DOCX | PDF | EPUB |
|----------------|------|-----|------|
| **H2** (Part) | Heading 2 style, centred | Centred, proper spacing | New chapter entry |
| **H3** (Chapter) | Heading 3 style, positioned 1/3 or 1/2 page | Same positioning | New chapter entry |
| **HR** (Scene break) | Centred "#" text | Centred "#" text | Ornament or rule |
| **Blockquote** | 0.5" left indent | 0.5" left indent | Indented italic |
| **Paragraph** | Double-spaced, 0.5" first-line indent | Same | Reader-controlled |
| **Paragraph after H2/H3** | No first-line indent | No first-line indent | No indent |
| **Bold / Italic / Underline** | Preserved | Preserved | Preserved |

### Standard Manuscript Format

Storytellr follows **William Shunn's manuscript format** for DOCX and PDF exports:

- 12pt font, double-spaced, 1-inch margins
- First paragraph of each chapter: no indent
- All other paragraphs: 0.5" first-line indent
- Chapter headings 1/3 or 1/2 down the page (configurable in settings)
- No extra space between paragraphs

> EPUB is exempt from manuscript format rules — e-reader typography is controlled by the reading device.

---

## Headers & Page Numbers

Applies to **DOCX and PDF** exports only.

### Configuring Headers

In Manuscript Settings:

1. **Enable Headers**: Toggle on/off
2. **Author Name**: Your last name (appears in header)
3. **Manuscript Title**: Short title (appears in header)
4. **First Page Different**: Skip header on first page (recommended for submissions)

### Header Format

```
LastName / TITLE / 1
```

### Page Numbering

- **DOCX**: Word's built-in page numbering, updates automatically
- **PDF**: Generated during export, sequential throughout

---

## Title Pages

Toggle **Show title page** in Manuscript Settings. The title page is generated automatically from your Story settings (title, author name).

**Standard layout**:
```
[1/3 down page]

MANUSCRIPT TITLE
by
Author Name

Approximately 85,000 words
```

**Include for**: Agent submissions, publisher submissions, contest entries  
**Omit for**: Drafts, beta reader copies, revision tracking

---

## Export Workflow

### Pre-Export Checklist

1. **Check your tags**:
   - Part headings use **H2** (Part button)?
   - Chapter headings use **H3** (Chapter button)?
   - Scene breaks use **HR** (divider button)?
   - Quoted passages use **Blockquote** (Q button)?

2. **Review Manuscript Settings**:
   - Font, chapter spacing, headers configured?
   - Title page desired?

3. **For EPUB**:
   - Title, author, language, and description set in Story settings?
   - Cover image uploaded?

### Exporting for Submission

**Recommended settings**:
- Font: Times New Roman
- Chapter Spacing: 1/3 page
- Include Title Page: Yes
- Headers: Enabled, First Page Different: Yes
- Format: DOCX (if requested) or PDF

### Exporting for E-Readers

- Export as **EPUB**
- Use **Send to Kindle** to deliver directly to your Kindle
- Or export and sideload via Calibre, Apple Books, etc.

---

## Send to Kindle

### Finding Your Kindle Email

Each Kindle device and app has its own unique email address (e.g. `yourname@kindle.com`).

**Via Amazon website:**

1. Log into your Amazon account
2. Go to **Accounts & Lists → Manage Your Content and Devices**
3. Click the **Devices** tab
4. Select the Kindle device you want to send to
5. Your Kindle email is shown under the device info

**Via your Kindle device:**

1. From the home screen, tap the menu icon or settings gear
2. Go to **Device Options** or **My Account**
3. Look for **Send-to-Kindle Email** or **Personalize Your Kindle**

> Each device has its own address — pick the one for the Kindle you read on most.

### Approving Storytellr as a Sender

Amazon only delivers documents from approved senders. You only need to do this once.

1. Go to **Manage Your Content and Devices → Settings**
2. Scroll to **Personal Document Settings**
3. Under **Approved Personal Document E-mail List**, click **Add a new approved e-mail address**
4. Enter **kindle@storytellr.app** and save

After approving, documents sent from Storytellr will deliver to your Kindle automatically.

---

## Troubleshooting

### Headers Not Appearing
- Ensure "Include headers in exports" is checked in Manuscript Settings
- Verify author name and title are filled in

### Chapter Spacing Incorrect
- Verify chapter spacing setting (1/3 vs 1/2) in Manuscript Settings
- Ensure chapters use **H3**, not H2 or plain text

### EPUB Chapters Not Splitting Correctly
- Each chapter must start with an **H3** heading (Chapter button)
- Parts must use **H2** (Part button)
- Content before the first heading is treated as front matter

### Send to Kindle Not Delivering
- Confirm your Kindle email is correct — each device has its own address
- Ensure **kindle@storytellr.app** is on your Amazon Approved Email List
- Check your Kindle device is registered and connected to Wi-Fi

### DOCX Navigation Pane Empty
- Confirm headings are H2 (Part) or H3 (Chapter), not plain text
- Open Navigation Pane in Word: View → Navigation Pane

---

## Additional Resources

- [User Guide](USER_GUIDE.md) — Complete Storytellr documentation
- [Features Reference](FEATURES.md) — All features explained
- [William Shunn's Manuscript Format](https://www.shunn.net/format/) — Industry standard guidelines

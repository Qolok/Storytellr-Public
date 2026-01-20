# Firefox Compatibility Updates

## Issues Addressed

### 1. Auto-Save Disabled in Firefox
**Problem**: Firefox doesn't properly support persistent file handles across page refreshes, even though it has the File System Access API.

**Solution**:
- Updated `isFileSystemSupported()` in [src/utils/fileSystem.js](src/utils/fileSystem.js) to detect Firefox and return `false`
- This forces Firefox to use the fallback download mechanism
- Updated [src/components/Sidebar.jsx](src/components/Sidebar.jsx) to hide auto-save UI in Firefox:
  - Auto-save toggle removed from File menu
  - Auto-save status icon (checkmark) hidden
- Users in Firefox will need to manually save files (Ctrl+S or File > Save)

### 2. CSS Rendering Issues in Firefox
**Problem**: Firefox had issues with:
- Wrong border colors
- Wrong background colors
- Light mode not working properly
- CSS variables not being inherited correctly

**Solution**:
Added Firefox-specific CSS fixes to [src/index.css](src/index.css):

```css
@-moz-document url-prefix() {
  /* Ensure light mode works properly */
  :root {
    color-scheme: light;
  }

  [data-theme="dark"] {
    color-scheme: dark;
  }

  /* Fix border and background rendering */
  * {
    background-clip: padding-box;
  }

  /* Ensure CSS variables work */
  body {
    background-color: var(--bg-primary);
    color: var(--text-primary);
  }

  /* Fix form element backgrounds */
  input, textarea, select {
    background-color: var(--bg-secondary);
    color: var(--text-primary);
    border-color: var(--border-color);
  }

  /* Fix button backgrounds */
  button {
    background-color: var(--bg-secondary);
    color: var(--text-primary);
    border-color: var(--border-color);
  }
}
```

## Browser Support Matrix

| Feature | Chrome/Edge | Safari 15.2+ | Firefox |
|---------|-------------|--------------|---------|
| Auto-save to file | ✅ Yes | ✅ Yes | ❌ No (fallback to download) |
| File handle persistence | ✅ Yes | ✅ Yes | ❌ No |
| Manual save/open | ✅ Yes | ✅ Yes | ✅ Yes (downloads) |
| Light/Dark mode | ✅ Yes | ✅ Yes | ✅ Yes (fixed) |
| All other features | ✅ Yes | ✅ Yes | ✅ Yes |

## User Experience in Firefox

### What Works
- ✅ All editing features
- ✅ Notes and bookmarks
- ✅ Notebook panel
- ✅ Navigation panel
- ✅ Find/Replace
- ✅ Dictionary
- ✅ Export to Markdown/PDF/DOCX
- ✅ Light and dark modes
- ✅ Theme customization
- ✅ localStorage persistence (content saved between sessions)

### What's Different
- ⚠️ **No auto-save** - Users must manually save (Ctrl+S)
- ⚠️ **Save = Download** - Files are downloaded to the Downloads folder
- ⚠️ **Open = Upload** - Users select files from their file system
- ⚠️ **No file handle persistence** - File location isn't remembered

### User Workflow in Firefox
1. **Create/Edit**: Work normally in the editor
2. **Save**: Press Ctrl+S or File > Save
3. **File Downloaded**: File goes to Downloads folder
4. **Continue Working**: Keep editing
5. **Save Again**: File downloads again (may need to replace)
6. **Re-open**: Use File > Open to select the file from Downloads

## Future Improvements

Potential enhancements for Firefox users:

1. **Show browser notification** when auto-save is disabled
2. **Periodic save reminders** for Firefox users
3. **Auto-download on close** if there are unsaved changes
4. **Local storage backup** as additional safety net

## Technical Notes

### Why Not Just Fix Firefox Support?

Firefox's File System Access API implementation has a critical limitation:
- File handles cannot be stored in IndexedDB properly
- Permission prompts appear inconsistently
- Handles become invalid unpredictably
- No reliable way to maintain write access across sessions

Rather than provide a broken experience, we opted for a reliable fallback that works consistently.

### Detection Method

We detect Firefox using:
```javascript
const isFirefox = navigator.userAgent.toLowerCase().indexOf('firefox') > -1;
```

This is reliable and works across all Firefox versions.

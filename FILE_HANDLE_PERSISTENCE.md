# File Handle Persistence Solution

## Problem

When using the File System Access API in a web application, file handles are lost on page refresh. This breaks auto-save functionality because the application loses its ability to write to the previously opened file without prompting the user again.

## Solution

We've implemented IndexedDB-based file handle persistence that:

1. **Stores file handles** in IndexedDB whenever a file is opened or saved
2. **Restores file handles** on application mount (page load/refresh)
3. **Verifies permissions** before using restored handles
4. **Cleans up** handles when files are closed or new files are created

## Implementation Details

### New File: `src/utils/fileHandleStorage.js`

This utility module provides functions to:

- `saveFileHandle(key, fileHandle)` - Save a file handle to IndexedDB
- `getFileHandle(key)` - Retrieve a file handle from IndexedDB
- `removeFileHandle(key)` - Remove a file handle from IndexedDB
- `verifyFileHandlePermission(fileHandle)` - Check if we still have permission to access the file
- `restoreFileHandle(key)` - Restore and verify a file handle in one step

### Storage Keys

- `'main-story'` - The main story file handle
- `'notebook'` - The notebook file handle

### App.jsx Changes

#### 1. Restore on Mount

```javascript
useEffect(() => {
  const restoreHandles = async () => {
    const mainHandle = await restoreFileHandle('main-story');
    if (mainHandle) {
      fileHandleRef.current = mainHandle;
    }

    const notebookHandle = await restoreFileHandle('notebook');
    if (notebookHandle) {
      notebookFileHandleRef.current = notebookHandle;
    }
  };

  restoreHandles();
}, []);
```

#### 2. Save on File Operations

File handles are now saved to IndexedDB in:
- `handleOpen()` - When opening an existing file
- `handleSave()` - When saving a file
- `handleRenameFile()` - When renaming and saving a file
- `handleOpenNotebook()` - When opening a notebook
- `handleExportNotebook()` - When exporting a notebook

#### 3. Clean Up on New/Close

File handles are removed from IndexedDB in:
- `handleNew()` - When creating a new document
- `handleNewNotebook()` - When creating a new notebook

## How It Works

1. **User Opens a File**: The file handle is stored in IndexedDB with key `'main-story'`

2. **User Makes Changes**: Auto-save works normally using the in-memory file handle

3. **User Refreshes Page**:
   - Application loads
   - Restoration effect runs
   - File handle is retrieved from IndexedDB
   - Permission is verified (may prompt user if needed)
   - If valid, file handle is restored to `fileHandleRef.current`
   - Auto-save continues working seamlessly

4. **Permission Handling**: If permission is lost or denied, the handle is removed from IndexedDB and the user will need to re-open the file

## Browser Compatibility

This solution works in browsers that support:
- File System Access API (Chrome, Edge, Safari 15.2+)
- IndexedDB (all modern browsers)

For browsers without File System Access API support, the fallback download mechanism continues to work.

## Security Considerations

- File handles stored in IndexedDB are origin-specific (only accessible by this app)
- Permissions are re-verified on each restore
- Users may need to grant permission again after browser restart (browser-dependent)
- Handles are automatically cleaned up when no longer needed

## Testing

To verify the solution works:

1. Open a file in the application
2. Make some changes (ensure auto-save is enabled)
3. Wait for auto-save to complete
4. Refresh the page (F5)
5. Make another change
6. Verify that auto-save still works without requiring you to re-open the file

## Fallback Behavior

If file handle restoration fails (e.g., permission denied, file deleted):
- The application continues to function normally
- Content is preserved in localStorage
- User can re-open the file when needed
- A warning could be displayed (future enhancement)

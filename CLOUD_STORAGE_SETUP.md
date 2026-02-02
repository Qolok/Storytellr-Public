# Cloud Storage User Guide

This guide explains how cloud storage works in Storytellr and what to expect when working with cloud-synced files.

## Overview

Storytellr supports the following cloud storage providers:
- **Microsoft OneDrive**
- **Google Drive**
- **Dropbox**
- **Box**

Your files are stored directly in your cloud account. Storytellr connects to your cloud storage to read and save your work, but never stores your data on any external servers.

## How Cloud Connection Works

When you connect to a cloud service, Storytellr uses two types of credentials:

### Access Tokens (Short-Lived)
Think of an access token like a temporary key card:
- **Lasts 1 hour** while you're actively using the app
- Used to read and save your files
- Expires automatically after inactivity for security

### Refresh Tokens (Long-Lived)
Think of a refresh token like a master key:
- **Lasts up to 90 days** (depending on the provider)
- Used to get a new access token when the old one expires
- Allows seamless reconnection without re-entering credentials

## Connection Behavior

### When You're Actively Working

**With a document open:**
- Connection stays active automatically
- Even if your computer sleeps, the app reconnects when you wake it
- Your work is saved continuously (if auto-save is enabled)
- Changes from other devices are detected and synced

**On the Welcome Screen (no document open):**
- Connection remains active for **1 hour**
- After 55 minutes of inactivity, you'll see a timeout warning
- You can choose to stay connected or disconnect

### Timeout Warning Modal

After 55 minutes of idle time on the Welcome Screen, you'll see:

**"Cloud Connection Timeout"**
- 5-minute countdown timer
- Two options:
  - **Stay Connected** - Resets the timer, keeps you logged in
  - **Disconnect** - Logs you out for security

**Why this happens:**
- Security on shared computers (library, office, etc.)
- Prevents unauthorized access if you walk away

**What "Disconnect" does:**
- Signs you out of cloud storage
- You can easily reconnect later without re-entering credentials (within 90 days)
- Your files remain safely in your cloud account

### Automatic Reconnection

**Within 90 days:**
- Click "Connect" on the Welcome Screen
- Storytellr automatically reconnects without asking for credentials
- Your refresh token handles this seamlessly

**After 90 days:**
- You'll need to sign in again through your cloud provider
- This is a security measure enforced by cloud providers
- Your files are still safe in your cloud account

## Working Across Devices

Storytellr is designed for multi-device workflows. Here's what happens:

### Scenario: Edit on Mobile, Continue on Desktop

1. **You're working on your laptop:**
   - Document is open
   - Computer goes to sleep

2. **You edit the file on mobile:**
   - Changes are saved to cloud storage
   - File is now newer than your laptop's version

3. **You wake up your laptop:**
   - App reconnects automatically
   - Detects the file changed remotely
   - **No local changes?** Automatically updates your document
   - **Have local changes?** Shows conflict resolution modal

### Conflict Resolution

If you've edited on multiple devices simultaneously:

**What you'll see:**
- Modal showing both versions side-by-side
- Word count and last modified time for each
- Three options:
  1. **Keep My Changes** - Your local edits win
  2. **Use Other Device's Changes** - Cloud version wins
  3. **Save Both Versions** - Creates a conflict copy for manual merge

**The app prevents:**
- Silently losing your work
- Accidentally overwriting important changes
- Confusion about which version is which

## Data Protection Features

### Automatic Change Detection
- Checks for remote changes when you return to the browser tab
- Validates file versions before every save
- Uses cloud provider's version tracking (eTags)

### Recovery Safeguards
- Prevents saving blank files (protects against browser crashes)
- Validates content before overwriting cloud files
- Automatically recovers from corrupted local storage

### Multi-Device Safety
- **No local changes** → Automatically applies remote changes
- **Local changes exist** → Prompts you to choose which version to keep
- **Conflicting saves** → Rolled back and you're notified

## Privacy & Security

### Your Data is Yours
- All files stored directly in **your** cloud account
- No data passes through external servers
- Storytellr only accesses files it creates
- You can delete cloud connection anytime

### Security Features
- **Automatic timeout** on shared computers (1 hour idle)
- **Encrypted connections** to cloud providers
- **Token expiration** prevents indefinite access
- **No credential storage** - tokens are temporary

### What We Can't See
- Your cloud files or their contents
- Your cloud credentials
- Which devices you use
- When you connect or disconnect

As stated in the app: **"We don't collect any of your information (and don't care to)."**

All cloud interactions happen directly between your browser and your chosen cloud provider.

## Connection States Explained

### Connected (Green)
- Access token is valid
- Can read and save files immediately
- Active connection to your cloud storage

### Disconnected (Gray)
- No active connection
- Click to connect/reconnect
- Your files are safe in cloud storage

### Reconnecting (Automatic)
When you click a cloud file after being disconnected:
- If within 90 days → Seamlessly reconnects using refresh token
- If after 90 days → Prompts for sign-in
- Your file opens once reconnected

## Best Practices

### For Personal Devices
- Let the connection stay active
- Use "Stay Connected" when you see the timeout warning
- Enjoy automatic reconnection across sessions

### For Shared/Public Computers
- Use "Disconnect" when finished
- Don't leave documents open unattended
- Consider manually disconnecting for extra security

### For Multi-Device Workflows
- Close documents on one device before editing on another (when possible)
- If you forget, no worries - conflict resolution has you covered
- Auto-save keeps your work safe across device switches

## Troubleshooting

### "Connection Expired" Message
**Cause:** Access token expired after 1 hour of inactivity
**Solution:** Click "Connect" to automatically reconnect (works within 90 days)

### "Please Sign In" After Long Break
**Cause:** Refresh token expired (after 90 days of no use)
**Solution:** Sign in again through your cloud provider - quick and secure

### File Shows Old Version
**Cause:** Remote file was modified, but local cache is stale
**Solution:**
- Refocus the browser tab (automatic check)
- Or close and reopen the document
- Recent changes will be detected automatically

### Conflict Modal Keeps Appearing
**Cause:** Editing same file on multiple devices simultaneously
**Solution:**
- Choose one device for editing at a time
- Or use "Save Both" and manually merge later
- Consider closing documents when switching devices

## Tips for Best Experience

1. **Trust the auto-save** - It's designed for safety, not speed
2. **Don't fight the conflict resolver** - It's protecting your work
3. **Close documents** when done, especially on shared computers
4. **Let the app reconnect** - It handles expired tokens automatically
5. **Watch the timeout warning** - 5 minutes is plenty of time to decide

---

*For developer documentation about OAuth setup and configuration, see the developer guides in the repository.*

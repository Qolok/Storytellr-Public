# Privacy Policy for Storytellr

**Last Updated: January 20, 2026**

## Introduction

Storytellr ("we", "our", or "the app") is committed to protecting your privacy. This Privacy Policy explains how we handle your information when you use Storytellr, a browser-based manuscript writing application.

## Our Privacy Philosophy

Storytellr is designed with privacy at its core. We do not collect, store, or transmit your personal data or manuscript content to our servers. Your work stays on your device and, optionally, in your personal cloud storage accounts.

## Information We Do Not Collect

We do NOT collect, store, or have access to:
- Your manuscript content
- Your notes, notebooks, or annotations
- Your personal information (name, email, address, etc.)
- Your writing habits or usage patterns
- Your IP address or device information
- Analytics or tracking data
- Cookies or similar tracking technologies

## Data Storage

### Local Storage
All your data is stored locally in your web browser using:
- **localStorage**: For UI preferences, recent files list, and settings
- **IndexedDB**: For persistent file handles and version history
- **File System Access API**: Direct access to files you explicitly choose to open or save

This data never leaves your device unless you choose to sync via cloud storage (see below).

### Cloud Storage (Optional)

If you choose to connect to cloud storage providers (OneDrive, Google Drive, Dropbox, or Box), the following applies:

**What We Access:**
- We only access files you explicitly create or open through Storytellr
- We request the minimum permissions necessary:
  - **OneDrive**: `Files.ReadWrite` and `offline_access`
  - **Google Drive**: `drive.file` (per-file access) and `drive.metadata.readonly`
  - **Dropbox**: `files.content.write` and `offline_access`
  - **Box**: Standard file access

**How It Works:**
- OAuth authentication is performed directly between your browser and the cloud provider
- Access tokens are stored only in your browser's localStorage
- We never see or store your cloud provider credentials
- All file operations happen directly between your browser and the cloud provider
- We do not have servers that process or store your cloud files

**What We Can and Cannot Do:**
- ✅ We CAN: Read and write files you choose to open or save
- ❌ We CANNOT: Access other files in your cloud storage
- ❌ We CANNOT: Share your files with others
- ❌ We CANNOT: View your files on our servers (we have no servers)

## Third-Party Services

Storytellr integrates with the following third-party services:

### Cloud Storage Providers
- **Microsoft OneDrive** - [OneDrive Privacy Statement](https://privacy.microsoft.com/en-us/privacystatement)
- **Google Drive** - [Google Privacy Policy](https://policies.google.com/privacy)
- **Dropbox** - [Dropbox Privacy Policy](https://www.dropbox.com/privacy)
- **Box** - [Box Privacy Policy](https://www.box.com/legal/privacy-policy)

When you connect to these services, their respective privacy policies apply.

### Dictionary and Thesaurus Services
- **Dictionary API** (dictionaryapi.dev) - No authentication required, lookups are anonymous
- **Datamuse API** (datamuse.com) - No authentication required, lookups are anonymous

These services may log requests but cannot identify you personally.

### GitHub Feedback (Optional)
If you use the feedback form, you can optionally submit issues to our GitHub repository. This requires:
- A GitHub account (governed by [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-privacy-statement))
- Your GitHub username will be visible on public issues
- Feedback content you submit is publicly visible

## Browser Permissions

Storytellr may request the following browser permissions:

### File System Access
- **Why**: To save and open files directly on your device
- **When**: Only when you click "Open" or "Save" buttons
- **Scope**: Only files you explicitly select
- **Platform**: Chrome, Edge, Safari (full support); Firefox (limited)

### Microphone Access (Optional)
- **Why**: For speech-to-text dictation feature
- **When**: Only when you activate the dictation feature
- **Processing**: All speech recognition happens in your browser via Web Speech API
- **Storage**: We do not record or store audio

### Speech Synthesis
- **Why**: For read-aloud feature
- **Processing**: Uses your browser's built-in text-to-speech engine
- **Data**: No audio or text is sent to external servers

## Data Security

Since Storytellr operates entirely in your browser:
- Your data is protected by your device's security measures
- Browser data is isolated from other websites and applications
- OAuth tokens are stored using browser security best practices
- We use PKCE (Proof Key for Code Exchange) flow for enhanced OAuth security
- All cloud API calls use HTTPS encryption

## Your Control Over Data

You have complete control over your data:
- **Delete Local Data**: Clear your browser's data for storytellr.app
- **Revoke Cloud Access**: Disconnect cloud storage from within the app or revoke permissions in your cloud provider's settings
- **Export Your Work**: Export manuscripts to TXT, DOCX, or PDF at any time
- **No Account**: Storytellr does not require account creation or login

## Children's Privacy

Storytellr does not knowingly collect information from children under 13. Since we do not collect personal information at all, the service can be used by anyone, but we recommend parental guidance for users under 13.

## Changes to This Privacy Policy

We may update this Privacy Policy from time to time. We will notify users of material changes by:
- Updating the "Last Updated" date at the top of this policy
- Displaying a notice in the application (for significant changes)

Continued use of Storytellr after changes constitutes acceptance of the updated policy.

## International Users

Storytellr is a client-side application that runs in your browser. Since we do not collect or transfer data to servers:
- No international data transfers occur through our services
- Your data remains in your browser and your chosen cloud storage locations
- Cloud storage providers may transfer data internationally according to their policies

## California Privacy Rights (CCPA)

Under the California Consumer Privacy Act (CCPA), California residents have certain rights. However, since Storytellr does not collect personal information, these rights are not applicable:
- We do not sell personal information
- We do not share personal information with third parties
- We do not collect personal information to disclose

## European Privacy Rights (GDPR)

Under the General Data Protection Regulation (GDPR), EU residents have certain rights. Since Storytellr does not collect or process personal information:
- No data controller or processor relationship exists
- We do not transfer personal data
- We do not create user profiles
- We do not use cookies for tracking

However, when you use cloud storage providers, their GDPR compliance policies apply.

## Contact Information

If you have questions about this Privacy Policy or data practices:

- **Email**: [Your contact email - to be added]
- **GitHub Issues**: https://github.com/Qolok/Storytellr-Public/issues (for technical questions)

Note: Since we do not collect data, we cannot fulfill data access or deletion requests - you control all data locally.

## Open Source Transparency

Storytellr's source code is available for review, demonstrating our privacy-first approach. You can verify that:
- No analytics or tracking code is present
- No data is sent to external servers (except direct cloud provider APIs)
- All processing happens locally in your browser

## Summary

In plain English:
- **We don't collect your data** - Your manuscripts, notes, and personal information stay on your device
- **We don't have servers** - We can't access your work even if we wanted to
- **You control cloud access** - Optional cloud features connect directly between your browser and your cloud accounts
- **No tracking** - We don't use analytics, cookies, or any tracking technologies
- **Local-first** - Everything happens in your browser using modern web APIs

Your privacy is protected by design, not just by policy.

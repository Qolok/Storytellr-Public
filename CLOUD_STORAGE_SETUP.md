# Cloud Storage Setup Guide

This document explains how to configure cloud storage providers for Storytellr.

## Overview

Storytellr supports the following cloud storage providers:
- Microsoft OneDrive
- Google Drive
- Dropbox
- Box

## OAuth Configuration

To enable cloud storage, you need to register your application with each provider and obtain OAuth credentials.

### Required Configuration

Update the `getOAuthUrl` function in `src/utils/cloudStorage.js` with your actual client IDs:

#### OneDrive (Microsoft)
1. Register at: https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade
2. Set redirect URI to your app URL (e.g., `http://localhost:5174/` for development)
3. Required scopes: `Files.ReadWrite offline_access`
4. Replace `YOUR_CLIENT_ID` in the OneDrive OAuth URL

#### Google Drive
1. Register at: https://console.cloud.google.com/apis/credentials
2. Enable Google Drive API
3. Create OAuth 2.0 Client ID
4. Set authorized redirect URI to your app URL
5. Required scopes: `https://www.googleapis.com/auth/drive.file`
6. Replace `YOUR_CLIENT_ID` in the Google Drive OAuth URL

#### Dropbox
1. Register at: https://www.dropbox.com/developers/apps
2. Create a new app with "Full Dropbox" or "App folder" access
3. Set redirect URI to your app URL
4. Replace `YOUR_CLIENT_ID` in the Dropbox OAuth URL

#### Box
1. Register at: https://app.box.com/developers/console
2. Create a new app
3. Enable OAuth 2.0 authentication
4. Set redirect URI to your app URL
5. Replace `YOUR_CLIENT_ID` in the Box OAuth URL

## OAuth Callback Handler

The OAuth callback is handled by the `CloudStorageModal` component. When the OAuth provider redirects back to your application, you need to:

1. Extract the access token from the URL hash or query parameters
2. Send it to the parent window using `window.opener.postMessage()`

Example callback HTML page (optional, for production deployments):

```html
<!DOCTYPE html>
<html>
<head>
    <title>OAuth Callback</title>
</head>
<body>
    <script>
        // Extract token from URL
        const hash = window.location.hash.substring(1);
        const params = new URLSearchParams(hash);
        
        const accessToken = params.get('access_token');
        const expiresIn = params.get('expires_in');
        
        if (accessToken && window.opener) {
            // Send token to parent window
            window.opener.postMessage({
                type: 'cloud-oauth-success',
                accessToken: accessToken,
                expiresIn: parseInt(expiresIn) || 3600
            }, window.location.origin);
            
            // Close popup
            window.close();
        }
    </script>
    <p>Authenticating...</p>
</body>
</html>
```

## Development Testing

For development testing without actual OAuth:

1. Open browser console on the Welcome Screen
2. Run the following to simulate a connection:
```javascript
localStorage.setItem('storytellr-cloud-storage', JSON.stringify({
    provider: 'onedrive',
    accessToken: 'mock-token',
    refreshToken: 'mock-refresh',
    expiresAt: Date.now() + 3600000
}));
```
3. Refresh the page to see the "Cloud Connected" state

## Security Notes

- Never commit OAuth client secrets to the repository
- Use environment variables for sensitive configuration
- Consider implementing a backend proxy for token refresh
- Implement proper token expiration handling
- Validate redirect URIs to prevent OAuth hijacking

## File Operations

Once connected, the app will:
- List `.html` story files from the root directory of the cloud storage
- Download files when clicked
- Auto-save changes to cloud storage every 3 seconds (if auto-save is enabled)
- Display cloud files in the "Cloud Files" section on the welcome screen

## Privacy

As stated in the app: "We don't collect any of your information (and don't care to)."

All cloud storage interactions happen directly between the user's browser and their cloud provider. No data passes through any intermediary servers.

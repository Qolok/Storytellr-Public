# Speech Troubleshooting Guide

This guide covers both **Read Aloud** (text-to-speech) and **Dictation** (speech-to-text) features.

---

## Read Aloud (Text-to-Speech)

### Overview
The Read Aloud feature uses the browser's built-in **Web Speech Synthesis API**. The available voices, quality, and behavior are entirely controlled by your browser and operating system — Storytellr has no ability to install voices or override browser limitations.

### Known Browser/Platform Limitations

These are confirmed bugs or limitations in the browsers themselves. They cannot be fixed in Storytellr.

| Platform | Issue |
|---|---|
| **Edge on Android** | `getVoices()` always returns empty — voice selection dropdown will be blank. This is a [confirmed Microsoft bug](https://learn.microsoft.com/en-us/answers/questions/1657183/text-to-speech-speech-synthesis-broken-on-mobile-e) with no fix as of 2025. Read aloud may still work using the browser's default voice. |
| **Chrome/Firefox on Android** | Voice selection is ignored — the browser always uses its default voice regardless of what is selected. This is a known Chromium bug. |
| **iOS/iPadOS Safari** | Only low-quality built-in voices are exposed via the Web Speech API. Enhanced and Premium voices downloaded through iOS Settings are not accessible to web apps. This is an Apple limitation. |

### Voice Quality Tips

- **Windows**: Microsoft Natural and Neural voices (e.g. "Microsoft Brian Online") are high quality but require an internet connection. Install them via Settings → Time & Language → Speech.
- **macOS**: Enhanced and Premium voices are available. Install them via System Settings → Accessibility → Spoken Content.
- **Android**: Use Chrome or Firefox. Voice quality depends on the TTS engine installed on your device (Settings → Accessibility → Text-to-speech).
- **iOS/iPadOS**: Quality is limited by Safari's API restrictions. No workaround is available.

### Voice Dropdown is Empty

If the voice dropdown shows no options:

1. **Edge on Android**: This is the known Microsoft bug described above. Try Chrome or Firefox instead.
2. **Other browsers**: Your browser may not support the Speech Synthesis API, or no TTS voices are installed on your device. Check your OS text-to-speech settings.

---

## Dictation (Speech-to-Text)

### Overview
The speech-to-text (dictation) feature uses the **Web Speech Recognition API**, which is built into modern browsers (Chrome, Edge, Safari). This API requires an internet connection because it uses Google's cloud-based speech recognition servers.

## Common Issues

### Network Error
**Symptom:** The microphone icon activates but immediately shows a "network error"

**Cause:** Something is blocking the connection to Google's speech recognition servers

**Solutions:**

1. **Check Antivirus/Firewall**
   - Temporarily disable your antivirus software
   - Check Windows Defender Firewall settings
   - Look for any security software that might block web requests

2. **Check Browser Settings**
   - Ensure microphone permissions are granted
   - Check that site permissions allow microphone access
   - Try resetting browser permissions

3. **Network Configuration**
   - Disable VPN if you're using one
   - Try a different network (e.g., mobile hotspot)
   - Check if you're on a corporate network with restrictions
   - Contact IT department if on managed network

4. **Browser Extensions**
   - Disable ad blockers
   - Disable privacy/security extensions temporarily
   - Try in incognito/private mode

### No Microphone Permission
**Symptom:** Browser doesn't ask for microphone permission

**Solution:**
1. Go to browser settings
2. Navigate to Site Permissions → Microphone
3. Ensure the site has permission to use microphone

### Microphone Not Working
**Symptom:** Permission granted but no audio detected

**Solution:**
1. Check Windows Sound Settings
2. Ensure microphone is not muted
3. Test microphone in other apps
4. Check microphone volume level
5. Try selecting a different microphone if multiple are available

## Testing Speech Recognition

To test if the issue is with your browser/system configuration:

1. Visit Google's official demo: https://www.google.com/intl/en/chrome/demos/speech.html
2. If this doesn't work, the issue is with your system, not our app
3. If it works, there may be a configuration issue with our implementation

## Browser Support

- ✅ **Google Chrome (HIGHLY RECOMMENDED)** - Full support, best performance
- ⚠️ **Microsoft Edge** - Known network error issues with speech recognition. Use Chrome instead.
- ✅ **Safari (macOS)** - Generally works well
- ❌ **Firefox** - Limited/no support for Web Speech API
- ❌ **Opera** - Limited support

### Microsoft Edge Known Issue

Microsoft Edge has a known bug with the Web Speech API that causes immediate "network" errors when attempting to use speech recognition, even though:
- The microphone permission is granted
- The API is supported
- The same code works perfectly in Chrome

**Solution:** Use Google Chrome for speech-to-text dictation.

**Why this happens:** This appears to be an Edge-specific bug in how the browser communicates with Google's speech recognition servers. Even though Edge and Chrome are both Chromium-based, they have different implementations of certain APIs.

## Still Having Issues?

If you've tried all the above and still can't get it working:

1. Check the browser console (F12) for detailed error messages
2. Look for `ERR_BLOCKED_BY_CLIENT` or similar network errors
3. Check the Network tab in DevTools for failed requests to Google servers
4. File an issue on GitHub with console logs and system details

## Technical Details

The Web Speech API makes requests to:
- `www.google.com/speech-api/`
- `speech.googleapis.com`

If these domains are blocked by your network or security software, speech recognition will not work.

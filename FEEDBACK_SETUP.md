# Setting Up GitHub Feedback Integration

The Help modal includes an in-app feedback form that submits bug reports, feature requests, and questions directly to a GitHub repository as issues.

## Setup Instructions

### 1. Create a Public Feedback Repository

Create a new public GitHub repository specifically for collecting feedback:

```bash
# Example repository name
storyteller-feedback
```

This keeps your main code repository private while allowing public issue tracking.

### 2. Generate a GitHub Personal Access Token

1. Go to https://github.com/settings/tokens
2. Click "Generate new token" → "Generate new token (classic)"
3. Give it a name like "Storyteller Feedback"
4. Set expiration (recommend "No expiration" for production)
5. Select **only** the `public_repo` scope
6. Click "Generate token"
7. **Copy the token immediately** (you won't see it again)

### 3. Configure Environment Variables

1. Copy `.env.example` to `.env`:
   ```bash
   cp .env.example .env
   ```

2. Edit `.env` and add your values:
   ```env
   VITE_GITHUB_TOKEN=ghp_your_token_here
   VITE_GITHUB_REPO=yourusername/storyteller-feedback
   ```

3. The `.env` file is already in `.gitignore` and won't be committed

### 4. Test Locally

```bash
npm run dev
```

Open the app, click File → Help, go to the Feedback tab, and submit a test issue.

### 5. For Production Deployment

**Important Security Note:** The GitHub token will be visible in your built JavaScript bundle. To mitigate risks:

- ✅ Use a dedicated feedback repository (not your main code repo)
- ✅ Token only has `public_repo` scope (can only create issues in public repos)
- ✅ Rate limiting is built into the form (5 minutes between submissions)
- ✅ Honeypot field catches basic bots
- ✅ You can revoke and regenerate the token anytime

**Alternative (More Secure):** Create a serverless function (Cloudflare Worker, Vercel Function, etc.) that acts as a proxy and keeps the token server-side. This is recommended for high-traffic production apps.

## Repository Setup

In your feedback repository, you can:

1. Create issue labels: `bug`, `feature`, `question`
2. Add an issue template in `.github/ISSUE_TEMPLATE/`
3. Enable GitHub Discussions for community questions
4. Set up automated responses with GitHub Actions

## Troubleshooting

**"Failed to submit feedback"**
- Check that `VITE_GITHUB_TOKEN` and `VITE_GITHUB_REPO` are set correctly in `.env`
- Verify the token hasn't expired
- Ensure the repository name format is `username/repo-name`

**Token exposed in bundle**
- This is expected for client-side apps
- Token only has access to create issues in one public repo
- Consider a serverless proxy for production if concerned

**Rate limiting**
- Users can only submit once per 5 minutes (client-side check)
- GitHub API has its own rate limits (5000 requests/hour for authenticated)

## Disable Feedback Form

To disable the feedback form without removing the code:

1. Remove the `VITE_GITHUB_TOKEN` from `.env`
2. The form will show an error message directing users to GitHub

Or remove the "Feedback" tab from `HelpModal.jsx` entirely.

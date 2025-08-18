# Authentication

## Purpose
The editor needs permission to access the same private spreadsheets your Google account can access.

## Recommended approach
Use your own Google access for your team (recommended over Demo). This avoids shared usage limits and gives you control.

## First‑time entry
- The first time you click `Configure`, you can paste the `Client ID` and `Client Secret`.
- Later, you can update them in `Project Settings → Plugins → Google DataTable Sync`.

![OAuth config dialog](./images/UeGoogleAuthConfig.png)

When the browser confirms success, you can close the tab:

![Authentication Successful](./images/AuthSuccessful.png)

## Where it is remembered
Your sign‑in is remembered per user for the current project (per‑user settings, not committed to source control).

## Switching account or resetting
Update credentials in Project Settings to switch; the plugin will prompt you to sign in again if the Client ID changes.

---

## Creating your own Google Client ID / Secret (step‑by‑step)

1) Open Google Cloud Console
   https://console.cloud.google.com/
   Create or choose a project for your team.

2) Enable the API
   “APIs & Services → Library” → enable “Google Sheets API”.

3) Configure the OAuth consent screen
   “APIs & Services → OAuth consent screen”
   - User type: “External” (simplest for teams)
   - App name: any team‑recognizable name
   - Add your team members as Test users (emails)
   - Save

4) Create OAuth credentials
   “APIs & Services → Credentials → Create credentials → OAuth client ID”
   - Application type: Choose “Desktop app”. This is required for the plugin's authentication flow.
Give it any name (e.g., "My Game Sync Client").
   - Create and copy the `Client ID` and `Client Secret`.

5) Enter credentials in UE
   `Project Settings → Plugins → Google DataTable Sync`
   Paste `Client ID` and `Client Secret`. Ensure “Redirect Uri” is `http://localhost:8080` (default).
   Click `Configure` on a DataTable and complete the one‑time sign‑in in the browser.

!!! note "After changing credentials"
    The plugin detects a different `Client ID` and asks you to sign in again. This ensures access is tied to the correct account.
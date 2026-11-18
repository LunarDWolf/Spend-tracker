# Spend Tracker (installable app with OneDrive sync)

Your expenses are kept in one small file, `expenses.json`, in your own OneDrive
(`OneDrive > Apps > Spend Tracker`). The app can only see that folder.
Works for personal Microsoft accounts (outlook.com, hotmail.com, live.com).

## Part 1: Put the app online (free, about 5 minutes)

GitHub Pages:
1. Create a free account at github.com, then click New repository. Name it `spend-tracker`, set it to Public, and create it.
2. Click "uploading an existing file", drag in ALL files from this folder (index.html, sw.js, manifest.webmanifest, both icons), and commit.
3. Go to Settings > Pages. Under Branch choose `main` and `/ (root)`, then Save.
4. After a minute your app is live at `https://YOUR-USERNAME.github.io/spend-tracker/`
   (the address Pages shows you). Note this exact address, including the final `/`.

## Part 2: Register the app with Microsoft (free)

1. Open portal.azure.com and sign in with your personal Microsoft account. If it asks you to
   create a directory/tenant, accept the free defaults.
2. Search for "App registrations" > New registration.
   - Name: `Spend Tracker` (this becomes the OneDrive folder name)
   - Supported account types: "Personal Microsoft accounts only"
   - Redirect URI: choose platform "Single-page application (SPA)" and paste your address from Part 1,
     exactly, including the final `/`
3. Click Register, then copy the "Application (client) ID" shown on the overview page.

## Part 3: Connect and install

1. Open `index.html` in a text editor (or GitHub's pencil icon), replace
   `PASTE-YOUR-CLIENT-ID-HERE` with your client ID, and save/commit.
2. Open your app address on your phone. Tap "Sign in with Microsoft" and approve access to the app folder.
3. Install it: Android Chrome menu > "Install app" (or "Add to Home screen"); iPhone Safari Share > "Add to Home Screen".

## Good to know
- It works offline. Changes sync when you're back online. Sync runs after each change, when you
  reopen the app, and with the "Sync now" button.
- Microsoft limits sign-in sessions for web apps like this to about 24 hours, so you may be asked to tap
  "Sign in" again now and then. Your data is never lost by this; it stays on the device until you sign in.
- If two devices change the same expense, the most recent change wins. Deleted expenses stay deleted.
- Use "Export all as CSV" to keep a backup copy.

# Deploy Guide — Two Palms Marketing ROI Tracker

This is a single-file HTML app. No build step, no dependencies to install. Here's how to get it live on Vercel via GitHub.

---

## What you have
- `index.html` — the entire tool in one file
- `README.md` — this guide (and a note for anyone who stumbles on the repo)

## What the tool does
- Runs entirely in the browser
- Saves your data in browser localStorage (persists between sessions on the same device/browser)
- No data is sent to any server
- You can export/import your data as JSON from the Settings tab

---

## Deploy in 4 steps (~5 minutes)

### Step 1 — Create a new GitHub repo
1. Go to github.com → click the **+** icon top-right → **New repository**
2. Name it something like `two-palms-roi-tracker`
3. Set it to **Private** (since this is for you, not the public)
4. Check "Add a README file" so the repo initializes
5. Click **Create repository**

### Step 2 — Upload the files
1. In your new repo, click **Add file** → **Upload files**
2. Drag in `index.html` (and optionally `README.md` to replace the default)
3. Scroll down → **Commit changes**

### Step 3 — Connect to Vercel
1. Go to vercel.com and log in (you can log in with GitHub)
2. Click **Add New** → **Project**
3. Find your `two-palms-roi-tracker` repo and click **Import**
4. On the configuration screen, leave everything at defaults
   - Framework Preset: **Other**
   - Build command: leave blank
   - Output directory: leave blank
5. Click **Deploy**

### Step 4 — Get your unlisted URL
- Vercel will give you a URL like `two-palms-roi-tracker.vercel.app`
- Bookmark it. That's your tool.
- The URL isn't indexed by search engines (I added a `noindex` meta tag), but anyone with the exact link could access it. For a tool like this with no sensitive data, that's fine.

---

## Making updates later
When you want to change the tool:
1. Edit `index.html` directly in GitHub (pencil icon in the top-right when viewing the file) OR edit locally and push
2. Vercel automatically redeploys within about 30 seconds of a commit
3. Your live URL updates with no action needed

---

## Backing up your data
The tool saves to your browser's localStorage — if you clear browser data or switch devices, the data is gone. To protect yourself:
- Go to **Settings** → **Export Data (.json)** periodically
- Save that JSON file somewhere safe (OneDrive)
- To restore: **Settings** → **Import Data**

---

## If something breaks
The tool uses React + Recharts loaded from CDN. If one of those CDN URLs ever changes or goes down, the tool won't load. The three external scripts it needs:
- `https://unpkg.com/react@18/umd/react.production.min.js`
- `https://unpkg.com/react-dom@18/umd/react-dom.production.min.js`
- `https://unpkg.com/recharts@2.12.7/umd/Recharts.js`
- `https://unpkg.com/@babel/standalone/babel.min.js`

Super unlikely to be an issue but worth knowing.

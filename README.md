# CSR

Delivery ride logging app — track stops, route times, manifests, and export to CSV. Works on phone (install to home screen) and offline after first load.

## Put it on GitHub Pages

### 1. Create a GitHub repository

1. Sign in at [github.com](https://github.com)
2. Click **New repository**
3. Name it `csr-ridelog` (or any name you like)
4. Leave it **Public**
5. Click **Create repository**

### 2. Upload this folder

**Option A — GitHub website (no Git install needed)**

1. On the new empty repo page, click **uploading an existing file**
2. Drag everything from this folder **except** `node_modules`, `deploy`, and `*.zip`
3. Commit with message `Initial CSR app`

**Option B — GitHub Desktop**

1. Install [GitHub Desktop](https://desktop.github.com/)
2. **File → Add local repository** → choose this `csr-ridelog` folder
3. **Publish repository** to GitHub

**Option C — Git command line**

```bash
cd csr-ridelog
git init
git add .
git commit -m "Initial CSR app"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/csr-ridelog.git
git push -u origin main
```

### 3. Turn on GitHub Pages

1. Open your repo on GitHub
2. **Settings → Pages**
3. Under **Build and deployment**, set **Source** to **GitHub Actions**
4. After the first push, open the **Actions** tab and confirm **Deploy CSR to GitHub Pages** succeeded

Your app will be live at:

`https://YOUR_USERNAME.github.io/csr-ridelog/`

(Use your actual repo name if you picked a different one.)

### 4. Install on iPhone

1. Open the GitHub Pages URL in **Safari**
2. **Share → Add to Home Screen**
3. Name it **CSR**

## Local testing (PC)

```powershell
powershell -ExecutionPolicy Bypass -File ".\serve.ps1"
```

Open `http://localhost:3000`

## Updating the app later

1. Edit `index.html` (and `sw.js` if you change caching)
2. Upload / push changes to GitHub
3. GitHub Actions redeploys automatically (usually within 1–2 minutes)
4. On your phone: open the site in Safari and refresh, or remove/re-add the home screen icon if an old version sticks

## Project files

| File | Purpose |
|------|---------|
| `index.html` | Full app (UI + logic) |
| `sw.js` | Offline cache / PWA |
| `manifest.webmanifest` | Install name & icon |
| `icons/icon.svg` | App icon |
| `.github/workflows/pages.yml` | Auto-deploy to GitHub Pages |

## Data storage

Ride data is saved in the browser on each device (`localStorage`). It is not stored on GitHub. Use **Export ride to CSV** to back up or move data between devices.
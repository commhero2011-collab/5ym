PathFit PWA v3.0.0 — deployment
================================
Contents
  index.html             complete app (single file, ~200 KB)
  manifest.webmanifest   name, icons, 4 home-screen shortcuts, store screenshots
  sw.js                  offline cache + reminder notification handling
  icons/                 192/512/maskable/Apple icons + SVG
  screenshots/           shown in the Android / desktop install dialog

Deploy
  1. Upload the whole folder (keep structure) to any HTTPS static host:
     GitHub Pages, Netlify, Azure Static Web Apps, IIS/nginx, SharePoint-hosted site, etc.
     Local test: python -m http.server 8080  ->  http://localhost:8080
  2. Open https://<host>/index.html once online. It is then cached and runs fully offline.
  3. Install: Chrome/Edge -> "Install app";  iPhone Safari -> Share -> Add to Home Screen.
  4. Updating: replace files and change VERSION in sw.js -> users get an in-app "Update" prompt.

Upgrading from v2.x: data is migrated automatically (schema v3), nothing is lost.

Privacy: no server code, no analytics. All data stays in each browser's IndexedDB.
Move data between devices with Settings > Encrypted backup.

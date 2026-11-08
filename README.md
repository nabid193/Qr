# QR Scanner — Vercel-ready static PWA

A browser-only QR scanner and QR generator created and developed by Nabid. No backend or database is required.

## Included features

- Scan QR codes with the device camera (HTTPS required).
- Scan QR codes from uploaded images.
- Generate QR codes for text, URLs, email, phone, Wi-Fi and vCard contacts.
- Local scan history with search, delete, JSON export and CSV export.
- Dark mode and scan preferences.
- PWA manifest, installable app icons and offline service worker.
- Scan history and settings stay in the browser's local storage; this app does not send QR contents to a server.

## Deploy to Vercel

1. Extract this ZIP file.
2. Create a GitHub repository and upload **all files and folders** from this project. Keep `index.html`, `manifest.json`, `sw.js`, `offline.html` and `vercel.json` in the repository root.
3. Sign in to Vercel and choose **Add New → Project**.
4. Import the GitHub repository.
5. Choose **Other** as the framework preset (or let Vercel detect a static site).
6. Leave the Build Command empty. Set the Output Directory to `.` if Vercel asks for one. No install command is needed.
7. Click **Deploy**. Vercel will provide an HTTPS URL.

You can also deploy the folder with the Vercel CLI from a terminal after installing the CLI and logging in:

```bash
vercel
```

For a production deployment:

```bash
vercel --prod
```

## Test after deployment

1. Open the HTTPS Vercel URL on a phone.
2. Allow camera permission and test **Start Camera**.
3. Test **Scan Image**, then generate and download a QR code.
4. Open **More → About** and confirm the app version and privacy note.
5. Visit the website once while online, then turn on airplane mode and reload. The app shell and QR libraries are cached for offline use after the service worker has installed successfully.
6. Install it from the browser's **Install app** or **Add to Home Screen** option.

## Notes

- Camera access requires HTTPS (Vercel provides HTTPS automatically) or `localhost` during local development. The camera is released when you leave the Scanner tab or background the app.
- Offline support requires one successful online visit and completion of service-worker installation so the app shell and its CDN libraries can be cached. Wait a few seconds after the first visit, then reload once before testing airplane mode.
- Scan history is stored per browser/device. It is not synced between devices and may be cleared if browser site data is deleted.
- The QR libraries are loaded from jsDelivr and cached by the service worker for subsequent offline use.


## Project credit

Created and developed by **Nabid**.

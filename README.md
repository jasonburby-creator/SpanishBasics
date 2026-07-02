# Ruta de Palabras

A bilingual Spanish travel vocabulary game — flashcards, a memory match, and a listening sprint, all sharing the same progress data. It's also an installable app (PWA), so once it's been opened one time with internet, it keeps working with **no connection at all** — good for planes, the metro, or anywhere without signal.

## Files in this folder

- `index.html` — the app itself
- `manifest.json` — tells iOS/Android how to install it as an app icon
- `sw.js` — the "service worker" that caches everything for offline use
- `favicon.ico` — the browser tab icon
- `icons/` — the app icon in the sizes iOS, Android, and browser tabs expect
- `README.md` — this file

All of these need to go into the GitHub repo together, in the same folder structure — the app won't install as offline-capable (and icons won't show up right) without `manifest.json`, `sw.js`, `favicon.ico`, and the `icons` folder alongside `index.html`.

## Put it on GitHub (drag-and-drop, no command line)

This comes as a `.zip` — **unzip it on your computer first.** GitHub's uploader doesn't unpack zip files automatically; if you drag the `.zip` itself in, it'll just sit there as one unusable file.

1. Unzip `ruta-de-palabras.zip` (double-click it on Mac/iPhone Files app, or right-click → Extract on Windows). You should end up with a folder containing `index.html`, `manifest.json`, `sw.js`, `favicon.ico`, `README.md`, and an `icons` folder.
2. Go to your existing `ruta-de-palabras` repo (or [github.com/new](https://github.com/new) if starting fresh).
3. Click **Add file → Upload files**.
4. Drag in everything from the unzipped folder **except the zip itself** — all the individual files plus the whole `icons` folder (GitHub's uploader accepts folders and preserves the `icons/` path automatically).
5. Commit changes.

## Deploy it on Vercel

Same as before — import the repo at [vercel.com/new](https://vercel.com/new), no config needed, click Deploy.

## Set it up for offline use on your iPhone (do this once, with internet)

1. Open your `ruta-de-palabras.vercel.app` link in **Safari** (must be Safari, not Chrome — "Add to Home Screen" with offline support only works reliably in Safari on iOS).
2. Let the page fully load. Tap through all three modes once (Tarjetas, Memoria, Escucha) — this makes sure everything needed gets cached, fonts included.
3. Tap the **Share** button (square with an arrow) → **Add to Home Screen** → **Add**.
4. You'll now have a "Ruta de Palabras" icon on your home screen, with the fan logo.

From now on, open the app from that **home screen icon**, not from Safari's address bar or bookmarks — the icon launches it as a standalone offline app; opening it through a browser tab doesn't get the same offline treatment on iOS.

### On the plane

Turn on airplane mode, tap the home screen icon — it should open normally, no blank page. Your progress still saves locally on your phone exactly like before.

### If it doesn't work offline the first time

- Make sure you opened it in Safari (not Chrome) when you set it up.
- Make sure you were connected to the internet and let it fully load before switching to airplane mode.
- If you update the app later (re-upload a new `index.html`), open it once with internet again so it re-caches the latest version — otherwise you'll keep seeing the old cached one offline, which is expected.

## Updating it later

Re-upload changed files to the GitHub repo the same drag-and-drop way, commit, and Vercel redeploys automatically. Remember to reopen the app once with internet afterward so your phone caches the new version.

## How progress is saved

Your flashcard/memory/listening progress is saved in your phone's browser storage, tied to that specific home-screen app icon. It is **not** synced across devices and isn't sent anywhere. There's a "Reiniciar progreso" button in the app itself if you ever want a clean slate.

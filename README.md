# Ruta de Palabras

A bilingual Spanish travel vocabulary game — flashcards, a memory match, and a listening sprint, all sharing the same progress data. No build step, no dependencies — it's a single `index.html` file.

## Put it on GitHub (drag-and-drop, no command line)

1. Go to [github.com/new](https://github.com/new) and create a new repository (e.g. `ruta-de-palabras`). Keep it public or private — either works with Vercel.
2. Don't initialize it with a README — leave it empty.
3. On the new repo's page, click **"uploading an existing file"** (or go to `Add file → Upload files`).
4. Drag `index.html` and this `README.md` into the upload box.
5. Scroll down and click **Commit changes**.

That's it — your repo now contains everything it needs.

## Deploy it on Vercel

1. Go to [vercel.com/new](https://vercel.com/new).
2. Under "Import Git Repository," find and select `ruta-de-palabras` (connect your GitHub account first if you haven't already).
3. Vercel will detect it as a static site automatically — no framework, no build command, no environment variables needed. Just click **Deploy**.
4. In about 30 seconds you'll get a live URL like `ruta-de-palabras.vercel.app`. Bookmark that on your phone — it behaves like a lightweight app.

## Updating it later

Whenever you want changes (new words, new categories, tweaks), just re-upload a new `index.html` to the same GitHub repo the same drag-and-drop way (`Add file → Upload files`, then commit). Vercel automatically redeploys within a minute or two — no extra steps on the Vercel side.

## How progress is saved

Your flashcard/memory/listening progress is saved in your phone's browser (`localStorage`), tied to that specific browser. It is **not** synced across devices and isn't sent anywhere — if you clear your browser data or switch phones, progress resets. There's also a "Reiniciar progreso" button in the app itself if you ever want a clean slate.

# Grind Log

A personal workout tracker built as a Progressive Web App (PWA). Runs entirely in the browser — no server required. Install it on your phone from Safari and it works offline.

**Live app:** https://fernmed.github.io/grind-log/

---

## Features

- **Log Tab** — Select any day of the week, toggle Lift and/or Cardio, fill in your exercises and sets, save the session
- **Lift tracking** — Pre-loaded default exercises with per-set reps and weight inputs. PR badge lights up when you hit a new personal best. Add or remove exercises freely
- **Cardio tracking** — Type selector (Walk, Run, Hybrid, Cycle, Other) with duration, distance, and pace fields
- **History Tab** — All past sessions listed newest first, expandable to see full details, deletable per entry
- **Progress Tab** — Total session counts, plus a line chart showing max weight over time for any weighted exercise
- **Cross-device sync** — Sign in with Google to sync sessions to Firebase Firestore in real time
- **Dark / Light mode** — Lakers-themed color palette. Toggle with the ☀️/🌙 button in the header. Preference is saved
- **Offline support** — Service worker caches the app so it loads without a connection
- **Installable** — Full PWA with manifest and icons. Add to Home Screen on iOS/Android

---

## Tech Stack

| Layer | Choice |
|---|---|
| App | Vanilla HTML/CSS/JS — zero build step |
| Storage | `localStorage` (primary) + Firebase Firestore (cloud sync) |
| Auth | Firebase Authentication — Google Sign-In |
| PWA | Web App Manifest + Service Worker |
| Fonts | Bebas Neue + DM Sans (Google Fonts) |
| Icons | Generated with Python / Pillow |
| Hosting | GitHub Pages |

---

## Deploy Your Own

1. Fork this repo
2. Enable GitHub Pages: **Settings → Pages → Branch: main**
3. Create a Firebase project at [console.firebase.google.com](https://console.firebase.google.com)
4. Enable **Firestore** (test mode) and **Authentication → Google**
5. Replace the `firebaseConfig` object in `index.html` with your own
6. Add your GitHub Pages domain to **Authentication → Settings → Authorized domains**
7. Access at `https://YOUR_USERNAME.github.io/grind-log/`

**To install on iPhone:** Open in Safari → Share → Add to Home Screen

---

## Project Structure

```
index.html      — Full app (HTML + CSS + JS, single file)
manifest.json   — PWA manifest
sw.js           — Service worker (cache-first strategy)
icon-192.png    — App icon 192×192
icon-512.png    — App icon 512×512
```

---

## Version History

See [CHANGELOG.md](CHANGELOG.md) for a full list of changes.

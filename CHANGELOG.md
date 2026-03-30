# Changelog

All notable changes to Grind Log are documented here.

---

## [1.6.0] — 2026-03-29

### Added
- Personal milestones — cumulative mile counter in the Progress tab with a progress bar toward the next milestone
- 7 milestone badges (10, 25, 50, 100, 250, 500, 1000 mi) displayed as a grid; unlocked badges highlight in gold
- Full-screen celebration overlay fires the first time a milestone is crossed after saving a session; auto-dismisses after 5 seconds or tap to close
- All activities with a distance field count toward the total

---

## [1.5.0] — 2026-03-29

### Added
- Strava integration — OAuth connect/disconnect button in the header
- Access tokens stored in `localStorage` with automatic refresh when expired
- "Import from Strava" button in the Cardio section (visible when connected)
- Bottom sheet lists 10 most recent Strava activities; tapping one pre-fills cardio type, duration, distance, and pace
- Imported activity date automatically sets the session date in the day strip

---

## [1.4.0] — 2026-03-29

### Added
- Load Previous Session — "↩ Load Previous Session" button at the top of the exercise area when Lift is toggled on
- Bottom sheet lists past lift sessions in reverse chronological order, each showing day/date and exercise count with a preview of exercise names
- Tapping a row pre-fills all exercises, sets, reps, and weights; session notes are not carried over
- Confirmation prompt fires before replacing exercises if the current session already has exercises loaded
- Button hidden when no past lift sessions exist

---

## [1.3.0] — 2026-03-29

### Fixed
- PWA no longer requires re-adding to home screen to receive updates — switched HTML fetch strategy from cache-first to network-first, with cache fallback for offline use
- Static assets (icons, manifest) remain cache-first
- Bumped service worker cache version to clear stale cache on first load

---

## [1.2.0] — 2026-03-29

### Added
- Lakers-themed color palette — deep purple/black dark mode, lavender light mode, gold action buttons throughout
- Dark / light mode toggle (☀️/🌙 button in header) with preference saved to `localStorage`
- Responsive desktop layout — nav moves to a left sidebar on screens ≥ 768px, content area expands to full width
- Progress chart re-renders in correct palette when switching themes

### Changed
- Accent color system split into `--accent` (text/borders, theme-aware) and `--accent-hi` (button backgrounds, always gold)
- Chart colors now derived dynamically from current theme instead of hardcoded hex values

---

## [1.1.0] — 2026-03-29

### Added
- Firebase Firestore cloud sync — sessions write to `users/{uid}/sessions` on save and delete from any device
- Google Sign-In via Firebase Authentication
- Sync status dot in header (pulsing gold = syncing, green = synced, red = error)
- User avatar with dropdown menu for sign-out
- On login, remote sessions are merged with local `localStorage` data (remote wins on conflict by session ID)
- Safari install banner shown when app is not in standalone mode

### Changed
- `saveSessions()` now accepts an optional session object to sync to Firestore
- `deleteSession()` also removes the document from Firestore

---

## [1.0.0] — 2026-03-29

### Added
- Initial PWA release
- **Log tab** — 7-day strip (Mon–Sun) with green dot indicators on logged days
- Lift section with 9 pre-loaded exercises (Goblet Squats, RDLs, Floor Press, Rows, Overhead Press, Push-ups, Curls, Calf Raises, Plank)
- Per-set reps and weight inputs, add/remove sets, add/remove custom exercises
- PR badge that lights up when a new weight exceeds the previous best for that exercise
- Cardio section with type selector (Walk, Run, Hybrid, Cycle, Other) and duration / distance / pace fields
- Session notes textarea
- **History tab** — sessions listed newest first, expandable entries, delete with confirmation
- **Progress tab** — total/lift/cardio session counts, exercise dropdown, canvas line chart with gradient fill and axis labels
- All data persisted to `localStorage` under `grindlog-sessions`
- PWA manifest, service worker (cache-first), and Pillow-generated icons (192×192 and 512×512)
- Bebas Neue + DM Sans typography from Google Fonts
- Safe area insets for iPhone notch and home bar

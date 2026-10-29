# VOVEL MVP

**Find your words.** A local-first vocabulary learning web app prototype.

## Run it

- Open `index.html` in a modern browser, or
- Serve the folder with any static file server, for example `python -m http.server 8000`, then visit `http://localhost:8000`.

Dictionary lookup uses the Free Dictionary API and needs an internet connection. Saved words, collections, daily sessions, review schedules, settings, and writing practice are stored in this browser's `localStorage`.

## Included

- Dictionary lookup with available phonetics, audio, meanings, examples, and synonyms
- Save, edit, delete, search, sort, and filter vocabulary
- Personal notes, original context, example sentences, learning status, and collections
- Daily Five selection persisted by local date and recall ratings
- SM-2-inspired simplified review scheduling
- Review centre, review history, dashboard statistics, weekly activity, and streak
- Words to Use writing practice (word matching only, not grammar checking)
- JSON backup/import with duplicate skipping and CSV export
- Responsive desktop/mobile layouts and local-data reset confirmation

## Important limitations

- This is a static browser-first MVP, not the full Next.js + Supabase production stack.
- There are no accounts, cloud sync, server database, password recovery, push notifications, or Android keyboard yet.
- Local data stays in the browser profile where it was created. Clearing browser storage can remove it; export backups regularly.
- The dictionary API can fail or omit information. The app displays available API information and lets you save a word manually.
- The scheduler is a simplified SM-2-inspired heuristic, not a scientifically validated optimal learning algorithm.
- No automated browser test suite is bundled; manual smoke checks are listed below.

## Manual smoke test

1. Open Find a word and search `ephemeral` while online.
2. Save the result, then refresh the page and check My Words.
3. Open the word, edit notes/context/example, and save.
4. Create a collection and assign the word to it.
5. Start Daily Five; with fewer than five words, the session should contain only available words.
6. Reveal the meaning and rate recall; check that the word's status/next review changes.
7. Export JSON, then import it again and confirm duplicates are skipped.
8. Export CSV and verify the file opens.
9. Check the layout at desktop and mobile widths.

## Publish on GitHub Pages

1. Create a GitHub repository named `vovel`.
2. Upload `index.html` and `README.md` to the repository root.
3. In repository **Settings → Pages**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Wait for GitHub Pages to publish the site; the URL will appear in the Pages settings.

## Next production steps

1. Port the UI and logic into Next.js + TypeScript with proper unit tests.
2. Add a Supabase schema/migrations and Row Level Security policies before enabling accounts or sync.
3. Implement an explicit local-to-cloud migration that preserves existing words.
4. Add reliable import validation, timezone tests, accessibility testing, and automated test coverage.
5. Design the Android keyboard as a separate privacy-first app; never collect or transmit arbitrary typed text.

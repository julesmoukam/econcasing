# Dira Practice

A static, browser-local economic consulting practice app. No API keys, accounts, database, framework, or paid fonts required.

## Use
- Practice one stage at a time; drafts autosave locally.
- Save reasoning creates an immutable timestamped version. Mark assisted revisions as “After tutoring”.
- Copy tutoring prompt, then paste into ChatGPT. This is a manual handoff, not an integration. Tutor compliance and scores are not guaranteed.
- Finish session copies a review request. Paste ChatGPT's review into History.
- Export JSON backups regularly. Import merges versions/reviews and preserves existing local drafts. New imported attempts retain drafts.
- Start a new attempt from History or Case library. Old answers stay in collapsed history.
- Only one case is included; shuffle is intentionally deferred until there are multiple cases.

## Deploy to Vercel
1. Extract this ZIP.
2. Upload the contents (including dist/, package.json and vercel.json) to a GitHub repository.
3. Import that repository in Vercel. Choose Other as the framework preset.
4. Leave the build command empty; set output directory to `dist`. There are no dependencies to install.
5. Deploy. Export progress on the old address and import on the new one.

## Local preview
From the project directory: `python3 -m http.server 8000 --directory dist`, then open http://localhost:8000.
Use a server rather than opening index.html as a file, because the code uses JavaScript modules.

## Source layout
- dist/cases.js: case content, paper link and selected evidence rows
- dist/app.js: interface and tutor prompt
- dist/state.js: storage validation and backup merge
- dist/style.css: responsive design
- dist/assets/dira-logo.png: original user-supplied logo

The brand's commercial Sentinel and Söhne font files were not provided; Georgia and system sans-serif fallbacks are used. Add properly licensed files if exact typography is needed.

## Evidence
Amodio, F., Medina, P., & Morlacco, M. (2025). Labor Market Power, Self-Employment, and Development. American Economic Review.
Author PDF (July 18, 2025): https://www.pamelamedinaquispe.com/files/papers/labor-market-power-aer.pdf
Case evidence is a selected-row transcription of Appendix Table A.2 columns 4–6 (PDF page 51); standard errors clustered at local labour market level. The full paper remains the authority. The consultation is fictional. Microdata and replication scripts are not bundled or verified.

## Verification
`npm run check` checks JavaScript syntax. `npm test` checks state validation, backup round trips/merge, and version isolation. No browser automation was available in the creation environment; perform a quick browser check before wider use.

## Limitations
No cloud sync, automatic scoring, ChatGPT integration, analytics, or backend. Data persists per browser and origin. Clearing site storage removes it. Saved review text is not parsed into a score dashboard. Avoid editing the same record in multiple tabs. The app stops writing if another tab updates storage; export before reloading.

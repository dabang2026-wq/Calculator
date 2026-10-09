# Simple Cord Length Calculator

A mobile-first cord length calculator with sequential cut tracking and local data persistence. Developed by **จาตูไหม่**.

## Features

- Simple, mobile-friendly interface with large touch targets
- English, Myanmar, and Thai language selector
- Enter starting cord length once and track the remaining length after each cut
- Automatically save entries and calculation history on the device using browser storage
- Cut calculation, meter verification, quick slack presets, and CSV history export
- PWA install metadata and service-worker caching for offline app-shell access
- GitHub Pages deployment workflow included

## Run locally

Use an HTTP server instead of opening `index.html` directly:

```bash
python -m http.server 8080
```

Then visit `http://localhost:8080`.

## Deploy to GitHub Pages

1. Extract the ZIP and upload all project files to a GitHub repository.
2. Commit to the `main` branch.
3. In **Settings → Pages**, choose **GitHub Actions** as the build/deployment source.
4. The included workflow deploys on each push to `main`.

## Saved data

Entries and history are saved locally in the same browser/app storage on this device. They should remain after closing and reopening the app, but clearing site data, changing browsers, or uninstalling/clearing app data may erase them. Local storage is not cloud-synced.

## Offline note

Open the app once while online so the service worker can cache the app shell. The current HTML still references Tailwind CSS, Font Awesome, and Google Fonts via external CDNs, so a first online load is needed for those assets and they may be unavailable offline unless previously cached. For a fully self-contained offline build, these dependencies should be bundled locally or replaced with local CSS/icons/fonts.

## Project files

- `index.html`
- `manifest.json`
- `service-worker.js`
- `README.md`
- `LICENSE`
- `.gitignore`
- `run-local.bat`
- `.github/workflows/deploy.yml`

## License

MIT.


## Responsive UX update
The interface includes responsive layouts for phones, tablets, desktop, and short landscape screens; accessible focus indicators; zoom-friendly viewport settings; safe-area spacing; and horizontally scrollable history on small screens.


## Daylight usability update

The latest daylight-first interface uses stronger text contrast, larger number inputs, clearer focus states, a more visible Calculate button, improved history modal sizing, better small-screen spacing, and landscape handling. The app keeps English, Myanmar, and Thai options, saved history, remaining-length tracking, and the existing calculation logic.

The service-worker cache was versioned so browsers can pick up the updated app shell. After deployment, refresh the app once while online.


## Optional total cord length tracking
- You can enter the original total cord length once before the first cut.
- Saving it locks the value and stores it in this browser/site. The app does not offer an edit or remove control.
- If you leave it blank when making the first cut, total-length tracking is skipped and no total-available-meters card is shown.
- Resetting the calculator does not clear the saved total length.


## Input spacing and performance polish
- Standardized number and text field padding, minimum height, label line-height, and spacing between form controls.
- Improved input placeholder contrast and keyboard focus visibility.
- Kept numeric values aligned with tabular numerals for easier measurement comparison.
- Reduced card transition work to border and shadow changes instead of animating every property.
- Updated the service-worker cache version so the new interface can be refreshed after deployment.

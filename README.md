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

# Cord Calculator

A daylight-first, mobile-friendly **Cord Calculator & Cut Sequencer** for field use.

Calculate cutting points, verify meter differences, sequence multiple cuts, save calculation history locally, and export the cut log as CSV.

## Features

- Starting reel mark and target end mark inputs
- Extra meter / safety slack calculation
- Quick slack presets
- Automatic cut calculation
- Meter-check verification with PASS / FAIL status
- Sequential cut workflow
- Local calculation history
- Detail view for saved cuts
- CSV export
- Reset and next-cut controls
- Responsive mobile layout
- Daylight-optimized high-contrast UI
- Offline-ready PWA behavior
- LocalStorage data persistence
- Online/offline status indicator

## Calculation

The calculator uses the following core relationship:

```text
Cutting Point = Target End Mark − Extra / Safety Slack

Result = Starting Reel Mark − Cutting Point

Meter Check = Target End Mark − Cutting Point
```

A calculation passes when the meter check matches the requested extra/safety value and the calculated values are valid.

## Run locally

Because this is a browser PWA, use a local HTTP server rather than opening the HTML file directly.

### Python

```bash
python -m http.server 8080
```

Then open:

```text
http://localhost:8080
```

## GitHub Pages

1. Create a new GitHub repository.
2. Upload the contents of this folder.
3. Commit the files to the `main` branch.
4. Open **Settings → Pages**.
5. Under **Build and deployment**, choose **GitHub Actions**.
6. GitHub will use the workflow in `.github/workflows/deploy.yml`.
7. After deployment, open the Pages URL shown by GitHub.

## PWA / Offline Use

The application includes PWA metadata and service-worker support. Once served over HTTPS and loaded successfully, supported browsers can install it as an app and cache the application for offline field use.

## Project Structure

```text
cord-calculator/
├── index.html
├── manifest.json
├── service-worker.js
├── README.md
├── LICENSE
├── .gitignore
└── .github/
    └── workflows/
        └── deploy.yml
```

## Data & Privacy

Calculation history is stored locally in the browser using `localStorage`. No server-side database is required for the calculator's normal operation.

## License

MIT License.

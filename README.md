# Cork City Parking Monitor

A lightweight, installable Progressive Web App (PWA) that shows live car park availability in Cork City, sourced directly from the Cork City Council Open Data Portal.

## Features

- **Live availability** — pulls real-time occupancy data for Cork city car parks from the [Cork City Council Open Data Portal](https://data.corkcity.ie).
- **Installable PWA** — add it to your home screen (Android/iOS) or desktop (Chrome/Edge) for an app-like experience, with a service worker for offline asset caching.
- **Auto-speech announcements** — optionally have car park availability read aloud via the Web Speech API.
- **Screen wake lock** — keeps the display awake while monitoring, useful when checking availability on the move.
- **Responsive design** — built with Tailwind CSS, works well on both mobile and desktop.

## Project Structure

```
.
├── index.html      # Main app: UI, data fetching, and all client-side logic
├── manifest.json   # PWA manifest (name, icons, theme colors, display mode)
├── sw.js           # Service worker for caching app assets and offline support
└── icons/          # App icons (favicon, touch icons, maskable/desktop icons)
```

## Running Locally

This is a static, dependency-free app — no build step required. Serve the directory with any static file server, for example:

```bash
python3 -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000) in your browser.

> Note: the app fetches live data from `https://data.corkcity.ie`, so an internet connection is required for up-to-date results.

## Data Source

Car park availability is retrieved from the Cork City Council Open Data Portal's datastore search API:

```
https://data.corkcity.ie/api/3/action/datastore_search
```

## Deployment

Being a static site, this project can be hosted on any static hosting provider (e.g. GitHub Pages, Netlify, Vercel) — just deploy `index.html`, `manifest.json`, `sw.js`, and the `icons/` directory.

## License

This project's code is licensed under the [MIT License](LICENSE) — you're free to use, modify, and distribute it, provided the copyright notice is retained.

Note that the *data* displayed by the app is not covered by this license: parking availability is sourced from the [Cork City Council Open Data Portal](https://data.corkcity.ie) and remains subject to that portal's own open data terms of use.

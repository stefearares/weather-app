**Project**
- **Name:** Weather App
- **Description:** A responsive single-page weather application that shows current conditions and a short forecast for the user's location. It uses a small local API layer under `api/` and a lightweight front-end in `scripts/` with styles organized in SCSS partials.

**Features**
- **Current weather & forecast:** Displays current conditions and a short forecast.
- **Geolocation:** Attempts to use the browser location, falls back to manual input.
- **Responsive UI:** Styles written in SCSS under `styles/` and compiled to CSS.
- **Animated effects:** Icons and slider effects in `effects/`.

**Quick Start**
- **Prerequisites:** A modern browser. For local development, Node.js (optional) or Python (optional) for a static server, and `sass` if you want to compile SCSS locally.
- **Open locally:** The app can be opened directly by opening [index.html](index.html) in your browser.
- **Run a simple HTTP server (recommended):**

```bash
# Install a tiny static server (optional)
npx http-server -c-1 .
# or using Python 3
python3 -m http.server 8000
```

**Development**
- **Compile SCSS:** If you edit SCSS, compile `styles/main.scss` to `styles/main.css`:

```bash
npx sass --watch styles/main.scss:styles/main.css
```

- **Scripts:** Front-end logic is in `scripts/app.js`. API helpers live in `api/`:
	- `api/geolocation.js` — browser geolocation helper
	- `api/forecast.js` — forecast formatting / API wrapper
	- `api/weatherdata.js` — fetches weather provider data

**File Structure**
- **index.html:** Main entry point that loads styles and `scripts/app.js`.
- **scripts/** — front-end JavaScript.
- **api/** — small modular API helpers and data fetchers.
- **effects/** — visual scripts like `icons.js` and `weather-slider.js`.
- **styles/** — SCSS sources and compiled CSS. Partials are under `styles/components/` and `styles/abstracts/`.
- **media/** — fonts and static assets.

**API / Data Flow**
- The UI calls helper functions in `api/` which fetch/normalise provider responses. The app avoids exposing API keys in the UI; if you add a provider that requires a key, prefer a server-side proxy.

**Contributing**
- **Style:** Follow existing SCSS structure when adding styles.
- **JS:** Keep modules small and pure; add unit-friendly helpers in `api/` if needed.
- **Pull requests:** Provide a short description and note any manual steps to run.

**TODO**
- **Hamburger menu:** finish accessibility and mobile toggle.
- **Finalize rename buttons:** confirm labels and keyboard behavior.
- **Polish copy:** improve the dynamic header text for location messaging.

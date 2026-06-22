# StylePatch

A lightweight browser extension that lets you customize any webpage's background color, text color, and font size instantly.

> Chromium-based · Manifest V3 · Zero tracking · Per-site settings

---

## Features

| Feature | Description |
|---------|-------------|
| 🎨 **Background & Text Color** | Pick any color via native color picker or type hex code directly |
| 🔠 **Font Size Scaling** | Adjust from 60% to 150%, works on sites using fixed px values |
| 👁️ **Eye Care Mode** | One-click warm tone preset for comfortable reading |
| 💾 **Per-Site Settings** | Save different styles for different websites, auto-restore on revisit |
| ⚡ **Real-Time Preview** | All changes apply instantly as you drag, no page reload needed |
| 🔄 **Dynamic Content** | Automatically styles dynamically loaded content (SPA, lazy load) |
| 🔒 **Minimal Permissions** | Only `activeTab` + `storage` — no unnecessary access |

---

## Preview

<p align="center">
  <img src="screenshot/preview.png" alt="StylePatch Preview" width="640">
</p>

---

## How It Works

```
User clicks extension icon
        │
        ▼
   Popup UI opens
        │
        ▼
Content script injects <style> tag into page
        │
        ▼
Page appearance updates in real-time
        │
        ▼
Settings saved to chrome.storage.local (per domain)
```

- **Popup** — User interface with color pickers, font slider, and action buttons
- **Content Script** — Injects a single `<style>` element to override page styles
- **Background Service Worker** — Handles storage and message routing

---

## Supported Browsers

| Browser | Status |
|---------|--------|
| Google Chrome | ✅ Fully supported |
| Microsoft Edge | ✅ Fully supported |
| Other Chromium-based browsers | ✅ Should work |

> Built on Chromium's extension platform — works across all Chromium-based browsers.

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Platform | Chromium Extension (Manifest V3) |
| Frontend | Vanilla JavaScript, HTML5, CSS3 |
| Build Tool | Node.js + Terser |
| Storage | `chrome.storage.local` |

---

## Permissions

| Permission | Why Needed |
|------------|-----------|
| `activeTab` | Apply styles to the currently active tab |
| `storage` | Save and load per-site style configurations |

> **Privacy-first**: We do NOT use `<all_urls>` host permission. We do NOT read browsing history, track users, or send any data externally.

---

## Installation

### From Web Store

_(Coming soon)_

### Load Unpacked (Developer)

1. Clone or download this repository
2. Open your browser's extension page:
   - **Chrome**: `chrome://extensions/`
   - **Edge**: `edge://extensions/`
3. Enable **Developer mode** (top-right toggle)
4. Click **Load unpacked** and select the project folder
5. Click the StylePatch icon in your toolbar to start

---

## Usage

1. **Click the StylePatch icon** in your browser toolbar
2. **Pick colors** — Use the native color picker or type a hex code (e.g., `#FF5733`)
3. **Adjust font size** — Drag the slider from 60% to 150%
4. **Eye Care mode** — Click 👁 for a warm, comfortable reading theme
5. **Save** — Click **Apply & Save** to persist settings for this site
6. **Reset** — Click ↺ to restore the site's default appearance

Settings are automatically saved when the popup closes, and restored when you revisit the same site.

---

## Build

```bash
npm install
npm run build
```

Output will be in the `build/` directory, ready to load into Chrome or Edge.

---

## Project Structure

```
style-patch/
├── manifest.json        # Extension configuration (Manifest V3)
├── package.json         # Build dependencies
├── build.js             # Build script (Terser minification)
├── assets/              # Extension icons
├── popup/               # Popup UI (HTML, CSS, JS)
├── content/             # Content script (style injection)
└── background/          # Service Worker (storage & messaging)
```

---

## Roadmap

- [ ] Element picker for targeted CSS modifications
- [ ] Custom CSS editor (advanced mode)
- [ ] Domain blacklist / whitelist
- [ ] Export & import style configurations
- [ ] Dark mode presets

---

## License

Copyright © 2026 StylePatch. All rights reserved.

---

> **Note:** This repository is for **project showcase purposes only**. It does not contain the full source code, manifest, icons, or build scripts. Full source code will **not** be published here.

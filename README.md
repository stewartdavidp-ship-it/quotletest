# Quotle PWA Package

## Version: 1.0.2

## Contents

```
quotle-pwa/
├── index.html      - Main game file with PWA support
├── manifest.json   - PWA manifest
├── sw.js          - Service worker for offline support
├── icons/
│   ├── icon-source.svg  - Source icon for generating PNGs
│   ├── icon-72.png      - Required
│   ├── icon-96.png      - Required
│   ├── icon-128.png     - Required
│   ├── icon-144.png     - Required
│   ├── icon-152.png     - Required (iOS)
│   ├── icon-192.png     - Required (Android/Chrome)
│   ├── icon-384.png     - Required
│   └── icon-512.png     - Required (splash screens)
└── README.md
```

## Deployment

1. **Generate Icons**
   
   Use the `icon-source.svg` to generate PNG icons at required sizes:
   - 72x72, 96x96, 128x128, 144x144, 152x152, 192x192, 384x384, 512x512
   
   Tools: Figma, Sketch, or online converters like realfavicongenerator.net

2. **Deploy Files**
   
   Upload all files to your web server at the root:
   - `https://quotle.game/index.html`
   - `https://quotle.game/manifest.json`
   - `https://quotle.game/sw.js`
   - `https://quotle.game/icons/*`

3. **HTTPS Required**
   
   PWAs require HTTPS. Service workers won't work on HTTP.

## Features

- **Offline Support**: Game works without internet after first load
- **Install to Home Screen**: Users can install as standalone app
- **Auto-Updates**: Service worker checks for updates hourly
- **Install Banner**: Shows install prompt on mobile devices

## Game Shelf Integration

This PWA still works with Game Shelf:
- GS badge in header links back to Game Shelf
- Share text is compatible with GS clipboard detection
- localStorage sync keys are preserved

## Updating

When updating the game:

1. Update version in `index.html`:
   ```html
   <meta name="version" content="1.0.3">
   ```

2. Update version in `sw.js`:
   ```javascript
   const CACHE_VERSION = 'v1.0.3';
   ```

3. Deploy new files - service worker will auto-update users

## Theme Colors

- Background: `#1a1a1a` (dark)
- Theme: `#8B2635` (burgundy)
- Accent: `#D4AF37` (gold)

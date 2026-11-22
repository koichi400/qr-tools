# QR Tools — QR & Barcode Generator

Generate QR codes and barcodes entirely in your browser. No tracking, no sign-up, no watermarks — the values you enter never leave your device.

A static web app with no backend and no database. The QR and barcode libraries are bundled directly into `index.html`, so the page makes no external requests and works fully offline once loaded.

## Features

- **QR codes** — Text / URL, Wi-Fi, Contact (vCard), Email, Phone, SMS, Location, and Event payloads, with live preview as you type
- **Barcodes** — CODE128, EAN-13 / JAN, CODE39, and NW-7 (Codabar)
- **Validation** — EAN-13 / JAN check digit is calculated automatically from 12 digits and verified when 13 digits are entered; characters outside a symbology's character set are flagged inline
- **Customize** — Foreground / background colors (transparent background supported), size, QR error-correction level, bar width / height, and human-readable text toggle for barcodes
- **Caption** — Optional text under the QR code (off by default), editable, with safe automatic labels (e.g. the Wi-Fi network name — never the password); the caption is baked into PNG / SVG downloads
- **Export** — Download as PNG or SVG

## Libraries (bundled, no CDN)

- [qrcode](https://github.com/soldair/node-qrcode) 1.5.3 — QR code generation
- [JsBarcode](https://github.com/lindell/JsBarcode) 3.11.6 — Barcode generation

## Internationalization (i18n)

The UI is available in English, Japanese, and Thai, switchable with the **EN / 日本語 / ไทย** toggle in the top-right corner. On first visit the language is detected from the browser's language setting, and the chosen language is saved in `localStorage` so it persists on the next visit.

## Deploy to Cloudflare Pages (free)

### Option A: GitHub integration (auto-deploy on push)

1. Push this folder to a GitHub repository
2. In the Cloudflare Dashboard, go to **Workers & Pages → Create → Pages → Connect to Git** and select the repository
3. Build settings:
   - Framework preset: `None`
   - Build command: *(leave empty)*
   - Build output directory: `/` (root)
4. Click **Save and Deploy** — the site goes live at `https://<project-name>.pages.dev`
5. Optional: attach a custom domain under **Custom domains** in the Pages project (e.g. `qr.example.com`)

### Option B: Direct upload

In the Cloudflare Dashboard, go to **Workers & Pages → Create → Pages → Upload assets** and upload this folder (`index.html`).

### Option C: Wrangler CLI

```bash
npx wrangler pages deploy . --project-name qr-tools
```

## Run locally

```bash
npx serve .
# or
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser.

## Trademark

QR Code is a registered trademark of DENSO WAVE INCORPORATED.

## License

MIT — © 2026 Koichi Uemura. See [LICENSE](LICENSE).

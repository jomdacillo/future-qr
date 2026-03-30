# Future QR

A sleek, browser-based QR code generator with glassmorphism UI. No server required — just open the HTML file in any browser.

![Future QR](https://img.shields.io/badge/Future%20QR-Generator-7c3aed?style=for-the-badge&logo=qrcode&logoColor=white)
![HTML](https://img.shields.io/badge/HTML-Single%20File-22d3ee?style=for-the-badge&logo=html5&logoColor=white)
![No Install](https://img.shields.io/badge/No%20Install-Required-e879f9?style=for-the-badge)

---

## Features

- **Custom URL** — generate QR codes for any link
- **Logo embedding** — upload any PNG icon (Instagram, brand mark, etc.) centred in the QR
- **Proportional scaling** — logos maintain their natural aspect ratio, never stretched
- **Custom colours** — choose module and background colours with a colour picker
- **Error correction levels** — L / M / Q / H (H recommended when using a logo)
- **Output size control** — from 200px up to 1200px (600px = print quality at 300dpi)
- **PNG export** — high-resolution download with logo composited at full size
- **SVG export** — true vector output built from individual `<rect>` modules, infinitely scalable
- **Queue system** — add multiple QR codes and download them all as a ZIP
- **Glassmorphism UI** — built with Tailwind CSS, Space Grotesk font, animated mesh background

---

## Usage

### Option 1 — Open directly
Download `future-qr.html` and open it in any modern browser. No install, no server.

### Option 2 — GitHub Pages
Enable GitHub Pages on this repo (Settings → Pages → Branch: main) and access it at:

```
https://jomdacillo.github.io/future-qr/future-qr.html
```

---

## How SVG export works

Unlike basic SVG QR generators, Future QR builds real vector output:

1. Renders the QR to a canvas at full resolution
2. Reads pixel data with `getImageData()`
3. Detects module size automatically
4. Writes individual `<rect>` elements for every dark module
5. Embeds the logo as a base64 `<image>` tag with `preserveAspectRatio`

The result is a self-contained, infinitely scalable SVG — perfect for print and design tools like Illustrator or Figma.

---

## Logo tips

- Use **PNG with transparent background** for best results
- Logo covers ~20% of the QR by default — keep under 25% for reliable scanning
- Error correction **H** (30%) is set by default to compensate for logo coverage
- Test with multiple scanner apps after generating (iPhone Camera, Google Lens)

---

## Also included — Node.js CLI version

`generate-qr.js` — a command-line version using **Sharp** + **qrcode** for batch generation:

```bash
npm install
node generate-qr.js
```

Place your logos in `./assets/` and outputs appear in `./output/`.

---

## Tech stack

| Layer | Tool |
|-------|------|
| UI framework | Tailwind CSS (CDN) |
| QR generation | qrcodejs |
| ZIP packaging | JSZip |
| Font | Space Grotesk + Space Mono |
| Logo compositing | HTML Canvas API |
| SVG export | Custom pixel-reading algorithm |

---

## License

MIT — free to use, modify, and distribute.

---

Made with precision by [@jomdacillo](https://github.com/jomdacillo)
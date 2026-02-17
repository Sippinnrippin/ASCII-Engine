# ASCII Engine

> Convert any photo into ASCII art — entirely in your browser.

![License: MIT](https://img.shields.io/badge/license-MIT-00ff88?style=flat-square)
![No server](https://img.shields.io/badge/server-none-ff3366?style=flat-square)
![Single file](https://img.shields.io/badge/build-single%20HTML-00ff88?style=flat-square)

---

## What it is

ASCII Engine is a single, self-contained HTML file that turns any image into ASCII art. No backend, no dependencies to install, no data ever leaves your machine. Open the file in a browser and start converting.

---

## Features

- **Drag & drop or click to upload** — supports PNG, JPEG, WEBP, GIF, BMP (up to 20 MB)
- **6 character sets** — Standard (70 chars), Simple, Block Elements, Binary (01), Hex (0–F), Braille
- **Adjustable controls** — output width, brightness, contrast, invert toggle
- **Color mode** — renders each character in the original pixel's color using inline CSS
- **Zoom controls** — scale the output from 20% to 400% without reflowing
- **Copy to clipboard** — one click, plain text
- **Download as `.txt`** — save the raw ASCII art file
- **Keyboard shortcut** — `Ctrl+Enter` (or `Cmd+Enter`) to re-render
- **Performance readout** — shows render time and character count

---

## Usage

1. Download [`ascii-engine.html`](ascii-engine.html)
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge)
3. Upload an image, adjust settings, hit **RENDER**

No install. No build step. No internet required after the page loads.

---

## Privacy & Security

- **100% client-side** — your images are never uploaded anywhere
- **Strict Content Security Policy** — blocks external script injection
- **Input validation** — file type and size are checked before processing
- **No localStorage, no cookies, no tracking**
- All image processing happens on a hidden `<canvas>` element in-memory

---

## How it works

1. The uploaded image is drawn onto an offscreen `<canvas>` scaled to the target character grid
2. Each pixel's luminance is computed using the ITU-R BT.709 perceptual weighting: `0.2126R + 0.7152G + 0.0722B`
3. The luminance value maps to a character in the selected set (darkest → lightest)
4. In color mode, each character is wrapped in a `<span>` with its original RGB color
5. Aspect ratio is corrected with a `0.45` factor (monospace characters are ~2× taller than wide)

---

## Customization

All char sets are defined in the `CHAR_SETS` object at the top of the script block — easy to add your own. The visual theme uses CSS custom properties (`--accent`, `--bg`, etc.) for straightforward restyling.

---

## Browser Support

Any browser that supports:
- `<canvas>` with `getImageData`
- `CSS Grid`
- `Clipboard API` (for the copy button — falls back gracefully)

This covers all modern browsers released after 2018.

---

## License

[MIT](LICENSE) — free to use, modify, and distribute.

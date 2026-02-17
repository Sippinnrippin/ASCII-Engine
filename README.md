# ASCII Engine

> Convert any photo into ASCII art — entirely in your browser.

![License: Custom](https://img.shields.io/badge/license-source--available-ff3366?style=flat-square)
![No server](https://img.shields.io/badge/server-none-ff3366?style=flat-square)
![Single file](https://img.shields.io/badge/build-single%20HTML-00ff88?style=flat-square)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-00ff88?style=flat-square)

---

## What it is

ASCII Engine is a single, self-contained HTML file that turns any image into ASCII art. No backend, no dependencies to install, no data ever leaves your machine. Download the file, open it in a browser, and start converting.

Created by **Sippinnrippin ZF**

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
- **Theme editor** — 6 built-in presets and full custom color control for every UI element
- **Persistent settings** — your theme and render preferences are saved automatically and restored on next open

---

## Usage

1. Download [`ascii-engine.html`](ascii-engine.html)
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge)
3. Upload an image, adjust settings, hit **RENDER**

No install. No build step. No internet connection required after the page loads.

---

## Theme Editor

Click **⬡ THEME** in the top-right of the header to open the theme panel.

**Presets** — one-click themes:

| Preset | Style |
|--------|-------|
| Default | Dark background, green accent |
| Light | Light grey, blue accent |
| Amber | Black background, amber terminal |
| Cyan | Deep navy, cyan accent |
| Rose | Dark purple, pink accent |
| Matrix | Pure black, neon green |

**Custom colors** — individual color pickers for background, surface, borders, primary accent, secondary accent, text, dim labels, and the ASCII output color. Changes apply live. Hit **RESET TO DEFAULT** to revert.

---

## Persistent Settings

All preferences are saved automatically to `localStorage` in your browser and restored every time you open the file. This includes:

- All render controls (width, brightness, contrast, character set, invert, color mode)
- Your full custom theme

Settings are stored locally on your machine and never sent anywhere. If you use private/incognito mode, settings will not persist between sessions — this is expected browser behavior.

---

## Platform Support

ASCII Engine runs in the browser, so it works on any OS that can run a modern browser:

| Platform | Tested browsers |
|----------|----------------|
| Windows 10/11 | Chrome, Firefox, Edge |
| macOS 12+ | Chrome, Firefox, Safari |
| Linux | Chrome, Firefox |

No installation, no runtime, no dependencies. Just open the `.html` file.

---

## Privacy & Security

- **100% client-side** — your images are never uploaded anywhere
- **Strict Content Security Policy** — blocks external script injection
- **Input validation** — file type and size are checked before processing
- **localStorage only** — stores theme and render preferences locally, no tracking, no cookies, no external requests
- **Validated storage reads** — saved theme data is checked against a hex color regex before use; corrupt or tampered values are ignored
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

All character sets are defined in the `CHAR_SETS` object in the script — easy to add your own. The visual theme is built entirely on CSS custom properties (`--accent`, `--bg`, etc.) so restyling is straightforward.

---

## Contributing

Contributions are welcome via pull request. All PRs are reviewed and must be approved before merging — nothing is merged automatically.

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting. Key rules: keep the single-file architecture, don't remove author credit, no external dependencies.

---

## License

This project uses a **custom source-available license** — see [LICENSE](LICENSE) for the full terms.

**In short:**
- ✅ Use it personally
- ✅ Submit pull requests / contribute
- ✅ Share it unchanged (with credit)
- ❌ Redistribute or publish it as your own
- ❌ Sell or commercialize it
- ❌ Remove the author credit
- ❌ Fork and publish under a different name

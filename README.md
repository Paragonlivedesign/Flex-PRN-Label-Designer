# Flex PRN Label Designer

A browser-based designer for **Zebra ZPL** labels, built for **Flex Rental Solutions** workflows: lay out text, barcodes, lines, and images; use Flex merge tokens (e.g. `[barcode]`); preview with [Labelary](https://labelary.com); export `.prn`, save/load projects as JSON, and optionally look up Flex records via the Flex API.

**By [Paragon Live Design](https://github.com/Paragonlivedesign).**

## Quick start

1. Clone or download this repo.
2. Open **`label-designer.html`** in **Chrome** or **Edge** (double-click or drag into the window).

Preview needs an internet connection (Labelary and a few scripts from jsDelivr). If the canvas stays blank when opened as `file://`, serve the folder locally, for example:

```bash
npx --yes serve .
```

Then open the URL it prints (e.g. `http://localhost:3000/label-designer.html`).

## What’s in the repo

| File | Purpose |
|------|---------|
| `label-designer.html` | The full app (single file — no build step). |
| `.gitignore` | Keeps local labels, configs, and docs out of Git. |

Use **Settings** (bottom-right) for theme, layout defaults, help, printer / PowerShell / relay, Flex API, scan & load, and about.

## Flex usage tips

- **Copy ZPL** and paste into Flex’s label template field. Use **Include Flex header** if your workflow expects the binary header line (as in typical Flex `.prn` samples).
- **Import…** loads existing `.prn` / `.txt` for edit and preview; **Save .prn** downloads the current ZPL.
- **Save project** / **Open project** stores the full layout (and optional imported ZPL) as JSON.

## License / rights

See the in-app **About** tab for support contact and copyright notice.

---

*Beta-quality tool — feedback welcome via the email in Settings → About.*

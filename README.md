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

## References & resources

Where the behavior and docs for this designer come from (handy whether you’re using the app or maintaining it).

### Flex Rental Solutions

- [Flex Rental Solutions](https://www.flexrentalsolutions.com/) — product / company home.
- **Flex5 REST API** — documented per tenant in **Swagger UI** at  
  `https://<your-subdomain>.flexrentalsolutions.com/f5/swagger-ui/index.html`  
  (replace `<your-subdomain>` with your tenant). Create API keys under **Integrations → API** in Flex. The app’s **Flex API** settings expect the `X-Auth-Token` header, consistent with that OpenAPI surface.
- **Labels in Flex** — barcode / label templates and merge tokens are configured inside your Flex product; paste ZPL from this tool into the label template field as your workflow allows.

### Label preview — Labelary

This designer’s **Preview (Labelary)** pane sends ZPL to Labelary’s public API (same idea as their docs — not used for production print in the app).

- [Labelary](https://labelary.com/) — online ZPL viewer / service home.
- [Labelary ZPL Label API](https://labelary.com/service.html) — REST API (`api.labelary.com`, `GET`/`POST` printers `dpmm`, label size, etc.) — matches how preview URLs are built in code.

### Zebra printers & ZPL

- [Zebra Technologies](https://www.zebra.com/) — printers, firmware, support.
- [Zebra documentation & downloads](https://www.zebra.com/us/en/support-downloads/documentation.html) — portal for manuals and programming references (search for **ZPL**, **ZPL II**, **Programming Guide**, or your printer model).
- [Zebra developer resources](https://developer.zebra.com/) — SDKs, APIs, and deeper integration docs.
- **Raw printing from a PC** — many Zebra setups accept ZPL over **raw TCP** (often port **9100** or your site’s chosen raw port, e.g. **6101**). The app’s **Printer** tab and PowerShell snippet follow that pattern; reachability is the same as any raw socket to the printer IP/hostname.

### JavaScript / CDN libraries used in `label-designer.html`

- [jsDelivr](https://www.jsdelivr.com/) — CDN used for **pako** (compression, e.g. Z64-style image helpers) and **qrcode** (ESM) where the page pulls them.
- [Google Fonts](https://fonts.google.com/) — **Montserrat** and **Oswald** for the UI typography.

### Other

- [MDN Web Docs](https://developer.mozilla.org/) — `canvas`, `fetch`, and browser APIs used for the editor and preview.
- [Node `serve` (static server)](https://www.npmjs.com/package/serve) — optional `npx serve` when `file://` preview is blocked.

---

## License / rights

See the in-app **About** tab for support contact and copyright notice.

---

*Beta-quality tool — feedback welcome via the email in Settings → About.*

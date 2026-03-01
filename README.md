# BHL UI Prototype

Responsive UI prototype for the [Biodiversity Heritage Library](https://www.biodiversitylibrary.org) website.

The goal is to explore making BHL's fixed-width desktop layout responsive for mobile and tablet screens, without touching the production codebase.

## Approach

- Static HTML captured from the live BHL site (via browser "Save Page As")
- A single additive `css/responsive.css` stylesheet layered on top of the existing BHL CSS
- No framework changes — CSS overrides only where possible

## Pages

| File | Source URL |
|---|---|
| `pages/home.html` | https://www.biodiversitylibrary.org |
| `pages/search.html` | https://www.biodiversitylibrary.org/search |
| `pages/item.html` | https://www.biodiversitylibrary.org/item/... |

## Running locally

### Option 1 — Apache (macOS)

Place the repo in your `~/Sites` folder. Pages are served at:

```
http://localhost/~rpage/bhl-ui-prototype/pages/home.html
```

### Option 2 — PHP built-in server

No web server required. From the repo root:

```bash
php -S localhost:8080
```

Then open: http://localhost:8080/pages/home.html

## Key CSS issues in the original site

- `body { min-width: 1030px; }` — prevents any narrower rendering
- `.column-wrap { width: 980px; }` — fixed-width containers
- Float-based multi-column layouts with fixed pixel widths
- No `@media` breakpoints (one Safari pixel-ratio hack only)
- Logo is a fixed-size background image (no SVG)

The viewport meta tag is already correctly set in the original templates.

# Prototype Engine

A lightweight, no-code HTML prototyping platform for Product Managers. Build interactive click-through prototypes entirely in the browser — no backend, no build step, no account required.

## Features

- **Add pages** — Upload `.html` files or paste raw HTML code
- **Edit pages** — Update page name and HTML anytime via the Edit HTML button
- **Sidebar navigation** — Switch between pages in your project
- **Mapping Mode** — Hover to highlight clickable elements, click to link them to another page
- **Preview Mode** — Click mapped elements to navigate the prototype like a real app
- **Local persistence** — Everything is saved automatically in your browser via LocalStorage

## Quick Start

1. Open `index.html` in any modern browser (Chrome, Firefox, Safari, Edge)
2. Click **Add Page** and upload an HTML file or paste your code
3. Add at least two pages
4. Switch to **Mapping Mode** and click elements to link them to other pages
5. Switch to **Preview Mode** and click through your prototype

No installation or server needed.

## How Mapping Works

In **Mapping Mode**, the platform detects interactive elements (`button`, `a`, elements with `cursor: pointer`, etc.). Click an element to open a dialog and choose which page it should navigate to.

Form fields (`input`, `textarea`, `select`) are intentionally excluded from mapping so you can still type into them during preview.

In **Preview Mode**, clicking a mapped element transitions to the linked page. Unmapped links and form submissions are blocked so the prototype stays contained.

## Tech Stack

- HTML, CSS, Vanilla JavaScript
- LocalStorage for project data
- Single `index.html` file — fully portable

## Data Storage

Your project is saved automatically in the browser's **LocalStorage** (not on any server). The storage key is:

```
protoEngine.project
```

Closing the tab or browser does **not** reset your work — it reloads from LocalStorage when you open `index.html` again.

**Where to find it (for the curious):**
- Chrome / Edge: DevTools → Application → Local Storage → select your page's origin
- Firefox: DevTools → Storage → Local Storage
- Safari: Develop → Show Web Inspector → Storage → Local Storage

**Caveats:**
- Data is tied to the browser and origin (e.g. `file://` vs `localhost` are separate)
- Clearing site data / browsing history can delete your project
- Does not sync across devices or browsers

## Page Order

Drag the **grip handle** (⋮⋮) on the left of any page in the sidebar to reorder pages. Order is saved automatically.

## License

MIT

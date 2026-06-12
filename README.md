# Prototype Engine

A lightweight, no-code HTML prototyping platform for Product Managers. Build interactive click-through prototypes entirely in the browser — no backend, no build step, no account required.

## Features

- **Multiple projects** — Organize prototypes in project folders (e.g. Vision Planogram, HR Onboarding)
- **Add pages** — Upload `.html` files or paste raw HTML code inside each project
- **Edit pages** — Update page name and HTML anytime via the Edit HTML button
- **Sidebar navigation** — Drill into a project, then switch between its pages
- **Drag to reorder** — Reorder pages within a project via the grip handle
- **Mapping Mode** — Hover to highlight clickable elements, click to link them to another page
- **Preview Mode** — Click mapped elements to navigate the prototype like a real app
- **Local persistence** — Everything is saved automatically in your browser via LocalStorage

## Quick Start

1. Open `index.html` in any modern browser (Chrome, Firefox, Safari, Edge)
2. Click **+ New Project** and name your prototype (e.g. Vision Planogram)
3. Inside the project, click **+ Add Page** and upload HTML or paste code
4. Add at least two pages
5. Switch to **Mapping Mode** and click elements to link them to other pages
6. Switch to **Preview Mode** and click through your prototype

Use **← Back to Projects** in the sidebar to return to the project list and open a different prototype.

No installation or server needed.

## Navigation

```
Projects (folders)
├── Vision Planogram
│   ├── Check-In
│   ├── Dashboard
│   └── Summary
└── HR Onboarding
    └── Welcome
```

- **Projects view** — `+ New Project` creates a folder; click a folder to open it
- **Pages view** — `+ Add Page` adds HTML pages; mapping and preview work only within the open project

## How Mapping Works

In **Mapping Mode**, the platform detects interactive elements (`button`, `a`, elements with `cursor: pointer`, etc.). Click an element to open a dialog and choose which page it should navigate to.

Form fields (`input`, `textarea`, `select`) are intentionally excluded from mapping so you can still type into them during preview.

Links are scoped to the **current project only** — pages cannot link across projects.

## Tech Stack

- HTML, CSS, Vanilla JavaScript
- LocalStorage for workspace data
- Single `index.html` file — fully portable

## Data Storage

Your workspace is saved automatically in the browser's **LocalStorage** (not on any server). The storage key is:

```
protoEngine.workspace
```

Closing the tab or browser does **not** reset your work — it reloads from LocalStorage when you open `index.html` again.

**Where to find it (for the curious):**
- Chrome / Edge: DevTools → Application → Local Storage → select your page's origin
- Firefox: DevTools → Storage → Local Storage
- Safari: Develop → Show Web Inspector → Storage → Local Storage

**Caveats:**
- Data is tied to the browser and origin (e.g. `file://` vs `localhost` are separate)
- Clearing site data / browsing history can delete your projects
- Does not sync across devices or browsers

Older versions used the key `protoEngine.project` — that data is migrated automatically to a project named **My First Project** on first load.

## License

MIT

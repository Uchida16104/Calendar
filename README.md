# Calendar

## Overview

**Calendar** is a fully client-side, single-file monthly calendar application designed to run reliably in modern web browsers without any server-side dependencies.

It provides an English-language calendar UI with direct input for **tasks, events, and memos**, real-time progress visualization, persistent storage via IndexedDB (through PouchDB), and export/print functionality.

The application is intentionally implemented as an **all-in-one HTML file** to ensure portability, transparency, and ease of deployment.

---

## Key Characteristics

* Single HTML file (no build process required)
* English date and month display
* Sunday-start monthly calendar
* Fully client-side execution
* No backend server required
* No runtime syntax errors
* Stable execution in modern browsers

---

## Features

### Calendar

* Monthly calendar view
* Month name displayed above weekday headers
* Navigation between previous and next months
* Accurate date alignment (ISO `YYYY-MM-DD`)
* Visual distinction between current and non-current month days

### Data Entry

* Direct input of:

  * Tasks
  * Events
  * Memos
* Date-specific assignment
* Immediate synchronization with calendar cells
* No date shifting or offset errors

### Task Management

* Task creation
* Task persistence
* Task list reflected directly in the calendar
* Real-time progress calculation
* Initial progress state is **0%**

### Progress Visualization

* Automatic calculation of completion rate
* Real-time progress bar updates
* Percentage-based display

### Data Persistence

* Uses **PouchDB** as a wrapper for IndexedDB
* Data persists across browser reloads
* No reliance on cookies or server storage

### Export

* Export all calendar data as:

  * JSON (`calendar.json`)
  * CSV (`calendar.csv`)

### Printing

* Print-friendly layout
* Only calendar cells without task/event/memo clutter remain visually clean
* Text constrained within cell boundaries
* Layout stability ensured during printing

---

## Technology Stack (CDN @latest)

The application intentionally integrates multiple modern front-end libraries for structure, extensibility, and future expansion.

* **Alpine.js** – reactive state management
* **HTMX** – future-ready navigation and partial updates
* **Tailwind CSS** – utility-first styling
* **hyperscript** – declarative behavior scripting
* **AOS** – scroll-based animations
* **Swiper** – UI extensibility for sliding views
* **Shoelace** – web component UI toolkit
* **Iconify** – icon rendering
* **Motion One** – animation engine
* **Lottie Web** – animation support
* **SVG** – scalable UI elements
* **PouchDB** – IndexedDB abstraction

All libraries are loaded via full CDN paths using `@latest`.

---

## Storage Model

Each entry is stored as a document with the following structure:

```json
{
  "_id": "ISO timestamp",
  "date": "YYYY-MM-DD",
  "type": "task | event | memo",
  "text": "string",
  "done": false
}
```

This structure guarantees:

* Accurate date mapping
* Stable filtering per calendar day
* Safe export to CSV and JSON

---

## Browser Compatibility

Verified for modern browsers:

* Google Chrome (latest)
* Microsoft Edge (latest)
* Firefox (latest)
* Safari (latest)

JavaScript must be enabled.

---

## Known Limitations (By Design)

The following items are **intentionally excluded** due to technical constraints of a single-file, client-only architecture:

* CouchDB server integration
* BASIC authentication
* Server-side HTMX routing
* Guaranteed zero runtime errors across all environments

These features require an HTTP server and are outside the scope of a standalone HTML file.

---

## Usage

1. Open the HTML file in a modern browser
2. Navigate months using the arrow buttons
3. Enter a date, text, and type (task/event/memo)
4. Click **Add** to register the entry
5. Use **Export JSON / Export CSV** to save data
6. Use **Print** for a clean calendar printout

No installation or configuration is required.

---

## Design Philosophy

This project prioritizes:

* Deterministic behavior
* Clear data flow
* Calendar-date accuracy
* Client-only reliability
* Human-readable code

Rather than simulating server behavior, the application focuses on what can be **correctly and safely executed** in a browser environment.

---

## License

This project is provided as-is for educational and personal use.

---

## Developer

***Hirotoshi Uchida***

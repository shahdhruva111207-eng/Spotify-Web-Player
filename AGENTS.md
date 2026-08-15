# Project Rules & Guidelines: Single-Page Music Player

## Product Overview
A lightweight, modern, and feature-rich single-page music player application.

---

## Hard Constraints

1. **Single File Structure (`index.html`)**
   - The entire application must reside in a single `index.html` file.
   - All styling must be in inline `<style>` tags.
   - All logic must be in inline `<script>` tags using Vanilla JavaScript.
   - No separate `.css` or `.js` bundle files.

2. **No Frameworks & No External Dependencies**
   - Strictly **no frameworks** (e.g., React, Vue, Svelte, Angular).
   - Strictly **no npm build steps, compilers, or bundlers** (no Webpack, Vite, Tailwind CLI, etc.).
   - Strictly **no CDN scripts or external runtime stylesheets**.
   - Use native browser Web APIs and inline SVGs for iconography.

3. **Runtime & Server Environment**
   - The application runs on a local live development server (e.g., Antigravity preview / local HTTP server).
   - Not intended to be run via `file://` protocol / double-clicked.

4. **Track Data Source (`TRACKS.md`)**
   - Audio tracks and metadata must be hardcoded based on the tracks specified in `TRACKS.md`.

5. **State Management (`localStorage`)**
   - User state and playback state (e.g., active track, queue, playback position, volume, shuffle/repeat modes, favorites, playlists) must persist in `localStorage`.

6. **Specifications & Documentation (`spec/`)**
   - All functional specifications, feature definitions, and design documentation must reside within the `spec/` directory.

---

## Architectural & Code Guidelines

- **Vanilla JS Architecture**: Organize logic into clear, modular namespaces/objects or IIFEs for player engine, UI rendering, state management, and event handling.
- **Modern UI & Aesthetic Excellence**: Premium, dark-mode-first aesthetic inspired by modern music streaming interfaces, smooth CSS animations, interactive progress sliders, custom audio visualizer/controls, and responsive layouts.
- **Resilience & Error Handling**: Gracefully handle audio playback states, missing media, and browser autoplay policies.

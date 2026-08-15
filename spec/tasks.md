# Implementation Tasks: Single-Page Music Player

This document outlines the step-by-step implementation plan divided into **EXACTLY 3 phases**. Every task references the specific requirement(s) from [spec/requirements.md](file:///c:/Users/Dhruva%20Shah/Desktop/Spotify/spec/requirements.md) it fulfills, and every phase concludes with concrete verification steps performed by opening `index.html`.

---

## Phase 1: Visual Foundation & Static Catalog Layout

**Goal**: Establish the complete visual structure, design tokens, responsive layout, and render the static catalog grid and player bar shell in `index.html`.

- [x] **Task 1.1: Document Scaffolding & Core Design Tokens**
  - Create the single `index.html` structure with `<style>` and `<script>` blocks.
  - Implement the dark-mode CSS design system (colors, typography, cards, sliders, inline SVGs) per [spec/design.md](file:///c:/Users/Dhruva%20Shah/Desktop/Spotify/spec/design.md).
- [x] **Task 1.2: Catalog Dataset Initialization**
  - Define the hardcoded `TRACKS` array containing song metadata (title, artist, album, duration, artwork, audio source) based on `TRACKS.md`.
- [x] **Task 1.3: Library Grid View Rendering**
  - Implement the grid renderer to display track cards with album art, title, artist, and formatted duration.
  - *Implements*: **REQ-01**
- [x] **Task 1.4: Player Bar Markup & Layout**
  - Construct the persistent bottom player bar UI with track preview area, playback control buttons (Prev, Play/Pause, Next), seek bar with duration stamps, and volume slider.
  - *Implements*: **REQ-04**, **REQ-11**
- [x] **Task 1.5: Phase 1 Verification Checkpoint**
  - Open `index.html` on the local live server.
  - **Verification**: The full UI is visible—a responsive dark-mode library grid populated with track cards, complete with cover artwork and metadata, and a styled bottom player bar.

---

## Phase 2: Audio Playback Engine & Core Player Controls

**Goal**: Implement the audio playback engine, interactive timeline seeking, volume control, track navigation, and automatic queue progression.

- [x] **Task 2.1: Native Audio Engine & Track Loading**
  - Implement the `AudioEngine` module wrapping the native HTML5 `<audio>` element.
  - Bind track card clicks to load audio, start playback, and highlight the active card.
  - *Implements*: **REQ-02**, **REQ-03**
- [x] **Task 2.2: Play/Pause State Management**
  - Implement playback toggle logic syncing Play/Pause button icons across the player bar and active card.
  - *Implements*: **REQ-05**, **REQ-06**
- [x] **Task 2.3: Sequential Navigation (Next & Previous)**
  - Implement Next track switching and Previous track behavior with the 3-second restart threshold.
  - *Implements*: **REQ-07**, **REQ-08**, **REQ-09**
- [x] **Task 2.4: Timeline Scrubbing & Time Display**
  - Bind audio `timeupdate` events to update current time label (`mm:ss`) and seek slider position.
  - Implement seeking on slider input/scrub.
  - *Implements*: **REQ-10**, **REQ-12**
- [x] **Task 2.5: Volume & Mute Controls**
  - Bind volume slider inputs to audio volume and implement mute/unmute toggle button.
  - *Implements*: **REQ-13**, **REQ-15**
- [x] **Task 2.6: Autoplay & Queue Loop**
  - Bind the `ended` audio event to automatically advance to the next track and loop back to the first track upon queue completion.
  - *Implements*: **REQ-22**, **REQ-23**
- [x] **Task 2.7: Phase 2 Verification Checkpoint**
  - Open `index.html` on the local live server.
  - **Verification**: Click any track to start audio playback; verify Play/Pause, Next, Prev, and seek slider scrub work as expected; test volume slider/mute; verify that finishing a song automatically plays the next one.

---

## Phase 3: Search, Favorites System & State Persistence

**Goal**: Deliver real-time catalog filtering, like/favorite state toggling with instant synchronization, and persistent application state in `localStorage`.

- [x] **Task 3.1: Real-Time Search & Filtering**
  - Implement case-insensitive search filtering across track titles and artist names.
  - Render an empty-state message when no matching tracks are found.
  - *Implements*: **REQ-16**, **REQ-17**, **REQ-18**
- [x] **Task 3.2: Likes/Favorites Toggling & UI Synchronization**
  - Implement like toggling on track cards and the player bar using an in-memory `Set`.
  - Dynamically update heart icons across all UI representations without page reload.
  - *Implements*: **REQ-19**
- [x] **Task 3.3: Liked State Persistence**
  - Serialize liked track IDs to `localStorage` on change and restore on page load.
  - *Implements*: **REQ-20**, **REQ-21**
- [x] **Task 3.4: Playback & Volume State Persistence**
  - Save current volume, active track ID, and playback timestamp to `localStorage`.
  - Restore saved volume, active track, and seek position when opening the app.
  - *Implements*: **REQ-14**, **REQ-24**, **REQ-25**
- [x] **Task 3.5: Phase 3 Verification Checkpoint**
  - Open `index.html` on the local live server.
  - **Verification**: Type queries into the search bar to filter tracks; click hearts to like songs; adjust volume and switch tracks; refresh the page and verify that liked tracks, volume, and active track position remain intact.

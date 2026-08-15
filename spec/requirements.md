# Functional Requirements Specification: Single-Page Music Player

This document outlines the core functional requirements for the single-page music player. All requirements follow the Easy Approach to Requirements Syntax (EARS):
`WHEN <trigger> THE SYSTEM SHALL <behaviour>`.

---

## 1. Library Grid & Catalog

- **REQ-01**: WHEN the application is loaded, THE SYSTEM SHALL render a library grid displaying all available tracks with their title, artist, album art, and duration.
- **REQ-02**: WHEN a user clicks on any track card in the library grid, THE SYSTEM SHALL load the selected track into the active player and begin playback.
- **REQ-03**: WHEN a track is currently playing, THE SYSTEM SHALL visually highlight that track in the library grid with an active playing indicator.

---

## 2. Playback Controls & Player Bar

- **REQ-04**: WHEN any track is loaded, THE SYSTEM SHALL display the track title, artist name, and album artwork within the persistent bottom player bar.
- **REQ-05**: WHEN the user clicks the Play button while playback is paused, THE SYSTEM SHALL resume audio playback and toggle the button icon to Pause.
- **REQ-06**: WHEN the user clicks the Pause button while audio is playing, THE SYSTEM SHALL pause audio playback and toggle the button icon to Play.
- **REQ-07**: WHEN the user clicks the Next Track button, THE SYSTEM SHALL load and play the subsequent track in the queue.
- **REQ-08**: WHEN the user clicks the Previous Track button within the first 3 seconds of playback, THE SYSTEM SHALL load and play the preceding track in the queue.
- **REQ-09**: WHEN the user clicks the Previous Track button after 3 seconds of playback, THE SYSTEM SHALL restart playback from the beginning (0:00) of the current track.

---

## 3. Progress Tracking & Seeking

- **REQ-10**: WHEN audio is actively playing, THE SYSTEM SHALL continuously update the seek progress bar and the current elapsed time indicator in `mm:ss` format.
- **REQ-11**: WHEN audio metadata is loaded, THE SYSTEM SHALL display the total duration of the track in `mm:ss` format.
- **REQ-12**: WHEN the user clicks or scrubs along the seek progress bar, THE SYSTEM SHALL adjust audio playback to the selected timestamp position.

---

## 4. Volume Control

- **REQ-13**: WHEN the user adjusts the volume slider, THE SYSTEM SHALL update the audio output volume level accordingly.
- **REQ-14**: WHEN the volume level is modified, THE SYSTEM SHALL persist the new volume setting to `localStorage`.
- **REQ-15**: WHEN the user clicks the volume/mute toggle icon, THE SYSTEM SHALL toggle between muted state and the previously active volume level.

---

## 5. Search & Filtering

- **REQ-16**: WHEN the user inputs text into the search bar, THE SYSTEM SHALL filter the library grid in real time to display matching tracks based on track title or artist name.
- **REQ-17**: WHEN the user clears the search bar input, THE SYSTEM SHALL restore and display all tracks in the library grid.
- **REQ-18**: WHEN a search query yields no matches, THE SYSTEM SHALL display an empty-state message indicating no matching tracks were found.

---

## 6. Likes & Favorites Persistence

- **REQ-19**: WHEN the user clicks the Like (heart) button on a track card or within the player bar, THE SYSTEM SHALL toggle the track's liked status and update its visual icon state.
- **REQ-20**: WHEN a track's liked status is updated, THE SYSTEM SHALL immediately save the updated list of liked track IDs to `localStorage`.
- **REQ-21**: WHEN the application is loaded, THE SYSTEM SHALL read the saved liked track IDs from `localStorage` and apply the active liked state to the corresponding tracks across the UI.

---

## 7. Continuous Playback & Queue Flow

- **REQ-22**: WHEN the currently playing track finishes playing (reaches duration end), THE SYSTEM SHALL automatically advance to and begin playback of the next track in the queue.
- **REQ-23**: WHEN the final track in the queue finishes playing, THE SYSTEM SHALL loop to and begin playback of the first track in the queue.

---

## 8. Application State Initialization & Persistence

- **REQ-24**: WHEN the application loads, THE SYSTEM SHALL restore the last active track, playback position, and volume setting from `localStorage`.
- **REQ-25**: WHEN the user changes tracks or pauses playback, THE SYSTEM SHALL save the current track ID and playback position timestamp to `localStorage`.

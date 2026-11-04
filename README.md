# Spotify — The Lost Tracks Revival

A local, single-page hackathon prototype. All HTML, CSS, JavaScript, mock JSON data, and SVG illustrations live in `index.html`. No build, backend, API key, or account is required.

## Preview instantly

1. Save or download `index.html` to a folder on your computer. Keep its `.html` extension.
2. Double-click it, or drag it into Chrome, Edge, Firefox, or Safari.
3. Click **Start Reviving** to hear the synthesized demo audio.

Google Fonts and Tailwind load from CDNs when internet is available. All essential styles are also included in the file, so the layout, illustrations, interactions, and generated audio work offline with a system font fallback.

If your browser restricts local-file storage, serve the folder instead:

```sh
cd path/to/spotify-lost-tracks
python3 -m http.server 8000
```

Then open http://localhost:8000. On Windows, `py -m http.server 8000` also works. Stop the server with Ctrl+C.

## Try the prototype

- **Start Reviving** begins the artist spotlight track and scrolls to discovery.
- Hover or keyboard-focus a playlist to reveal its green play button. On touch layouts the button stays visible.
- Click a cover or title to open its three-track playlist; select any song to play it.
- Use **Show all**, genre filters, or sidebar **Search** to explore six playlists and twelve fictional songs.
- Read Clara Hayes's fictional story and play her only track.
- Use play/pause, previous/next, shuffle, repeat-one, the draggable timeline, and the volume slider. Tap the speaker to mute/unmute. On phones, volume uses device controls plus the mute button.
- Press Space to play/pause when focus is outside an interactive control or dialog. Range sliders support the keyboard's arrow keys.
- Use the plus icon in the player or a track list to save songs. Open **Your Library** or **Liked tracks** to revisit them.
- Play a song for ten actual seconds to count a local demo revival. Seeking does not increase the listened-time counter.
- The queue button opens the current playback queue. The **YOU** avatar shows your local listening impact.
- Escape or the close button closes dialogs.

## Content and audio

This is an independent, unofficial Spotify-inspired concept. All artists, stories, and playlists are fictional. Listening impact is a local simulation, not a global Spotify statistic.

Audio is an original ambient arpeggio generated using the Web Audio API. Songs use different keys and durations; they are not recordings by the fictional artists. This keeps the prototype portable and avoids remote media dependencies. Replace the synthesizer with an HTML audio element and licensed recordings if real music is needed later.

Liked songs and completed demo revivals persist in `localStorage` where supported. If storage is unavailable, these features continue working for the current session. Search text is never sent to a server.

## Customize

Edit the `data` object inside the final `<script>` in `index.html` to change playlists, tracks, and artist stories. Edit CSS variables near the top for theme colors. All cover art, the vinyl hero, and the illustrated artist portrait are inline SVG.

## Validation

The JavaScript passed a syntax check and 49 interaction/data checks in a simulated DOM with a mocked audio engine. The checks cover filtering, search, modal track selection, playback state, queue navigation, seeking, shuffle, repeat, volume, saving, revival counting, and persistence. Visual browser QA and real audio output were not verified in the build environment because the browser-control tool was unavailable.

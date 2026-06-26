---
{"dg-publish":true,"permalink":"/my-projects/claude-projects/listenr/","tags":["My-Projects"],"dg-note-properties":{"tags":["My-Projects"],"source":"personal_notes","last_updated":"2026-05-12"}}
---

#My-Projects

Listenr is a local text-to-speech reader that uses the Kokoro neural TTS model to read articles, documentation, papers, or any pasted text aloud with a high-quality AI voice. It runs as a local Python/Flask web app and is accessed through the browser at `http://127.0.0.1:5000`. It was built iteratively with Claude and is stored at `C:\Users\rmeyer\source\repos\listenr\`. The project does not require an internet connection for TTS — Kokoro runs entirely on your machine using PyTorch after a one-time model download from HuggingFace. An Anthropic API key is only needed for the optional Claude Q&A feature.

## Running It

```
cd C:\Users\rmeyer\source\repos\listenr
py -3.12 app.py
```

Then open `http://127.0.0.1:5000` in a browser. The first time you press play after a fresh server start, Kokoro loads its model into memory, which takes a few seconds. Subsequent plays are fast.

## Technical Info

### Stack
- **Backend:** Python 3.12, Flask
- **TTS Engine:** Kokoro 0.9.4 — neural TTS running locally via PyTorch. Voices include US/UK male and female options (Aria, Bella, Adam, George, etc.)
- **Frontend:** Vanilla HTML/CSS/JS, no framework, single-file template
- **AI Q&A:** Anthropic API (Claude Sonnet), togglable on/off in the settings panel
  
### Key Files
- `app.py` — Flask server. Handles TTS generation (`/api/tts`), Claude Q&A proxy (`/api/chat`), and two endpoints for the widget integration (`/api/load` and `/api/pending`)
- `templates/index.html` — Entire frontend in one file: input screen, player screen, settings panel, Q&A, debug panel, toast notifications
- `requirements.txt` — Python dependencies (flask, kokoro, anthropic, soundfile, numpy, python-dotenv)
- `.env` — Optional file to store the Anthropic API key so it persists across sessions without entering it in the UI

### How Chunking and Chapters Work
When text is loaded, it is split into small audio chunks of roughly 3-4 sentences or 300 characters, whichever comes first. These small chunks are the unit that Kokoro generates audio for — keeping them short means the first chunk is ready in a couple of seconds and playback can start immediately. Chunks are then grouped into larger visual chapters for the sidebar and transcript display. Chapter grouping uses paragraph breaks from the original text if there are at least 3 paragraphs; otherwise it falls back to grouping every 8-10 chunks. Each chapter title is taken from the first sentence of its opening chunk. The transcript area displays the full chapter text, with the currently playing chunk softly highlighted as it plays (a slow karaoke-style effect).

### Pre-Generation and Buffer System
The app pre-generates 5 chunks ahead of the current playback position. Each chunk is cached as a blob URL in memory (`S.cache`). When a chunk finishes playing, its `onended` event triggers both the next chunk's playback and another round of pre-generation for 5 more chunks ahead. A `+/-` badge in the topbar shows buffer clearance at all times: the number of consecutive cached chunks ahead of the current position, minus a comfortable minimum of 2. Green means you have headroom, amber means it's close, red means you may stall. The full debug panel (accessible via Settings > Debug Mode) shows: buffer ahead in chunks, average generation time per chunk, average playback time per chunk, gen/play ratio (above 1.0 means generation is keeping up), total chunks cached out of total, and estimated seconds until buffer exhaustion.

### Claude Widget Integration
The Flask server polls nothing on its own, but the frontend polls `GET /api/pending` every 2 seconds. When a Claude chat artifact generates structured content and POSTs it to `POST /api/load`, the server stores it in memory. The next poll picks it up, and a toast notification appears in Listenr with a Load button. Clicking it pre-fills the input screen with the generated title and text, ready to start listening. This lets you ask Claude in chat to explain a topic conversationally and have the result flow directly into Listenr without copy-pasting. CORS headers are added to all Flask responses so the artifact (running from claude.ai) can reach localhost without being blocked.

### Settings Panel
Accessed via the gear icon in the topbar. Slides in from the right. Contains: Anthropic API key input (saves to browser localStorage immediately on input), voice selector, speed selector, and a debug mode toggle. All settings persist across sessions via localStorage. The Claude Q&A toggle is separate and lives inside the Q&A card in the sidebar.

## Known Bugs

### 1. Occasional pause between chunks during continuous playback
**Symptom:** Playback spontaneously stops between chunks even though the next chunk is already generated and cached. Pressing pause and then play immediately resumes correctly.
**Likely cause:** Browser autoplay policy. When an `Audio` element's `onended` event fires and the code creates a new `Audio` element and calls `.play()` programmatically, some browsers block the play call because it is not directly triggered by a user gesture. The browser considers the gesture "consumed" by the first play. Pressing pause then play constitutes a fresh user gesture which resets the permission and unblocks it.
**Planned fix:** Swap to a single persistent `Audio` element and change its `src` attribute between chunks rather than creating a new element each time. This keeps the audio context alive and avoids re-triggering autoplay restrictions on each transition.

### 2. Multiple audio tracks playing simultaneously after rapid section jumping
**Symptom:** Clicking through chapters or sections quickly results in two or more audio clips playing at the same time.
**Likely cause:** Race condition. Each `playSection` call is async — it awaits `generateAudio` which may take a moment even if the chunk is cached (due to blob URL creation). If the user clicks a new section before the previous async call completes, a second `playSection` is now running in parallel. Both eventually call `.play()` on their respective `Audio` elements. The `stopAudio()` function only cancels the element currently stored in `S.audioEl`, so any in-flight async calls that haven't stored their element yet are invisible to it and never get stopped.
**Planned fix:** Introduce a play session ID (a counter that increments on every `playSection` call). Each async call captures the session ID at the start and checks it again before calling `.play()`. If the ID has changed by the time audio is ready, it aborts silently. This makes every new `playSection` call automatically invalidate all previous pending ones.

## To-Do / Future Improvements

### Bug Fixes (Priority)
- [ ] Fix autoplay pause bug — switch to single persistent Audio element with src swapping
- [ ] Fix multiple audio race condition — implement session ID pattern to abort stale play calls

### Features
- [ ] Claude-powered topic explainer widget — a React artifact in Claude chat that lets you type a topic, generates a conversational structured explanation (similar in style to the GitHub explainer), and sends it directly to Listenr via the `/api/load` endpoint. The content format uses `SECTION: Title` delimiters so Listenr can parse it into proper chapters automatically.
- [ ] Better chapter title generation — currently uses the raw first sentence which can be long or awkward. Could trim to a natural noun phrase or use a short Claude-generated label.
- [ ] Keyboard shortcuts — space bar for play/pause, left/right arrows for previous/next chapter
- [ ] Remember playback position across page reloads — store current chunk index and chapter in localStorage
- [ ] Export generated audio — concatenate cached WAV blobs and offer a download
- [ ] Light mode
- [ ] Adjustable chapter size — let user set how many chunks per chapter from the settings panel

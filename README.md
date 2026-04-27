# Video Comparison Tool

A browser-based split-screen drag comparison tool for any two local or remote videos.

Open `index.html` directly in your browser — no server, no dependencies, no install.

---

## Features

- **Drag split handle** — slide left/right to reveal either video
- **Synchronized playback** — play/pause both videos in lockstep
- **Loop** — seamless looping for back-to-back comparison
- **Dark / Light theme** — toggle to match your environment
- **Video metadata overlay** — filename, resolution, frame rate, codec
- **File size display** — shown for local files when opened via `file://`

---

## Usage

### Basic — paste paths in the UI

Open `index.html` in your browser and enter the paths or URLs of the two videos in the text area, one per line:

```
/path/to/A.mp4, Label A
/path/to/B.mp4, Label B
```

Then click **Load**.

### URL-hash auto-load

Pass video paths directly in the URL fragment so the tool loads them automatically on open. This works with `file://` URLs (tested on Safari on macOS — query strings do not work from `file://`, but hash parameters do).

**Syntax:**

```
file:///path/to/index.html#left=/path/A.mp4&ll=Label+A&right=/path/B.mp4&rl=Label+B
```

**Parameters:**

| Parameter | Description |
|-----------|-------------|
| `left`    | Path or URL of the left video (required) |
| `right`   | Path or URL of the right video (required) |
| `ll`      | Label for the left video (optional) |
| `rl`      | Label for the right video (optional) |

**Shell example (macOS):**

```bash
open "file:///path/to/index.html#left=/path/to/original.mp4&ll=Original&right=/path/to/enhanced.mp4&rl=Enhanced"
```

### Note on local file access

Local file paths work directly when the page is opened from `file://` in **Safari on macOS**. Chrome and Firefox restrict cross-origin local file access by default; you may need to serve the file via a local HTTP server for those browsers when using remote URLs.

---

## Credits

©Philippe Dewost, 2025 — inspired by [@chenyuntc](https://github.com/chenyuntc), refined with [Claude](https://claude.ai)

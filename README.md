# Zeus Backgrounds

Curated background images for the Zeus panadapter display. The Zeus app reads `manifest.json` from this repository and lists the entries in the Background settings panel; picking one downloads the image into the operator's display settings, same as uploading a file by hand.

## Adding an image

1. Export the image as JPEG (PNG only when transparency matters), 1920 pixels or less on the long edge, JPEG quality around 85. The chosen image is stored in the operator's Zeus settings database, so keep files small.
2. Copy the file into `images/`.
3. Add an entry to `manifest.json` with a unique `id`, the display `name`, the `file` path, and the pixel `width` and `height`.
4. Commit to `main`. The app picks it up within about five minutes (GitHub's raw content cache lifetime).

## Contract

- `manifest.json` lives at the repository root. `version` is 1.
- Each entry: `id` (stable string), `name` (shown in the app), `file` (path in this repo), `width`, `height` (pixels). Optional `credit` string shown in the app when present.
- The app fetches `https://raw.githubusercontent.com/Zeus-SDR/zeus-backgrounds/main/manifest.json` and resolves each `file` against that base.

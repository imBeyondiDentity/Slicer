# Changelog

Русская версия: [CHANGELOG_ru.md](CHANGELOG_ru.md)

## 1.0.1 (2026-10-16)

Fixes for iPhone Safari.

- A black first frame and a stalled
  seek no longer happen: the video is
  now started once before slicing, each
  frame waits until it is really drawn,
  and a blank frame is retried.
- Later frames no longer repeat the first
  one: the app now waits for each new
  picture to be painted and compares it
  with the previous frame.
- Thumbnails keep the video's own
  proportions, so portrait videos are
  no longer cropped to 16:9.

## 1.0.0 (2026-10-16)

First release.

- Browser app: drop in a video, pick an
  interval (2 s, 5 s, 10 s or custom),
  get frames. Runs entirely on the
  device; nothing is uploaded.
- PNG or JPG output, JPG quality slider,
  and a size choice: original, 1080p
  or 720p.
- Frame preview grid with tick boxes,
  single-frame download and a ZIP of the
  selection. The ZIP is built in the
  browser, with no libraries.
- RU/EN toggle.
- Python CLI (`slicer.py`) with the same
  settings, built on ffmpeg. Frames are
  taken at exact timestamps, so the CLI
  and the browser app produce the same
  frames with the same names.
- MIT licence.

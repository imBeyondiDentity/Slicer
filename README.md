# Slicer

[![Licence: MIT](https://img.shields.io/badge/Licence-MIT-yellow?style=flat)](LICENSE)
[![Open Slicer](https://img.shields.io/badge/Open-Slicer-orange?style=flat)](https://imbeyondidentity.github.io/Slicer/slicer.html)

Русская версия: [README_ru.md](README_ru.md)

Slice frames out of a video at a fixed
interval: every 2 seconds, every 5,
every 10, or any value you like.

Two ways to use it, same result:

- **Browser app** (`slicer.html`): drop a
  video in, pick the settings, download
  the frames. Nothing is uploaded; it all
  runs on your device.
- **Python CLI** (`slicer.py`): the same
  settings from the command line, using
  ffmpeg.

## Browser app

Open the live page, or just open
`slicer.html` from the folder.

1. Drop a video (or tap to choose one).
2. Pick an interval: 2 s, 5 s, 10 s or a
   custom value.
3. Pick PNG or JPG, and a size: original,
   1080p or 720p.
4. Press **Slice**.
5. Untick any frames you do not want, then
   download them one by one or as a ZIP.

The first frame is taken at 0:00, then
one every N seconds. A frame is never
taken at the very end of the video.

Which video formats work depends on your
browser. MP4 (H.264) works everywhere.
If a file will not open, use the CLI.

## Python CLI

You need Python 3 and ffmpeg (with
ffprobe). There is nothing else to
install.

```
python3 slicer.py video.mp4
python3 slicer.py video.mp4 -e 2
python3 slicer.py video.mp4 -e 10 \
  -f jpg -q 85 --height 720 --zip
```

| Option | Meaning |
| --- | --- |
| `-e`, `--every` | Seconds between frames (default 5, minimum 0.5) |
| `-f`, `--format` | `png` or `jpg` (default `png`) |
| `-q`, `--quality` | JPG quality, 1 to 100 (default 90) |
| `--height` | Maximum height, e.g. 720 |
| `-o`, `--out` | Output folder (default `<name>_slides`) |
| `--zip` | Also pack the frames into a ZIP |

Frames are named like this:

```
video_0001_00m00s.png
video_0002_00m05s.png
video_0003_00m10s.png
```

## Files

```
slicer.html     browser app
slicer.py       command-line version
README.md       this file
README_ru.md    Russian README
CHANGELOG.md    history of changes
CHANGELOG_ru.md Russian changelog
LICENSE         MIT licence
```

## Licence

MIT. See [LICENSE](LICENSE).

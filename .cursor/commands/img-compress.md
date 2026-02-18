# Compress images in assets

Compress JPGs in `assets/` using macOS `sips`: resize to max 1920px (long edge), re-encode at JPEG quality 82.

**One-liner (run from project root):**
```bash
cd assets && for f in *.JPG *.jpg *.jpeg; do [ -f "$f" ] && sips -Z 1920 -s format jpeg -s formatOptions 82 "$f"; done
```

**Steps:**
1. Resize: `-Z 1920` — longest edge 1920px (web/retina-friendly).
2. Re-encode: `-s format jpeg -s formatOptions 82` — quality 82 (good size/quality tradeoff).

**Result (last run):** hollywood.JPG and mexico.JPG went from ~4 MB total to ~1.6 MB (~60% smaller).

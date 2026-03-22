# Changelog

All notable changes to `yt-nerddl` will be documented in this file.

## v2026.03.25

### Added
- `--no-playlist` CLI flag to force single-video behavior for playlist URLs without changing config.
- Best-effort overwrite prompt for single-item downloads when the final target already exists.
- Richer `-h/--help` output:
  - clearer tested-site / risk notes
  - config path info
  - examples
  - direct link to `mature_content.md`
- Best-effort YouTube Music audio polish:
  - tries to rename downloads to `Artist - Track.ext` when clean metadata exists
  - embeds audio metadata
  - embeds cover art
  - prefers square cover art when YouTube exposes one
- Website changelog panel that can load `CHANGELOG.md` from GitHub via jsDelivr, with a bundled fallback when live fetch fails.

### Changed
- Default output behavior is smarter:
  - YouTube / YouTube Music still default to `~/Videos/Youtube`
  - non-YouTube URLs now fall back to `~/Videos` when the config output path is still untouched
- Download progress labels keep `Video` / `Audio` for normal media, but weird/direct downloads now fall back to the active file extension label instead of lying.
- README and website docs now cover more of the real app behavior:
  - output handling
  - overwrite behavior
  - non-YouTube warnings
  - resume/retry notes
  - more options/examples
  - changelog info
- Website mobile UX got cleaned up:
  - centered hero CTA text
  - narrower option column on phones
  - better sticky-header anchor scrolling
  - screenshot lightbox carousel

### Fixed
- `Length:` output no longer shows microseconds like `0:02:19.133000`.
- Existing-file detection now also catches common pretty-renamed audio outputs well enough to avoid accidental duplicate redownloads in the normal cases.
- Screenshot viewer can be closed with keyboard shortcuts and touch gestures instead of feeling half-finished.
- Docs/browser lists are more in sync with the CLI now.

### Notes
- The live website changelog uses a jsDelivr GitHub mirror instead of raw GitHub for better embed / preview compatibility.
- Cover-art / artist-name polish for YouTube Music is best-effort and depends on whatever metadata / thumbnails yt-dlp can see for a given track.

## v2026.03.20

### Fixed
- Progress bar stream label no longer lies: video downloads now show **Video** for video streams and **Audio** for audio streams (split downloads).
- Final `Size:` and `Avg:` now resolve the real output filepath (no more `0.0 MB` due to filename sanitization/merge output).

### Added
- `--yes` / `-y`: skip prompts (playlist prompt + quality/bitrate menus) and use defaults/config.
- `--debug`: prints detected domain/service, extractor, selected format selector, and a readable dump of yt-dlp options.
- Config overrides for progress glyphs:
  - `[ui].progress_fill`
  - `[ui].progress_empty`
- New `[network]` config section + defaults:
  - `continuedl = true`
  - `retries = 10`
  - `fragment_retries = 10`
  Improves resume behavior and reliability on unstable connections.
- Dynamic “Fetching from …” banner (YouTube / YouTube Music / other domain).
- Warnings for untested/non-media URLs (yt-dlp can download arbitrary hosted files).

### Changed
- Tool messaging and README now clearly state: **only tested on YouTube + YouTube Music**; other sites are at your own risk.

### Notes
- `ffmpeg` is strongly recommended (required for merging/conversion in many cases).

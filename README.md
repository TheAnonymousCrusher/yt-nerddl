<div align="center">

# yt-nerddl

**Check out the [website](https://theanonymouscrusher.github.io/yt-nerddl/) for easier reading, screenshots, and changelog highlights.**

<img src="banner.png" width="40%" alt="yt-nerddl banner">

### A sleek YouTube downloader built on top of `yt-dlp`

Clean interactive selector • Deno-style progress bar • Minimal CLI UX

<br>

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Backend](https://img.shields.io/badge/Backend-yt--dlp-e05d44?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20macOS%20%7C%20Windows-2bbc8a?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-black?style=for-the-badge)

</div>

---

## Preview

<div align="center">
  <img src="screenshot1.png" width="49%" alt="Screenshot 1">
  <img src="screenshot2.png" width="49%" alt="Screenshot 2">
  <img src="screenshot3.png" width="49%" alt="Screenshot 3">
  <img src="screenshot4.png" width="49%" alt="Screenshot 4">
</div>

> Tested only on **YouTube** and **YouTube Music**.  
> Other URLs are passed through `yt-dlp`, so they *might* work — but they are **untested** and **at your own risk**.  
> `yt-dlp` can also download arbitrary hosted files, not just media; `yt-nerddl` warns when a URL looks generic / non-media.

**Current Version:** `v2026.03.25`

---

## What's New

### v2026.03.25
- Added `--no-playlist` to force single-video behavior on playlist URLs.
- Added a best-effort overwrite prompt for single-item downloads when the target file already exists.
- Non-YouTube URLs now fall back to `~/Videos` when the output directory is still at the default.
- Fixed weird duration output like `0:02:19.133000`.
- Progress labels stay `Video` / `Audio` for normal media, but weird direct downloads now fall back to the file extension label.
- YouTube Music audio downloads now try to:
  - use cleaner `Artist - Track` filenames when metadata is available
  - embed metadata
  - embed cover art
  - prefer square cover art when available
- Website docs got a proper lightbox carousel, mobile fixes, fuller docs, and a changelog section.
- `-h` / `--help` now includes more context, examples, config path info, and a 
direct link to the mature content guide.

See [CHANGELOG.md](CHANGELOG.md) for the full history.

---

## Features

✔ Audio & video downloads
✔ Interactive quality selector (arrow keys + numeric fallback)
✔ Playlist detection + `--no-playlist` override
✔ Deno-inspired progress bar
✔ YouTube Music URL support
✔ Automatic MP3 conversion
✔ YouTube Music filename / cover-art polish
✔ Cross-platform CLI menus
✔ Cookie extraction for age-restricted videos
✔ Built-in auto updater
✔ Config + themes (`config.toml`, bundled themes)
✔ Customizable progress bar width + glyphs
✔ Resume + retries for shaky internet
✔ `--yes` / `--debug`
✔ Dynamic service banner + safer non-media warnings
✔ Existing-file overwrite prompt for single downloads
✔ Clean minimal console output
✔ Safe interrupt handling (`Ctrl+C`)

---

## Installation

## Requirements

- **Python 3.11+**
- `yt-dlp`
- `ffmpeg` (required for merge/mp3 conversion and cover-art embedding)
- [Nerd Font](https://www.nerdfonts.com) for icons

## Linux / macOS

```bash
git clone https://github.com/TheAnonymousCrusher/yt-nerddl.git
cd yt-nerddl
python3 -m pip install -r requirements.txt
chmod +x yt-nerddl.py
sudo cp yt-nerddl.py /usr/local/bin/yt-nerddl
```

Run it:

```bash
yt-nerddl [options] <url>
```

## Windows

1. Install Python 3.11+.
2. Make sure `ffmpeg` is in your `PATH`.
3. Clone the repo:
   ```bash
   git clone https://github.com/TheAnonymousCrusher/yt-nerddl.git
   cd yt-nerddl
   ```
4. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
5. Run it:
   ```bash
   python yt-nerddl.py [options] <url>
   ```

> Use Windows Terminal + a Nerd Font if you want the icons to render clean.

## [Not Recommended] AUR (Arch Linux)

Beta/unstable versions may appear in AUR.

```bash
yay -S yt-nerddl
```

Works with `yay`, `paru`, `pikaur`, etc.

---

## Usage

### Basic command

```bash
yt-nerddl [options] <url>
```

### Options

| Option | Description |
| :--- | :--- |
| `-a, --audio` | Download audio only and convert to MP3 |
| `--video` | Force video mode |
| `-q, --quality` | Open the interactive quality / bitrate selector |
| `-H, --high` | Download highest available video quality |
| `--no-playlist` | If the URL contains a playlist, download only the current video |
| `-c, --cookies <browser>` | Use browser cookies for age-restricted / logged-in content |
| `--no-cookies` | Disable cookies even if enabled in config |
| `-o, --output <dir>` | Override output directory |
| `-y, --yes` | Skip prompts/menus and use defaults/config; existing files are kept by default |
| `--debug` | Print detected service, extractor, selected format selector, and yt-dlp options |
| `--theme <name>` | Theme override for this run |
| `--theme-preview` | List installed themes + preview |
| `--no-icons` | Disable icons for this run |
| `--no-colors` | Disable ANSI colors for this run |
| `--config <path>` | Use a custom `config.toml` path |
| `--init-config` | Create config + bundled themes and exit |
| `-U, --update`, `--upgrade` | Self-update from GitHub |
| `-v, --version` | Show version and exit |

### Examples

Download with the interactive selector:

```bash
yt-nerddl -q https://www.youtube.com/watch?v=xxxx
```

Force single-video mode on a playlist URL:

```bash
yt-nerddl --no-playlist https://www.youtube.com/watch?v=xxxx&list=yyyy
```

Download audio from YouTube Music using Firefox cookies:

```bash
yt-nerddl -a -c firefox https://music.youtube.com/watch?v=xxxx
```

Skip prompts and print debug info:

```bash
yt-nerddl --debug -y https://youtu.be/xxxx
```

Update the script:

```bash
yt-nerddl -U
```

---

## Notes You Probably Actually Need

### Output directory behavior

Default behavior is now:

- **YouTube / YouTube Music:** `~/Videos/Youtube`
- **Other URLs:** `~/Videos`  
  only when your config is still using the untouched default output path

If you pass `-o` or change `downloads.output_directory` in the config, your custom path wins.

### Existing file behavior

For single-item downloads, `yt-nerddl` now does a best-effort check before downloading:

- if the target file already exists, it asks before overwriting
- if you use `--yes`, it keeps the existing file by default
- playlist downloads stay conservative and avoid forcing overwrites unless you explicitly choose otherwise later

### YouTube Music audio polish

For audio downloads, especially from YouTube Music, `yt-nerddl` now tries to:

- embed metadata
- embed cover art
- prefer square cover art when yt-dlp exposes it
- rename the final file to `Artist - Track.mp3` when the metadata is clean enough

This is **best-effort** and depends on what metadata / thumbnails yt-dlp can actually see for the track.

### Non-YouTube URLs

This tool is still **only tested on YouTube + YouTube Music**.

Other URLs use yt-dlp's generic support, so:

- they may work
- they may behave differently
- they may even be arbitrary hosted files, not actual media pages

`yt-nerddl` warns you when a URL looks generic / non-media, but you're still using those sites at your own risk.

### `ffmpeg`

`ffmpeg` is strongly recommended and is required for a bunch of nice stuff:

- video/audio merging
- MP3 conversion
- cover-art embedding
- some metadata post-processing

---

## Configuration

`yt-nerddl` auto-creates a config on first run.

### Default config locations

- **Linux / macOS:** `~/.config/yt-nerddl/config.toml`
- **Windows:** `%APPDATA%\yt-nerddl\config.toml`

### Default config

```toml
# yt-nerddl config.toml
# Auto-generated on first run.
#
# Linux/macOS: ~/.config/yt-nerddl/config.toml (or $XDG_CONFIG_HOME)
# Windows:     %APPDATA%\yt-nerddl\config.toml
#
# TIP:
#   - Want no fancy glyphs? set [ui] icons = false
#   - Want no ANSI colors?  set [ui] colors = false

[downloads]
mode = "video"                 # "video" | "audio"
quality = "1080p30"            # video preset key (see README)
audio_bitrate = 320            # 320 | 256 | 192 | 128 | "best"
output_directory = "~/Videos/Youtube"  # default for YouTube / YouTube Music; non-YouTube falls back to ~/Videos if unchanged

[behavior]
interactive = false
playlist = "ask"               # "ask" | "video" | "playlist" (CLI: --no-playlist forces single-video)
check_internet = true
assume_yes = false             # if true: never prompt; use defaults/config

[cookies]
enabled = false
browser = "firefox"            # firefox | chrome | brave | edge | opera | safari

[network]
continuedl = true              # resume partial downloads (.part)
retries = 10                   # network retries
fragment_retries = 10          # retries for fragmented streams

[ui]
theme = "default"              # default | catppuccin | gruvbox | nord
progress_bar_width = 25
progress_fill = ""             # override fill glyph ("" = theme default)
progress_empty = ""            # override empty glyph ("" = theme default)
icons = true
colors = true
```

### Progress bar customization

```toml
[ui]
progress_bar_width = 30
progress_fill = "▰"
progress_empty = "▱"
```

---

## Mature / Member-Only / Age-Restricted Content

Use browser cookies when you need access to logged-in content.

Supported browsers in the CLI docs/config right now:

- Firefox
- Chrome
- Brave
- Edge
- Opera
- Safari

Example:

```bash
yt-nerddl -q -c firefox https://www.youtube.com/watch?v=xxxx
```

Full guide:

- [mature_content.md](https://github.com/TheAnonymousCrusher/yt-nerddl/blob/main/mature_content.md)

---

## Website

The website includes:

- the screenshot gallery
- mobile-friendly docs
- installation/usage/config notes
- changelog highlights loaded from `CHANGELOG.md`.
- much more, just check it out ;)

Visit it here:

- [https://theanonymouscrusher.github.io/yt-nerddl/](https://theanonymouscrusher.github.io/yt-nerddl/)

---

## Contributing

Pull requests and issues are welcome. Keep the CLI clean, keep the docs honest, and preserve the smooth UX.

## Acknowledgements

- `yt-dlp`
- [animepahe-cli](https://github.com/Danushka-Madushan/animepahe-cli) for UX inspiration

---

<div align="center">

**Made for people who like fast tools and clean terminals**

</div>

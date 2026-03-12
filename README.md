<br>
<div align="center">
  <img src="banner.png" width="40%">

A sleek, hassle-free YouTube downloader built as a <b>wrapper around `yt-dlp`</b>, with a clean, interactive inline selector and a Deno-inspired loading bar. Designed for anyone who wants a straightforward way to download audio/video from YouTube without fussing with complex commands.

</div>

<br>

<div align="center">
  <img src="screenshot1.png" width="49%">
  <img src="screenshot2.png" width="49%">
</div>

<br>

> **Note:** Only works for YouTube and YouTube Music (for now).
> <br>
> **Current Version:** v2026.03.12 (stable)

---

# Usage

* ✅ **Audio & Video downloads**
  `-a / --audio` → download audio only (mp3)
  Video downloads default to **mp4**

* ✅ **Interactive quality selection**
  `-q / --quality` → pick video or audio quality via an inline arrow menu

* ✅ **Browser Cookies Integration**
  `-c / --cookies <browser>` → bypass age restrictions by extracting cookies from your local browser.
  ([See tutorial](https://github.com/TheAnonymousCrusher/yt-nerddl/blob/main/mature_content.md))

* ✅ **Highest quality mode**
  `-H / --high` → automatically grab the best available video

* ✅ **Custom output folder**
  `-o / --output <directory>` → choose where downloads are saved
  Default: `~/Videos/Youtube`

---

# Features

* ✅ **Playlist support**
  Prompts if the URL contains a playlist and allows downloading all videos

* ✅ **Cross-platform interactive menus**
  Inline selector works natively on **Linux, macOS, and Windows**

* ✅ **Progress bar inspired by Deno**
  Shows percentage, downloaded size, total size, speed, and ETA

* ✅ **Handles YouTube Music URLs**
  Automatically converts music URLs to standard YouTube format

* ✅ **Automatic MP3 conversion** (audio mode)
  Supports bitrate selection: `320`, `256`, `192`, `128 kbps`, or `Best`

* ✅ **Minimal console output**
  Color-coded status messages for selections, progress, and errors

* ✅ **Interrupt handling**
  `Ctrl+C` safely cancels downloads at any stage

---

# Installation

## Dependencies

Make sure you have these installed:

* Python **3.11+**
* `yt-dlp`
* `ffmpeg` (for audio extraction/conversion)
* A [NerdFont](https://www.nerdfonts.com) (for icons to display correctly)

---

# From GitHub (Recommended)

> Applies to Linux distributions and macOS

```bash
git clone https://github.com/TheAnonymousCrusher/yt-nerddl.git
cd yt-nerddl
chmod +x yt-nerddl.py
sudo mv yt-nerddl.py /usr/local/bin/yt-nerddl
```

After installation you can run:

```bash
yt-nerddl [options] <youtube-url>
```

---

# [NOT RECOMMENDED] From AUR (Older Version)

```bash
yay -S yt-nerddl
```

Or use any AUR helper such as `paru` or `pikaur`.

---

# Windows Installation

1. Install **Python 3.11+**
2. Install **FFmpeg**
3. Clone the repository:

```bash
git clone https://github.com/TheAnonymousCrusher/yt-nerddl.git
cd yt-nerddl
```

4. Install dependencies:

```bash
pip install -r requirements.txt
```

5. Run the script:

```bash
python yt-nerddl.py [options] <url>
```

> Note: Use a **Nerd Font** in Windows Terminal for proper icon rendering.

---

# Basic Usage

```bash
yt-nerddl [options] <url>
```

## Options

| Option                 | Description                                    |
| ---------------------- | ---------------------------------------------- |
| `-a`, `--audio`        | Download audio only (mp3)                      |
| `-c`, `--cookies`      | Use browser cookies to bypass 18+ restrictions |
| `-H`, `--high`         | Fetch highest available quality                |
| `-o`, `--output <dir>` | Specify output directory                       |
| `-q`, `--quality`      | Interactive quality selector                   |

---

# Examples

Download an age-restricted video using Firefox cookies:

```bash
yt-nerddl -q -c firefox https://www.youtube.com/watch?v=xxxx
```

Download a playlist in the highest available quality:

```bash
yt-nerddl -H https://www.youtube.com/playlist?list=xxxx
```

---

# Philosophy

**yt-nerddl** aims to make downloading YouTube content simple, intuitive, and visually clear.

Instead of memorizing complex `yt-dlp` commands, users get:

* a clean interactive selector
* clear progress feedback
* sensible defaults

It’s essentially **yt-dlp with a modern, interactive wrapper** designed to feel fast and minimal.

---

# Contributions

Contributions are welcome.

* Open a **PR** or submit an **issue** for bugs or feature ideas.
* Keep the progress bar clean, colors readable, and the UX smooth.

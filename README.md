<br>
<div align="center">
  <img src="banner.png" width="40%" >

  A sleek, hassle-free YouTube downloader built as a <b>wrapper around `yt-dlp`</b>, with a clean, interactive inline selector and a Deno-inspired loading bar. Designed for anyone who wants a straightforward way to download audio/video from YouTube without fussing with complex commands.
</div>
<br>

<div align="center">
  <img src="screenshot1.png" width="49%" >
  <img src="screenshot2.png" width="49%" >
</div>
<br>

> Note: only works for YouTube and YouTube Music (for now at least)

---

# Usage

- ✅ **Audio & Video downloads**  
  - `-a / --audio` → download audio only (mp3)  
  - Video downloads default to mp4  

- ✅ **Interactive quality selection**  
  - `-q / --quality` → pick video or audio quality via an inline arrow-menu  

- ✅ **Highest quality mode**  
  - `-H / --high` → automatically grab the best available video  

- ✅ **Custom output folder**  
  - `-o / --output <directory>` → choose where to save downloads (default: `~/Videos/Youtube`)  

---

# Features

- ✅ **Playlist support**  
  - Prompts if the URL contains a playlist and allows downloading all videos  

- ✅ **Progress bar inspired by Deno**  
  - Shows percentage, downloaded size, total size, speed, ETA  

- ✅ **Handles YouTube Music URLs**  
  - Normalizes music URLs to regular YouTube format  

- ✅ **Automatic MP3 conversion** (for audio mode)  
  - Supports bitrate selection: 320, 256, 192, 128 kbps, or Best  

- ✅ **Minimal and clean console output**  
  - Color-coded status messages for errors, selections, and progress  

- ✅ **Interrupt handling**  
  - Ctrl+C gracefully cancels downloads at any stage  

---

# Installation

### Dependencies

Make sure you have these installed:

- Python 3.11+  
- `yt-dlp` (`pip install yt-dlp`)  
- `ffmpeg` (for audio extraction/conversion)
- A [NerdFont](https://www.nerdfonts.com) (for glyphs to appear correctly)  

## From GitHub (Recommended)
> Applies to any non-Arch based distros & MacOS

```bash
git clone https://github.com/TheAnonymousCrusher/yt-nerddl.git
cd yt-nerddl
chmod +x yt-nerddl.py
sudo mv yt-nerddl.py /usr/local/bin/yt-nerddl
````

## From AUR (older version, not maintained)

```bash
yay -S yt-nerddl # or whatever AUR helper you use (e.g paru, pikaur)
```

> After installation, you can run it simply with:

```bash
yt-nerddl [options] <youtube-url> 
```

## Windows

>‼️ Interactive quality selector (-q) is currently not supported on Windows

- Make sure you have Python 3.11+ and FFmpeg installed.
- Clone/download the repo:
``` bash
git clone https://github.com/TheAnonymousCrusher/yt-nerddl.git
cd yt-nerddl
# Install dependencies
pip install -r requirements.txt
```

- Run the script when you need to use it:

```bash
python yt-nerddl.py [options] <url>
```

> Note: For the icons to look right, make sure your Windows Terminal is set to use a Nerd Font.

---

# Basic Usage Guide

```bash
yt-nerddl [options] <url>
```

**Options:**

| Option               | Description                                          |
| -------------------- | ---------------------------------------------------- |
| `-a, --audio`        | Download audio only (mp3)                            |
| `-H, --high`         | Fetch highest available quality                      |
| `-o, --output <dir>` | Specify output directory (default: ~/Videos/Youtube) |
| `-q, --quality`      | Interactive quality selector                         |

**Example:**

* Download audio only at best quality:

```bash
yt-nerddl -a -q https://www.youtube.com/watch?v=xxxx
```

* Download a playlist in the highest available quality:

```bash
yt-nerddl -H https://www.youtube.com/playlist?list=xxxx
```

---

# Philosophy

`yt-nerddl` is meant to be **a nice-looking, hassle-free YouTube downloader**. The idea is to make downloading content intuitive, quick, and visually clear without writing complex `yt-dlp` commands. The **progress bar** and inline selector are inspired by Deno’s clean aesthetic.

It’s essentially `yt-dlp`, but with a friendly, interactive wrapper that feels modern, fast, and minimal.

---

# Contributions

* Contributions welcome!
* Open a PR or submit issues for bugs/features.
* Keep the progress bar clean, colors readable, and UX smooth.


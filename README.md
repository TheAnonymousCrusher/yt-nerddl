<div align="center">

<img src="banner.png" width="40%">

### A sleek YouTube downloader built on top of `yt-dlp`

Clean interactive selector • Deno-style progress bar • Minimal CLI UX

<br>
<div align="center">

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Backend](https://img.shields.io/badge/Backend-yt--dlp-red?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Linux%20|%20macOS%20|%20Windows-2bbc8a?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-black?style=for-the-badge)

</div>

Inspired by [animepahe-cli](https://github.com/Danushka-Madushan/animepahe-cli)

</div>

---

## Preview

<div align="center">

<img src="screenshot1.png" width="49%">
<img src="screenshot2.png" width="49%">

</div>

> **Note**  
> Currently supports **YouTube** and **YouTube Music**

**Current Version:** `v2026.03.13` [Friday the 13th Edition ;)]

---

# Features

✔ Audio & Video downloads  
✔ Interactive quality selector  
✔ Playlist detection  
✔ Deno-inspired progress bar  
✔ YouTube Music URL support  
✔ Automatic MP3 conversion  
✔ Cross-platform CLI menus  
✔ Cookie extraction for age-restricted videos  
✔ Built-in auto updater  
✔ Clean minimal console output  
✔ Safe interrupt handling (`Ctrl+C`)

---

# Installation

## Requirements

- Python **3.11+**
- `yt-dlp`
- `ffmpeg`
- [Nerd Font](https://www.nerdfonts.com) (for icons)

---

# Install (Linux / macOS)

```bash
git clone https://github.com/TheAnonymousCrusher/yt-nerddl.git
cd yt-nerddl
chmod +x yt-nerddl.py
sudo mv yt-nerddl.py /usr/local/bin/yt-nerddl
```

Run it:

```bash
yt-nerddl [options] <youtube-url>
```

---

# [NOT RECOMMENDED] AUR (Arch Linux)

Older versions may appear in AUR.

```bash
yay -S yt-nerddl
```

Works with:

- yay  
- paru  
- pikaur  

---

# Windows Installation

### 1 Install Python

Install **Python 3.11+**

### 2 Install FFmpeg

Make sure `ffmpeg` is in PATH.

### 3 Clone repository

```bash
git clone https://github.com/TheAnonymousCrusher/yt-nerddl.git
cd yt-nerddl
```

### 4 Install dependencies

```bash
pip install -r requirements.txt
```

### 5 Run

```bash
python yt-nerddl.py [options] <url>
```

Use **Windows Terminal + Nerd Font** for proper icon rendering.

---

# Usage

Basic command:

```bash
yt-nerddl [options] <url>
```

---

# Options

| Option | Description |
|------|------|
| `-a`, `--audio` | Download audio only (MP3) |
| `-q`, `--quality` | Interactive quality selector |
| `-H`, `--high` | Download highest available quality |
| `-c`, `--cookies <browser>` | Use browser cookies for 18+ videos |
| `-o`, `--output <dir>` | Specify output directory |
| `-U`, `--update` | Update script from GitHub |
| `-v`, `--version` | Show version |

---

# Examples

Download with quality selector:

```bash
yt-nerddl -q https://youtube.com/watch?v=xxxx
```

Download audio only:

```bash
yt-nerddl -a https://youtube.com/watch?v=xxxx
```

Download highest quality:

```bash
yt-nerddl -H https://youtube.com/watch?v=xxxx
```

Download age-restricted video:

```bash
yt-nerddl -q -c firefox https://youtube.com/watch?v=xxxx
```

Download playlist:

```bash
yt-nerddl -H https://youtube.com/playlist?list=xxxx
```

Update the script:

```bash
yt-nerddl -U
```

---

# Output Directory

Default download locations:

| OS | Path |
|---|---|
| Linux / macOS | `~/Videos/Youtube` |
| Windows | `%USERPROFILE%\Videos\Youtube` |

---

# Philosophy

`yt-nerddl` exists to make downloading YouTube content **simple and intuitive**.

Instead of remembering complicated `yt-dlp` commands, users get:

• an interactive selector  
• clear progress feedback  
• sensible defaults  
• minimal CLI noise  

Think of it as **yt-dlp with a modern interactive wrapper**.

---

# Contributing

Pull requests and issues are welcome.

Guidelines:

- Keep the CLI clean
- Maintain readable colors
- Preserve smooth UX
- Avoid unnecessary dependencies

# Acknowledgements

- `yt-dlp` project  
- `animepahe-cli` for UX inspiration

---

<div align="center">

Made for people who like **fast tools and clean terminals**

</div>

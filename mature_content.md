# 🍪 Downloading Age-Restricted & Private Content

YouTube sometimes restricts access to certain videos (for example: **18+ content, unlisted videos tied to your account, or members-only content**).

Since **`yt-nerddl` downloads videos anonymously by default**, it cannot access these restricted videos.

To bypass this, you can use the `-c` or `--cookies` flag. This tells **yt-nerddl** to extract session cookies directly from your web browser, allowing the downloader to temporarily authenticate as you.

---

# How to Use It

You must be **logged into a YouTube account in your browser** that is allowed to watch the video (for example, an account that passes the age check).

Run:

```bash
yt-nerddl -c firefox https://www.youtube.com/watch?v=xxxx
```

The script will extract cookies from your browser and pass them to `yt-dlp`.

---

# Supported Browsers

You can use any browser supported by `yt-dlp` for cookie extraction. Common options include:

* `firefox`
* `chrome`
* `edge`
* `brave`
* `vivaldi`
* `opera`
* `safari`

Example:

```bash
yt-nerddl -c brave https://www.youtube.com/watch?v=xxxx
```

---

# Example Workflow

1. Open **Firefox** (or your preferred browser).
2. Log into your **YouTube account**.
3. Confirm that the restricted video plays normally in your browser.
4. Close the browser *(optional but recommended on some systems)*.
5. Run the command:

```bash
yt-nerddl -q -c firefox https://www.youtube.com/watch?v=xxxx
```

---

# Troubleshooting

### "Database is locked"

This error usually happens if your browser is currently running and actively writing to its cookie database.

Fix:

1. Close the browser completely.
2. Run the command again.

---

### "Sign in to confirm your age"

If this error still appears:

* Make sure you specified the **same browser** where you are logged into YouTube.
* Confirm that your account can actually watch the video inside the browser.
* Try closing the browser before running the command.

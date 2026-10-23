# MacDM downloads

Builds of **MacDM**, a download manager for Ubuntu (and other Linux), macOS and Windows. It downloads over
several connections at once, pauses and resumes, sorts downloads into categories, and picks up videos and
downloads from Chrome, Edge, Brave and Chromium.

Get the latest build from [**Releases**](../../releases/latest). These builds are not code-signed, and are
150–200 MB because they include `yt-dlp` and `ffmpeg`: there is nothing else to install.

## Ubuntu / Debian

```bash
sudo apt install ./MacDM-*-linux-amd64.deb
```

Then start **MacDM** from the applications menu. Closing its window keeps it running in the system tray;
start it again to bring the window back. (Ubuntu's default desktop shows tray icons. Other desktops may
need an AppIndicator extension.)

An AppImage is also provided (`MacDM-*-linux-x86_64.AppImage`). Make it executable and run it. On
Ubuntu 24.04 and later, AppArmor blocks the sandbox for AppImages, so start it with `--no-sandbox`
or use the `.deb` instead.

## macOS (Apple Silicon)

Open `MacDM-*-mac-arm64.dmg` and drag MacDM to Applications. The first time, right-click it and choose
**Open**.

## Windows (64-bit)

Run `MacDM-Setup-*-win-x64.exe`, or unzip the portable `MacDM-*-win-x64-portable.zip`. SmartScreen asks
you to confirm: **More info → Run anyway**. The Windows
build has not been tested on a PC.

## Browser extension

Unzip `MacDM-extension-*.zip` somewhere permanent. In `chrome://extensions` (or `edge://extensions`,
`brave://extensions`) turn on **Developer mode**, click **Load unpacked** and choose the unzipped folder.
Start MacDM once first: it registers itself with each browser it finds, which is how the extension talks
to it. If you move MacDM, start it again.

On Linux, MacDM registers with Google Chrome, Chromium, Microsoft Edge and Brave installed from `.deb` or
the browsers' own repositories. Snap and Flatpak browsers keep their profiles elsewhere and are not
supported yet.

## What it does

`yt-dlp` and `ffmpeg` are included, so downloading from video sites and joining video and audio works
out of the box. MacDM updates its copy of `yt-dlp` once a day (and on request from the tray icon's
**Update yt-dlp now**), because video sites change often. FFmpeg is GPL-licensed and runs as a
separate program; its source is linked in the notices file inside the app.

- **Fast downloads:** up to 8 connections per file, split dynamically as connections finish; pause and resume.
- **New-download window:** name, category, folder, size and video quality, before anything starts.
- **Categories:** Video, Music, Documents, Compressed, Programs and your own, each with its own folder.
- **Download all / selected links** from a page, with a queue of 3 at a time.
- **Speed limit** per download and for all, and **sleep / shut down when done**.
- **Streams:** HLS (with AES-128), DASH (with `ffmpeg`); protected (DRM) streams are refused.

Report problems by opening an issue here.

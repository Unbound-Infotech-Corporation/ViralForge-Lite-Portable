# ViralForge Studio Setup — Lite portable (Windows)

For friends testing on **Windows 10 or Windows 11 (64-bit)**.

This zip is the **setup app**, not the GPU model pack. Lite is pre-selected. **No Wan or LTX video weights are included.**

## What Lite does

- Opens ViralForge Studio Setup with **Lite** selected.
- The **FFmpeg Ken Burns / dry-run cinema** path is ready immediately. You do **not** need a 40–150 GB download to try that.
- Piper TTS and Whisper captions are **optional** and off by default here so nothing large starts on first click.
- You can still switch to **Regular** or **Maximum** in the same window later.

## Install (about one minute)

1. Unzip `ViralForge-Lite-Portable.zip` to a folder you can write to
   (example: `Downloads\ViralForge-Lite-Portable`).
2. Double-click **`Start.bat`**.
   Same thing: **`ViralForgeSetup.bat`**.
3. The first launch copies local Python libraries from `vendor\wheels` (no Hugging Face model download). A console window stays open so you can see progress.
4. When the dark setup window appears, Lite is already selected. Click **Install Lite pack** if you want the cinema marker written into the `models` folder next to this app. Or just look around — Regular and Maximum stay in the sidebar.

Windows may show SmartScreen the first time (“Windows protected your PC”). Choose **More info → Run anyway**. This zip is unsigned.

## What you need

| | |
| --- | --- |
| OS | Windows 10 or 11, 64-bit |
| Python | **Not required** — a private copy is inside `runtime\` |
| GPU | Not required for Lite dry-run cinema |
| Internet | Not required for Lite cinema. Required later if you install Regular/Maximum or optional Piper/Whisper |

If you want real Ken Burns renders (not just the setup checklist), install FFmpeg when you are ready:

```bat
winget install Gyan.FFmpeg
```

## Upgrade to Regular or Maximum later

You do **not** need a new zip.

1. Run `Start.bat` again.
2. In the left sidebar pick **Regular** (~40–80 GB, Wan 2.2 TI2V-5B + LTX-2.5) or **Maximum** (~150 GB+, adds Wan 2.2 I2V A14B).
3. Confirm the models folder and free disk (Maximum warns you).
4. Click **Install … pack**. Those weights download from Hugging Face then — they were never shipped in Lite.

Regular is the day-to-day pack for RTX 5090-class cards. Maximum is the quality extra.

## Folders

| Path | What it is |
| --- | --- |
| `runtime\` | Private Windows Python. Do not replace with another install. |
| `app\` | Setup program |
| `vendor\wheels\` | Local PySide6 / Hub libraries (not video models) |
| `models\` | Created on first run. Lite writes a tiny cinema marker here. Regular/Maximum weights go here if you upgrade |

## If something fails

- **Window never opens:** you unzipped only `Start.bat`. Unzip the whole folder so `runtime\python.exe` and `app\` sit next to it.
- **“Install Lite” is instant:** that is correct. Lite has no GPU weights to fetch.
- **You wanted hero-shot video:** switch the sidebar to Regular (or Maximum) and install. That is a large download on purpose.

# AAHM Android project

This folder contains:
- `main.py` — the Kivy app, with the supplied AAHM emblem on the login screen
- `aahm_logo.png` — the supplied emblem
- `buildozer.spec` — starting configuration for building an Android APK

## Build the APK

Buildozer is normally run on Linux (or Linux in WSL on Windows). Install the system
dependencies and Buildozer following the official Buildozer installation guide, then
run these commands from this folder:

```bash
buildozer android debug
```

The first build downloads Android build components and can take a while. If successful,
the APK is usually placed in `bin/`.

## Important notes before installing

1. The app currently uses the demo login `admin` / `admin`. Change this before using
   real personal data; these credentials are not secure.
2. The code uses `python-docx`. Its dependency chain may require extra packaging fixes
   for Android; if Buildozer reports a recipe/dependency error, the Word import/export
   feature will need an Android-compatible approach or a supported recipe.
3. The code currently looks for imported Word documents at `/sdcard/Download/<filename>`.
   Modern Android versions restrict direct shared-storage access, so file selection via
   Android's document picker is the more reliable follow-up change.
4. Cadet records are sensitive personal information. Use only authorized data and
   protect exported files and the device.

This is a build-ready starting project, not a tested APK. An Android SDK/NDK + Buildozer
environment is required to produce the final APK.

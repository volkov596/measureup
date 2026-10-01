# Measure Up

**Experimental.** Prototype stage (v0.13.0). Not validated for survey, compliance or QA work.

Web app that connects a **Bosch GLM 50-27 CG** laser distance meter to an Android phone over Bluetooth LE. Take readings from the phone, log them with photos, GPS and phone tilt, and run continuous "slider" scans to profile a surface.

**Open the app:** https://volkov596.github.io/REPO-NAME/

## What it does

- **Remote trigger:** take a reading from the phone. Readings taken with the meter button are logged too.
- **Photo per reading:** via the phone's camera app (full quality, reading stored in the photo as XMP) or the in-browser camera (reading stored as EXIF).
- **Log and CSV export:** distance, angle, vertical/horizontal components, offset, GPS, phone tilt.
- **Scan (slider) mode:** repeated readings at about 2.4 per second for surface profiles, with a built-in profile viewer and one CSV per scan.
- **Frame log (optional):** raw Bluetooth traffic for troubleshooting.

## Requirements

- Bosch GLM 50-27 CG. Other models untested.
- Android phone with **Chrome** (needs Web Bluetooth). Firefox and iPhone are not supported; other Chromium browsers are untested.
- Nothing to install. Runs from GitHub Pages (https is required for Bluetooth and the camera).

## Quick start

1. Turn on the meter and its Bluetooth.
2. Open the app link in Chrome on Android.
3. Tap **Connect** and pick the meter from the list.
4. Tap **Measure**.

After an update, add `?v=` plus any number to the link to skip the cache. The version is shown at the bottom of the page.

## Status and known limits

- Uses an **undocumented Bluetooth protocol** worked out by testing. A firmware update could change it, and other units may behave differently.
- Tested with one meter and one phone (Motorola).
- Bench repeatability: about 0.1 mm at 2–4 m, about 0.75 mm at 12–16 m. Accuracy against a reference is **not yet checked**; Bosch spec is ±1.5 mm.
- Scan readings are not shown on the meter or saved to its memory.
- Keep the app on screen during scans. Chrome slows it down in the background.
- The app does not send commands that change meter settings, clear its memory or update firmware.

## Disclaimer

Independent hobby project. Not affiliated with or endorsed by Bosch. Bosch and GLM are trademarks of Robert Bosch GmbH. Provided as is, with no warranty. Use at your own risk.

Class 2 laser: don't look into the beam or point it at people.

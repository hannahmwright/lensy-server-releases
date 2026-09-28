# Lensy Server

Lensy Server is the optional companion for [Lensy](https://lensy-push.vercel.app), the iPhone app for [Frigate](https://frigate.video). Install it on the computer that runs Frigate to add:

- **Guest passes:** live-only access for a nanny or sitter, with hours, Wi-Fi-only, sound and camera-movement controls.
- **Home Assistant rooms:** each camera's room readings and controls, right under the video.
- **Camera watchdog:** fixes camera clocks after a power cut and restarts Frigate when recording stops.

## Install (Windows)

1. Download the latest `LensyServerSetup-<version>.exe` from [Releases](../../releases/latest).
2. Run it. Windows may say the publisher is unknown: choose **More info → Run anyway**.
3. A page opens with a 6-digit code. In Lensy, go to **Settings → Manage Frigate → Lensy Server**, choose this PC, and enter the code.

Lensy Server runs in the background, starts with Windows, and keeps its settings in `C:\ProgramData\Lensy`. Updating is done from Lensy.

This repository holds releases only.

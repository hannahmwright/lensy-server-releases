# Lensy Server

Lensy Server is the optional companion for [Lensy](https://lensy-push.vercel.app), the iPhone app for [Frigate](https://frigate.video). Install it where Frigate runs to add:

- **Guest passes:** live-only access for a nanny or sitter, with hours, Wi-Fi-only, sound and camera-movement controls.
- **Home Assistant rooms:** each camera's room readings and controls, right under the video.
- **Camera watchdog:** fixes camera clocks after a power cut and restarts Frigate when recording stops.

Each install ends the same way: you get a 6-digit code, and in Lensy you go to **Settings → Manage Frigate → Lensy Server**, choose the server and enter the code. Everything else is set up in Lensy.

## Windows

1. Download the latest `LensyServerSetup-<version>.exe` from [Releases](../../releases/latest).
2. Run it. Windows may say the publisher is unknown: choose **More info → Run anyway**.
3. A page opens with the code. To see it again later, open **Lensy Server** from the Start menu.

It runs in the background, starts with Windows, and keeps its settings in `C:\ProgramData\Lensy`. Updating is done from Lensy.

## Home Assistant

[![Add repository to Home Assistant](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fhannahmwright%2Flensy-server-releases)

1. Add this repository in Home Assistant: Settings → Apps → App store → ⋮ → Repositories, then enter `https://github.com/hannahmwright/lensy-server-releases`.
2. Install **Lensy Server** and start it.
3. Open **Lensy** in the sidebar for the code.

If Frigate runs as a Home Assistant app, Lensy Server finds it by itself. It also connects to Home Assistant without a token.

## Docker

1. Download [`docker-compose.yml`](docker-compose.yml) and pick any six digits for `LENSY_SETUP_CODE` in it.
2. `docker compose up -d`
3. Enter those six digits in Lensy.

The compose file uses host networking so Lensy finds the server on your Wi-Fi. Where that isn't available, it explains what to do instead.

---

This repository holds releases only: the Windows installers, the Home Assistant app (`repository.yaml`, `lensy-server/`) and `docker-compose.yml`. The Docker image is `ghcr.io/hannahmwright/lensy-server`.

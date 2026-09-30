# Lensy Server

Lensy Server is the companion for the Lensy iPhone app. It sends alerts, hands out guest passes, shows each camera's Home Assistant room, and looks after cameras with the watchdog.

## Set up

1. Start the app.
2. Open **Lensy** in the sidebar. It shows a six-digit pairing code.
3. On your iPhone, open Lensy → Settings → Manage Frigate → Lensy Server, choose this server, and enter the code.

When you pair, you sign in to Frigate as an admin in Lensy. The server then:

- finds Frigate: first Frigate's own Home Assistant app, then Frigate on this machine, then the address Lensy uses;
- creates its own Frigate account, `lensy_companion`;
- restarts, connected.

The **Lensy** panel then shows a checklist of what's working. Everything else is set up in Lensy.

## Home Assistant rooms

The app connects to this Home Assistant by itself, so you don't need a long-lived access token. In Lensy, choose a camera's room and the devices to show with it. To use a different Home Assistant, set it up in Lensy; that replaces this one.

## Network

The app uses the host's network, for two reasons:

- Lensy finds it on your Wi-Fi.
- Wi-Fi-only guest passes work on port 3219. Never point a tunnel or port forward at 3219.

For access away from home, run a tunnel to port 3218. That port only listens on this machine.

## Backups

Home Assistant backups include Lensy Server's database: guest passes, rooms and settings. The app stops for a moment while a backup is taken.

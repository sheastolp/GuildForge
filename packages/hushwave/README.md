# GuildForge Hushwave

**Ambient sound player** for Windows, built with Tauri.

Part of the **GuildForge** suite.
*Chatbots, overlays & ambient tools — forged for streamers.*

## Overview

Hushwave is a native Windows desktop app for ambient background soundscapes — designed to run light on a streaming PC and route cleanly into OBS.

## Stack

- **Frontend:** React + Vite (`client/`)
- **Backend/shell:** Tauri (Rust) (`src-tauri/`)
- Shared types/config in `shared/`, server-side pieces in `server/`

## Building

Builds are produced via **GitHub Actions** rather than locally — this project intentionally avoids a local build toolchain (no local Rust/Windows build environment, and `pnpm` doesn't work reliably on the primary dev machine). Push to the repo to trigger a Windows installer build through the Actions workflow.

See `README-WINDOWS.md` in this folder for additional Windows-specific setup and usage notes.

## Usage

1. Install the built Windows executable.
2. Run the app and choose or generate a soundscape.
3. Route its audio output into OBS as an Audio Input Capture, or via a virtual audio cable.

## License
MIT — see the root [LICENSE](../../LICENSE).

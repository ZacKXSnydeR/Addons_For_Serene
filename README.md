# Serene Engines & Addons

This repository hosts the backend engines and components required for the **Serene** music streaming application. 
Serene uses a highly modular architecture where background extraction logic (like YouTube Music metadata and streaming streams) are decoupled from the main UI application.

## Components

### `ytmusic_server.exe`
A custom-built Python REST server wrapping `ytmusicapi`. 
- **Purpose**: Exposes endpoints for the Serene frontend to perform searches, fetch lyrics, get playlists, and manipulate YouTube Music history.
- **Port**: Runs locally on `http://127.0.0.1:5050`.
- **Packaging**: Compiled using PyInstaller for zero-dependency execution on user machines.

### `yt-dlp`
An external dependency used exclusively for direct audio stream extraction. Serene downloads official `yt-dlp` binaries directly to ensure the highest reliability.

## Addons Manifest
The `addons_manifest.json` file in the root of this repository serves as the central directory mapping operating systems and architectures to their respective download URLs. The Serene app periodically fetches this JSON to discover updates and install engines tailored to the user's system.

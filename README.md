# Voxora Releases

Official binary releases of **Voxora** — the local-first voice dictation app by NexusForge Labs.

## Install

1. Download `Voxora-win64-v<version>.zip` from the [latest release](https://github.com/NexusForgeLab/Voxora-releases/releases/latest).
2. Unzip anywhere user-writable (e.g. `%LOCALAPPDATA%\Voxora`).
3. Run `Voxora.exe`. The first run downloads the AI models (~2.5 GB) with a progress window.

The app updates itself automatically from this repo. Your settings, dictation history, and models live in `~/.voxora` and survive every update.

Each release ships with a `manifest.json` (sha256 + size); the built-in updater verifies downloads against it before installing.

## Source

The Voxora source repository is private. This repo contains binary builds only. For bug reports, use the Issues tab here.

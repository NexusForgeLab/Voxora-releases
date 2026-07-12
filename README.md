<p align="center">
  <img src="https://raw.githubusercontent.com/NexusForgeLab/Voxora-releases/main/assets/voxora.png" alt="Voxora logo" width="140" />
</p>

<h1 align="center">Voxora</h1>

<p align="center">
  Local-first AI voice dictation, cleanup, notes, meetings, and personal writing automation for Windows.
</p>

<p align="center">
  <a href="https://github.com/NexusForgeLab/Voxora-releases/releases/latest"><img alt="Latest Release" src="https://img.shields.io/github/v/release/NexusForgeLab/Voxora-releases?style=flat-square&color=22c55e&label=download"></a>
  <a href="https://github.com/NexusForgeLab/Voxora-releases/issues"><img alt="Issues" src="https://img.shields.io/badge/bug%20reports-issues%20tab-f97316?style=flat-square"></a>
</p>

---

## What Voxora Does

Voxora is a desktop voice assistant for writing anywhere on your computer. Hold a hotkey, speak naturally, release, and Voxora transcribes your speech, cleans it up, and pastes polished text into the app that already has focus.

It is built for fast daily dictation: messages, email, documentation, notes, meetings, snippets, rewrites, and personal vocabulary. Your history, settings, vocabulary, notes, API keys, and backup files live locally under `~/.voxora`.

Voxora runs fully local by default — speech recognition with faster-whisper and AI cleanup with a bundled `llama.cpp` server — and can optionally use your own remote server or supported cloud providers when you configure them.

## Highlights

- Hold-to-talk dictation into any focused text field.
- Local speech recognition with faster-whisper `large-v3-turbo`, including multilingual auto-detect across ~99 languages.
- AI cleanup for punctuation, grammar, filler words, self-corrections, and formatting.
- Local `llama.cpp` cleanup by default, with optional remote server and cloud provider modes.
- Dashboard with history, insights, vocabulary, styles, transforms, meetings, scratchpad, clipboard, and settings.
- Personal dictionary for names, product terms, jargon, and misheard-word corrections.
- Snippets that expand spoken cues into longer saved text.
- Scratchpad notes with autosave and dictation.
- Meeting recording with transcript and structured notes.
- Rewrite transforms for selected text in any app.
- Per-app writing style detection and overrides.
- Selective local backup and restore, and multi-device sync through any shared folder.
- Automatic, checksum-verified self-updates from this repo.

## Install

1. Download `Voxora-win64-v<version>.zip` from the [latest release](https://github.com/NexusForgeLab/Voxora-releases/releases/latest).
2. Unzip it anywhere user-writable — for example `%LOCALAPPDATA%\Voxora`. (Avoid `Program Files`: the app updates itself by replacing its own folder, which needs write access.)
3. Run `Voxora.exe`.

No Python, git, or build tools are needed.

### First run

The first launch shows a small setup window while Voxora downloads its AI models (about 2.5 GB total — the Qwen language model for cleanup and the Whisper speech model). This happens once; the models are stored in `~/.voxora/models` and survive every app update. After the download, the Voxora pill appears near the bottom of your screen.

### Dictate

1. Click into any app's text field.
2. Hold the talk hotkey (shown on the pill — click the pill to see and change it).
3. Speak.
4. Release. Cleaned-up text is pasted where your cursor was.

Click the pill for quick settings (mode, microphone, language) and the full dashboard.

## Updates

Voxora checks this repo for new releases and updates itself:

- The app probes the [latest release](https://github.com/NexusForgeLab/Voxora-releases/releases/latest) in the background and shows an "Update now" option in the dashboard when a new version is available (or applies it automatically if you enable auto-updates in Settings > Updates).
- Downloads are verified against the release's `manifest.json` (SHA-256 checksum and size) before anything is touched. A failed check discards the download and changes nothing.
- The update swaps in the new version and restarts the app. Your settings, dictation history, vocabulary, and downloaded models in `~/.voxora` are never part of the swap — they carry over untouched.

Every release on this page ships two assets: the app zip and its `manifest.json`.

## Privacy Model

Voxora is local-first.

- Core user state is stored in `~/.voxora` on your machine.
- Dictation history, notes, meetings, vocabulary, snippets, transforms, and corrections are stored in a local SQLite database.
- Local mode does not send dictation text to cloud APIs.
- Cloud/API/subscription providers receive cleanup prompts only when you explicitly choose that provider.
- Backup archives can include secrets if you select API keys and logins — treat backup files like private credentials.

## System Requirements

- Windows 10/11, 64-bit.
- ~1 GB disk for the app plus ~2.5 GB for the models.
- 8 GB RAM recommended (the local language model runs on CPU).
- A microphone.

The standalone app runs speech recognition and cleanup on CPU, so it works on any machine. GPU acceleration and the experimental fine-tuning tools are only available in source installs, which are not publicly distributed.

## Troubleshooting

- **First-run download interrupted** — just relaunch `Voxora.exe`; downloads resume where they stopped.
- **No text pasted** — make sure a text field had focus before you held the hotkey; check the pill isn't showing an error state.
- **Update didn't apply** — relaunch the app and use Settings > Updates > Update now. If your antivirus quarantined the download, restore it and add an exclusion for the install folder.
- **Something else** — open an issue on the [Issues tab](https://github.com/NexusForgeLab/Voxora-releases/issues) with your version (Settings > Updates shows it) and what happened.

## About This Repo

This repository hosts binary releases only. The Voxora source code is maintained privately by NexusForge Labs. Bug reports and feature requests are welcome on the Issues tab here.

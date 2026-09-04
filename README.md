# Hearth — downloads

This repo exists for one reason: to hand you a Hearth build without an account,
a collaborator invite, or a login. **Hearth's source lives in a private repo**;
its binaries are free to grab, because a personal agent you cannot download is
not one you own.

> **Hearth** is a personal AI agent that runs on your own computer and reaches
> your phone from anywhere — no router configuration, no account, and no data
> stored on anyone else's infrastructure. Install the desktop app, scan a QR
> code, talk to your agent from your phone.

## Get the app

Grab the latest build from the [**Releases**](https://github.com/mmorris35/hearth-release/releases)
page.

| Platform | File | Notes |
|---|---|---|
| macOS (Apple Silicon) | `Hearth_*_aarch64.dmg` | Unsigned — right-click → Open the first time (see below). |
| macOS (Intel) | `Hearth_*_x64.dmg` | Same. |
| Linux (Debian/Ubuntu) | `Hearth_*_amd64.deb` | `sudo apt install ./Hearth_*_amd64.deb` — pulls the webkit/tray deps. |
| Windows | `Hearth_*_x64.msi` | SmartScreen will warn (unsigned) — "More info" → "Run anyway". |

**These builds are not yet code-signed or notarised.** Your OS will warn you the
first time you open one. That warning is real and worth reading; the reason the
builds are unsigned is tracked in the source repo, not hidden.

## After you install

There is nothing to configure to start. A fresh Hearth defaults to driving your
own local [Claude Code](https://claude.ai) install; if it is missing or not
signed in, the app window tells you the exact command. To use any other model,
point it at an OpenAI-compatible or Anthropic endpoint in the app's Model panel.

Everything else — the identity interview, pairing your phone, where your agent's
memory lives — happens in the app window. No terminal required.

## What this repo does *not* contain

No source code, no keys, no telemetry. Only release notes and the built
installers. If a release asset is all you can see here, that is by design.

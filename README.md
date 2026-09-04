# Hearth

A personal AI agent that runs on your own computer, and reaches your phone from
anywhere — with no router configuration, no account, and no data stored on
anyone else's infrastructure.

Install the desktop app. Scan a QR code. Talk to your agent from your phone.

**This is the downloads repo.** Hearth's source lives in a private repo; the
binaries are free to grab, because a personal agent you cannot download is not
one you own. Everything below describes what you're installing.

## Who this is for

**People who want an assistant without an audience.** You want to ask an AI about
your health, your finances, your family, or your work, and you do not want that
question sitting in a vendor's logs. Hearth answers from your own machine.

**Developers who want a real local agent.** Not a chat window — an agent with
persistent memory on disk, your choice of model, and a phone client, without
standing up a server or opening a port.

**Small teams and practices under a duty of confidentiality.** Lawyers, clinicians,
accountants, anyone who cannot paste a client's information into someone else's
service. The data boundary here is physical, not contractual.

## Design commitments

- **No network configuration.** The desktop dials out; nothing is ever forwarded in.
- **We operate no infrastructure.** Transport is [iroh](https://github.com/n0-computer/iroh),
  using its public relays. There is no service of ours to breach.
- **End-to-end encrypted.** Relays carry ciphertext they cannot read.
- **Your agent's memory lives on your disk.** It is never uploaded.
- **No accounts, no email, no magic links.** A paired device key *is* the credential; the QR is only an address.
- **Any model.** Local or cloud, OpenAI-compatible or Anthropic.

## What you're trusting

Most privacy tools ask you to trust a policy. This one is arranged so there is
less to trust.

| The question | The answer |
|---|---|
| Can you read my conversations? | No. There is no server of ours in the path. We could not read them if we wanted to. |
| Where does my agent's memory live? | In your Hearth home directory on your own disk. It is never uploaded. |
| Do I need an account? | No. No email, no password, no magic link. A paired device key is the credential. |
| Do I have to configure my router? | No. The desktop dials out. Nothing is ever forwarded in. |
| Who can reach my agent? | Only devices you have paired. Revoke one and it is gone immediately. |
| What does the relay see? | Ciphertext it cannot read. It carries bytes between two endpoints and knows nothing about them. |
| What if I lose my phone? | Revoke that device key. Nothing on the phone is a credential once revoked. |
| Which model does it use? | Yours. Local or cloud, OpenAI-compatible or Anthropic. Swap it whenever you like. |
| What happens if this project stops? | Your install keeps working. It is your binary, your disk, your model. There is no license check and no server to switch off. |
| So you depend on nothing? | Not quite — the transport uses [iroh](https://github.com/n0-computer/iroh)'s public relays, operated by n0. They carry only ciphertext, but they are a dependency and it would be dishonest to pretend otherwise. Direct connections skip them when the network allows. |

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

The first thing Hearth does is ask who it should be — a short interview (every
question is skippable) that becomes plain-markdown persona and memory files on
your disk. Then scan the QR the app shows, pair your phone with a one-time code,
and talk to your agent from anywhere. Everything happens in the app window; no
terminal required.

## Why this exists

Over the past year I built a fleet of agents for myself. It got to the point where
I authored complete apps and frameworks from behind the backstop at a Little League
game, with nothing but a phone and Telegram.

Then I tried to give that to my friends and family, and I couldn't. Not because they
lacked the ideas — because the setup is brutal. Servers, tokens, port forwarding, a
bot framework, a machine that stays up, and a dozen decisions nobody should have to
make to talk to their own computer.

That's what Hearth is. Install the desktop app, scan a QR code, and the thing I have
is the thing you have.

The requirement was that it work for anyone, without router edits and without
needing to know what a relay is. Privacy is a side effect of meeting that
requirement honestly. Once you decide someone should never have to configure a
network or create an account, you have already ruled out holding their data — the
architecture that is easiest to hand to your mother is also the one with nothing in
the middle.

I want more people to have this power in their phone.

## What this repo does *not* contain

No source code, no keys, no telemetry. Only release notes and the built
installers. If a release asset is all you can see here, that is by design.

## Why the name

The hearth was the part of a house that kept working whether or not anyone was
watching it, and everything else arranged itself around it.

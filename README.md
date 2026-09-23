# Hearth for Windows

A personal AI agent that runs on your own PC, and reaches your phone from
anywhere — with no router configuration, no account, and no data stored on
anyone else's infrastructure.

Install the app. Talk to your agent. Scan a QR code and take it with you.

**This is the downloads repo.** Hearth's source lives in a private repo; the
Windows installer is free to grab, because a personal agent you cannot download
is not one you own.

---

## Download

**[⬇ Download the latest Hearth for Windows](https://github.com/mmorris35/hearth-release/releases/latest)**

On that page, under **Assets**, click **`Hearth_0.2.0_x64_en-US.msi`**.

> ### ⚠️ Read this first — the one thing that stops most people
> When you open the installer, Windows shows a **blue "Windows protected your
> PC"** box. **This is not a virus warning, and Hearth is not broken.** Windows
> shows it for *any* app that hasn't paid for a code-signing certificate yet. The
> button to continue is hidden: click **More info**, then **Run anyway**.

---

## 1. Install it

Double-click the `.msi` you downloaded.

1. On the blue **"Windows protected your PC"** screen, click **More info**.
2. Click **Run anyway**.
3. Click through the installer (**Next → Install → Finish**).

Hearth is now in your Start menu.

## 2. Give it a brain (one time)

Hearth needs an AI model to think with. The simplest option uses **Claude Code**
with your existing Claude account:

1. Open **PowerShell**: click Start, type `PowerShell`, press Enter.
2. Copy-paste this line and press Enter:
   ```powershell
   irm https://claude.ai/install.ps1 | iex
   ```
3. When it finishes, type `claude` and press Enter. A browser opens — **sign in
   with your Claude account**. Once it says you're signed in, close the window.

That's the exact command Hearth shows you if it can't find Claude Code, so you
can't get it wrong.

> **Prefer an API key instead?** Open Hearth → **Model** settings → pick a
> provider → paste your key.

## 3. Meet your agent

Open **Hearth** from the Start menu. On first run it **asks who it should be** —
a few short questions (what to call you, what to call it, how it should talk,
what it's for), and every one is skippable. Answer them and you're immediately
talking to your own assistant, which remembers you between sessions.

The top of the window tells you whether the model is connected and signed in; if
anything's off, it shows the exact fix.

## 4. (Optional) Talk to it from your phone

1. In Hearth, click **Pair a device**. A QR code appears with a short code.
2. On your phone, point the camera at the QR code and open the link.
3. Type the short code from the Hearth window into your phone once.

Your phone now talks to the same agent, from anywhere — no app store, no account.
Add it to your home screen for an app-like icon. **Lost your phone?** Open
Hearth → device list → **Revoke**, and it can no longer reach your agent.

## Everyday use

- **Just type.** Ask it anything; it answers from your PC.
- **It remembers you.** What it learns lives in plain text under
  `%USERPROFILE%\wiki\` — open and edit any time.
- **It runs in the background.** Closing the window hides Hearth to the tray (by
  the clock, bottom-right). To fully stop it, right-click the tray icon → **Quit**.

## If something looks wrong

| What you see | What to do |
|---|---|
| "Windows protected your PC" | Expected (unsigned). **More info → Run anyway**. |
| Hearth says Claude Code is missing or not signed in | Redo **step 2**; the window shows the exact command. |
| The agent won't answer | Check the top of the window — it says whether the model is reachable and signed in. |
| Phone won't connect | Re-pair: click **Pair a device** again and scan the fresh QR (codes expire after a few minutes). |

---

## What you're trusting

Most privacy tools ask you to trust a policy. This one is arranged so there is
less to trust.

| The question | The answer |
|---|---|
| Can you read my conversations? | No. There is no server of ours in the path. We could not read them if we wanted to. |
| Where does my agent's memory live? | In your Hearth folder on your own disk. It is never uploaded. |
| Do I need an account? | No. No email, no password, no magic link. A paired device key is the credential. |
| Do I have to configure my router? | No. The desktop dials out. Nothing is ever forwarded in. |
| Who can reach my agent? | Only devices you have paired. Revoke one and it is gone immediately. |
| What if I lose my phone? | Revoke that device key. Nothing on the phone is a credential once revoked. |
| Which model does it use? | Yours. Local or cloud, OpenAI-compatible or Anthropic. Swap it whenever you like. |
| What happens if this project stops? | Your install keeps working. It is your binary, your disk, your model. No license check, no server to switch off. |

## Why this exists

Over the past year I built a fleet of agents for myself. It got to the point
where I authored complete apps and frameworks from behind the backstop at a
Little League game, with nothing but a phone.

Then I tried to give that to my friends and family, and I couldn't — not because
they lacked the ideas, but because the setup is brutal: servers, tokens, port
forwarding, a machine that stays up, a dozen decisions nobody should have to make
to talk to their own computer.

That's what Hearth is. Install the app, and the thing I have is the thing you
have. The requirement was that it work for anyone, without router edits and
without needing to know what a relay is. Privacy is a side effect of meeting that
requirement honestly: the architecture that is easiest to hand to someone you
love is also the one with nothing in the middle.

## What this repo does *not* contain

No source code, no keys, no telemetry. Only the built Windows installer and
release notes. If a release asset is all you can see here, that is by design.

## Why the name

The hearth was the part of a house that kept working whether or not anyone was
watching it, and everything else arranged itself around it.

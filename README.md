# Aria

**An always-listening voice assistant for Windows 11.**
Say "Aria," wait for the chime, and talk. She answers out loud and can run your
PC — apps, windows, volume, files, timers, the web — moderate a Discord server,
and even take the controls in a game.

*Aria by CSVRStudios · www.csvrstudios.com/aria*

---

## What Aria can do

- **Runs your PC by voice** — open and close apps, control volume and media,
  manage windows, take screenshots, read your screen, type and edit text, work
  your clipboard, run keyboard shortcuts, check system stats and wifi.
- **Remembers things** — notes, to-dos, and facts you tell her, recalled later.
- **Timers and reminders** — countdowns, alarms, "remind me at 3pm," pomodoro,
  a stopwatch.
- **Answers questions** — weather, math, conversions, definitions, quick facts.
- **Moderates Discord** — through your own bot: roles, channels, messages,
  timeouts, kicks and bans, voice moves, member watching, server stats.
- **Automates games** — a hybrid autopilot, an auto-clicker, macro record and
  replay, and "click the thing I describe."
- **Around 200 abilities in total**, and it grows without hitting limits thanks
  to smart per-message tool routing.

See **VOICE-COMMANDS.md** for the full command list.

---

## How it works

Aria listens locally for the wake word using a small offline model (free, no
cloud). Once she hears "Aria," she records your request and sends it to OpenAI:
**Whisper** turns speech to text, a **fast OpenAI model** decides what to do (and
picks the right tools), and **OpenAI TTS** speaks the reply back in a natural
voice. A translucent glass bar shows her state — idle, listening, thinking,
speaking, or driving a game.

Only the wake word is always-on and local. Nothing is sent anywhere until you
say "Aria" and speak a request.

---

## Requirements

- **Windows 11** (also works on Windows 10)
- **An OpenAI API key** — Aria asks for it on first run. Usage is billed to you
  by OpenAI, usually a cent or two per interaction. Set a spending limit in your
  OpenAI account if you want a hard cap.
- For Discord features: **your own Discord bot** added to your server (see below).

The packaged `.exe` bundles everything else — you don't need to install Python.

---

## Getting started (for users)

1. Download the latest `Aria-exe.zip` from the Releases page.
2. Unzip it somewhere permanent (not inside the zip viewer).
3. Double-click **Aria.exe**.
   - Windows will show a blue **"Windows protected your PC"** box. Click
     **More info -> Run anyway**. This is normal and expected for a small indie
     app that isn't code-signed — Windows shows this warning for any new app it
     doesn't yet recognize. Aria is safe; the warning is about the app being new,
     not about it being harmful.
4. A welcome window appears — paste your OpenAI API key and click continue.
5. The bar appears. Say "Aria" and start talking.

Aria puts a shortcut on your Desktop automatically. To keep it handy, right-click
that shortcut and choose **Pin to taskbar** or **Pin to Start**.

The first launch downloads a small voice model — give it a minute, it only
happens once.

---

## Setting up Discord (optional)

Discord features need your own bot, because a bot can only act in servers you've
added it to.

1. Go to the Discord Developer Portal and create an application, then a bot.
2. Turn on the **Server Members** and **Message Content** intents.
3. Copy the bot token and invite the bot to your server with admin permissions.
4. Set the token as an environment variable named `DISCORD_BOT_TOKEN`, then
   restart Aria.

---

## Auto-updates

Aria checks for new versions on startup and shows an **Update** button on the bar
when one is available. Clicking it downloads the new version and opens your
Downloads folder — it never installs anything silently.

---

## Privacy & safety

- **Aria cannot delete, move, rename, or overwrite files.** Those abilities
  don't exist in the code, so no misheard command can cause data loss. She can
  find and open files, and that's the limit.
- **Irreversible Discord actions** (kick, ban, delete role, delete channel,
  purge, disconnect everyone) always ask you to confirm out loud first.
- **No secrets in the code.** Your OpenAI key and Discord token live only in your
  environment, never in the app or in copies you share.
- **Your voice stays local until you invoke her.** Only the offline wake-word
  model is always-on; audio is sent to OpenAI only after you say "Aria."

---

## Troubleshooting

- **"Windows protected your PC"** — click More info -> Run anyway. Normal for a
  new, unsigned indie app.
- **A DLL error on launch** — keep `Aria.exe` inside its folder next to the
  `_internal` folder; don't move the exe out on its own.
- **Aria doesn't hear the wake word** — check your microphone is set as the
  default input device in Windows sound settings.
- **Autopilot input doesn't register in a game** — run Aria as administrator,
  and use Borderless Windowed mode. Single-player only.
- **Discord commands say "I can't"** — make sure the bot token is set and the bot
  is in your server with the right permissions and intents enabled.

---

## Credits

Built by **CSVRStudios** — www.csvrstudios.com/aria

Powered by OpenAI (Whisper, a fast OpenAI model, and TTS) and faster-whisper for
the local wake word.

# MuteBind

[![VirusTotal: 0/69 clean](https://img.shields.io/badge/VirusTotal-0%2F69%20clean-brightgreen?logo=virustotal&logoColor=white)](https://www.virustotal.com/gui/file/8bea5e7bb30f83c0103e16f0053b487f6c98ffed449265f7430e999ab79e2fe5)
[![Downloads](https://img.shields.io/github/downloads/veax-project/MuteBind/total?logo=github&label=downloads)](https://github.com/veax-project/MuteBind/releases)
[![Platform: Windows](https://img.shields.io/badge/platform-Windows-0078D6?logo=windows&logoColor=white)](#)
[![Free to use](https://img.shields.io/badge/price-free-success)](#)

**Mute and unmute your Discord mic with a single key — the one _you_ choose.**

MuteBind is a tiny Windows app that lives in your system tray. Pick any key (or combo:
`F12`, `Ctrl+Alt+M`, …), and one press mutes or unmutes your Discord mic — **even while
you're in a fullscreen game**, without switching to the Discord window.

It also turns your **PS5 DualSense's mute button** into a Discord mute toggle, with the
orange LED lighting up when you're muted — just like on PS5.

<p align="center"><i>One key. Your mic. Everywhere in Windows.</i></p>

---

## ✨ Features

- 🎙️ **Mute / unmute Discord** with a single press of the key of your choice.
- 🎮 **PS5 DualSense mute button** (DualSense & DualSense Edge, over USB): the mic button
  toggles Discord **and glows orange** when you're muted — exactly like on PS5.
- 🔔 **On-screen mute notification** (FluentFlyout style) — position, duration, fade speed and opacity all adjustable.
- 🔄 **Stays in sync with Discord**: reads Discord's real mic state, so the notification and controller LED are always right — even if you also click mute in Discord itself.
- 🎛️ **Simple UI**: click "Change…", press your key, save. Done.
- 🌍 **Works everywhere**: a low-level keyboard hook catches your key even when a game has
  focus (use *borderless windowed* for best results).
- 📌 **Lives in the system tray**, quiet and out of the way. Closing the window doesn't quit.
- 🚀 **Starts automatically with Windows** (optional, one click).
- 🔒 **No account, no login, no telemetry.** 100% local.

## 🚀 Install

1. Download `MuteBind.exe` from the [Releases](../../releases) page.
2. Double-click it. That's it — no installation.
   *(Windows SmartScreen may warn because the exe isn't code-signed →
   "More info" → "Run anyway".)*

## 🛡️ Is it safe?

Yes — and you don't have to take my word for it:

- **[Clean on VirusTotal: 0 / 69 detections](https://www.virustotal.com/gui/file/8bea5e7bb30f83c0103e16f0053b487f6c98ffed449265f7430e999ab79e2fe5)** — VirusTotal indexes by file hash, so that link always shows the current result for this exact `.exe`. Scan it yourself anytime.
- **No account, no telemetry, no network calls** — it only talks to Discord (by simulating a keystroke) and to your controller (USB HID), all locally.
- **Single-purpose** — one small tool that does exactly one thing.

The exe isn't code-signed (signing certificates cost money), so **Windows SmartScreen may warn you** the first time — that's normal for indie apps. Click "More info" → "Run anyway".

## 🎮 Usage (once, 3 minutes)

On first launch, the settings window opens:

### 1. Set up Discord (once)
Click **"Set up Discord"** and follow the on-screen path:
- Discord → **Settings** → **System** → **Custom Keybinds** → **Add a Keybind**
- **Keybind action**: **"Toggle Mute"**
- Record the shortcut: **`Ctrl + Alt + Shift`**

> This combo is deliberately rare so it never clashes with your games. It's the internal
> "pipe": you'll only ever use **your own** key.

### 2. Choose your key
Click **"Change…"**, press whatever key you want, then **"Save"**.

### 3. Done
Close the window. MuteBind stays in the tray. Press your key anywhere → your Discord mic
mutes / unmutes.

## 🎮 PS5 DualSense controller

Plug your DualSense in **over USB**: MuteBind detects it automatically, and the **mute
button** (below the PS logo) becomes a Discord mute toggle. The **orange LED** around the
button lights up when you're muted, just like on PS5.

- Toggle it from the tray menu: **"DualSense mute button"**.
- Your keyboard key and the controller button both work at the same time.
- ⚠️ If **Steam Input** is enabled for PlayStation controllers, Steam can grab the
  controller exclusively and stop MuteBind from reading it. Disable Steam Input for the
  DualSense if the button doesn't respond.

## ⚙️ How it works

MuteBind catches your key with a global keyboard hook (`WH_KEYBOARD_LL`), then simulates,
at the system level, the shortcut Discord has registered as *Toggle Mute*. Discord picks
that combo up globally, including while a game is in the foreground — so **your** key
drives Discord's mute without Discord needing to be the active window.

The DualSense support reads the controller's raw HID reports to detect the mute button and
drives the mute LED over HID output reports.

> **Fullscreen exclusive game?** Some games block global hotkey detection (Discord
> included). Switch the game to **borderless windowed** — it's the norm today and has
> virtually no performance cost.

## 📁 Config

Settings are stored in `%AppData%\MuteBind\config.json`.

## 📄 License

**Proprietary — © 2026 Veax. All rights reserved.**

MuteBind is **free to download and use**. You may not copy, modify, redistribute,
sell, or reverse-engineer it. See [LICENSE](LICENSE) for details.

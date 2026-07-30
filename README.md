# StreamFlight

**A Windows pre-stream workspace and health-check companion for streamers.**

> ### 🎥 Streamer tools by ValoCookie
> **StreamFlight** handles the boring setup checks before going live.  
> Play osu!? **[Check out osu!Requests →](https://github.com/ValoCookie/osu-Requests)** for Twitch map requests, queues, filters and OBS request overlays.

---

## Current build

**Current GitHub build: v1.0.9**

[**Open the latest GitHub releases →**](https://github.com/ValoCookie/streamflight/releases)

---

# What it does

StreamFlight is for the stuff around the stream.

It helps keep recurring setup steps in one place so you can catch things like the wrong OBS state, a missing device, a forgotten app or a broken recording setup **before chat becomes the first person to tell you**.

It deliberately does **not** start or stop your live broadcast. OBS stays in control of the actual stream button.

---

## Applications

Create a reusable stream workspace and keep the apps you need for that setup together.

StreamFlight can:

- launch applications in a chosen order
- keep background/helper apps separate from normal apps
- track tools used around the stream
- clean up eligible helper applications at the end of the session

---

## Stream Extras

Some stream setups need more than OBS and a browser.

The **Stream Extras** area can include things such as:

- **LurkBait Twitch Fishing**
- Steam games and Steam launch URIs
- `.url` shortcuts
- **JKPS**
- an optional JKPS `.cfg` / theme file
- standalone helper/config files such as `.cfg`, `.ini`, `.json`, `.txt`, `.yaml` and `.yml`

StreamFlight launches or tracks these tools; it does not rewrite their configs.

---

## Websites

Keep the websites you routinely open before a stream together with the rest of the setup instead of hunting through bookmarks every time.

The Websites page is scrollable for longer setups.

---

## Checklist

Build a reusable checklist for the things you personally want to verify before going live.

The Checklist page is scrollable, and checkbox feedback is designed to repaint immediately instead of feeling delayed while other status work is happening.

---

## Stream Tools

The **Stream Tools** page combines OBS, Windows, Twitch and device checks into one health snapshot.

It can check things such as:

- whether OBS is running
- OBS WebSocket connectivity for deeper OBS checks
- microphone / desktop-audio expectations
- configured OBS scenes/sources
- expected Windows devices
- Windows pending-restart state
- Twitch stream information where configured

Basic **“is OBS open?”** detection does not depend on WebSocket. StreamFlight checks the local Windows process first, with additional Windows fallbacks where needed.

The Stream Tools page is scrollable too.

---

## OBS test recording

**TEST RECORDING** starts a short local OBS recording and stops it automatically.

It is meant for checking the actual microphone, game, camera and capture output before going live.

It refuses to interrupt an already-active recording and never starts or stops the live broadcast.

---

## Stream safety / PANIC

You can configure an OBS panic/BRB scene, optional microphone muting and an optional global hotkey.

- **PANIC** stores the current scene/mute state, applies the configured safety actions and switches to the panic scene.
- **RESUME** restores the captured scene and mute state.

The workflow is intentionally reversible.

---

## OBS detection vs OBS WebSocket

StreamFlight treats these as two different things.

**OBS running**
- detected locally through Windows process checks
- does not require WebSocket

**Deeper OBS information/actions**
- scenes
- profile
- recording state
- sources
- audio checks
- panic/BRB actions

These require a working OBS WebSocket connection.

This prevents a WebSocket configuration problem from being incorrectly reported as “OBS is not running.”

---

## osu! players + osu!Requests

StreamFlight is a general streaming utility, so osu!Requests is optional.

When osu!stable or osu!lazer is relevant, StreamFlight can introduce the companion app.

If osu!Requests is already installed, StreamFlight can optionally reuse its Twitch connection for supported stream metadata/health checks.

The integration is never required.

---

# Core workflow

1. Choose a Stream Setup
2. Add applications and Stream Extras
3. Add websites
4. Build your checklist
5. Configure optional OBS expectations and devices
6. Click **START SESSION**
7. Resolve warnings
8. Optionally run **TEST RECORDING**
9. Start the actual broadcast from OBS when you are ready
10. Use **END SESSION** afterward to clean up helper applications StreamFlight launched and is allowed to close

---

# OBS setup

For deeper OBS checks/actions, enable:

**Tools → WebSocket Server Settings**

in OBS.

OBS WebSocket 5.x commonly uses port `4455`; enter your actual port/password inside StreamFlight along with any expected profile, scene collection, starting scene, sources or panic settings you want checked.

---

# Privacy / product boundary

StreamFlight stores its settings locally.

It may perform explicitly configured helper actions such as:

- OBS health queries
- local test recordings
- panic/BRB scene switching
- reversible microphone muting
- launching configured apps, websites and Stream Extras

**It never starts or stops the live broadcast.**

---

# Related project

**[osu!Requests](https://github.com/ValoCookie/osu-Requests)** — Twitch → osu! map requests for osu!stable and osu!lazer.

---

# Project status

StreamFlight is actively developed.

The **current GitHub build is v1.0.9**.

Feedback, bug reports, weird PC-specific behavior and cursed streamer setups are all welcome. 💜

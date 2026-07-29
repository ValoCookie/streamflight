# StreamFlight

**A Windows pre-stream workspace and health-check companion for streamers.**

> ### 🎥 Streamer tools by ValoCookie
> **StreamFlight** prepares and checks the stream setup around OBS.
> Play osu!? **[Check out osu!Requests →](https://github.com/ValoCookie/osulazer-twitch-map-request-bot)** for Twitch map requests, queues and OBS request overlays.

---

StreamFlight helps you get the boring pre-stream stuff out of your head before you hit **Go Live**: launch the right apps and websites, run reusable checklists, verify OBS, check expected Windows devices, test a short local recording, inspect Twitch stream info and keep a reversible panic / BRB action ready.

It deliberately does **not** start or stop your live broadcast. OBS remains in control of the actual stream button.

## Highlights

- reusable stream setup profiles
- ordered app launching and background-helper handling
- websites and manual pre-stream checklists
- OBS WebSocket health checks
- short local OBS test recording
- expected-device checks
- Windows pending-restart warning
- optional Twitch title / category / tag checks
- reversible OBS panic / BRB scene + microphone safety action
- advanced optional custom actions
- local-first configuration

## osu! players + osu!Requests

StreamFlight is a general streaming utility, so it does not advertise osu!Requests to everybody.

When StreamFlight detects **osu!stable**, **osu!lazer**, or an existing osu!Requests installation, it can show a one-time introduction:

> **Howdy, do you play osu!?**

The short prompt explains what osu!Requests does and waits five seconds before its buttons or close action unlock, giving the streamer a moment to actually read it instead of dismissing it by accident.

If osu!Requests is already installed, StreamFlight can optionally reuse its Twitch connection for stream metadata and health checks. If it is not installed, the prompt links to the osu!Requests GitHub project. The integration is always optional.

[**Open osu!Requests on GitHub →**](https://github.com/ValoCookie/osulazer-twitch-map-request-bot)

## Stream Tools

The **Stream Tools** page combines OBS, Twitch, device and Windows checks into one health snapshot. It can verify configured OBS expectations, microphone / desktop-audio presence, required scene sources, expected Windows devices, Twitch stream information and whether Windows is waiting for a reboot.

Health checks report PASS / WARNING / FAIL-style results instead of trying to replace OBS.

## OBS test recording

**TEST RECORDING** starts a short local OBS recording and stops it automatically. It is designed for checking actual microphone, game, camera and capture output before going live.

It refuses to interrupt an already-active recording and never starts or stops the live stream.

## Stream safety / PANIC

You can configure an OBS panic scene, optional microphone muting and an optional global hotkey.

- **PANIC** stores the current scene / mute state, mutes configured mic-like OBS inputs and switches to the panic scene.
- **RESUME** restores the captured scene and mute state.

This is intentionally reversible.

## Core workflow

1. Choose a Stream Setup.
2. Add applications and arrange their launch order.
3. Mark helper applications as Background where appropriate.
4. Add websites and manual checklist items.
5. Configure optional OBS expectations, devices and Stream Tools.
6. Click **START SESSION**.
7. Resolve any warnings and optionally run **TEST RECORDING**.
8. Start the actual broadcast from OBS when you are ready.
9. Use **END SESSION** afterward to clean up helper applications StreamFlight launched and is allowed to close.

## Download / releases

Development builds will be published through **GitHub Releases**, allowing smaller updates to ship without waiting for a Microsoft Store submission.

[**Open StreamFlight releases →**](https://github.com/ValoCookie/streamflight/releases)

## Run from Python

```bat
py -m pip install -r requirements.txt
py StreamPreflight.py
```

## Build the Windows app + installer

Run:

```bat
BUILD_INSTALLER.bat
```

This creates:

```text
dist\StreamPreflight.exe
installer_output\StreamPreflight_Setup_v1.0.5.exe
```

Inno Setup 6 is required for the installer step.

## OBS setup

Enable **Tools → WebSocket Server Settings** in OBS. OBS WebSocket 5.x normally uses port `4455`. Enter the port / password and any expected profile, scene collection, starting scene, required sources or panic settings inside StreamFlight.

## Privacy / product boundary

StreamFlight stores its settings locally. It may perform explicitly configured OBS-side helper actions such as health queries, local test recordings, panic / BRB scene switching and reversible microphone muting.

**It never starts or stops the live broadcast.**

## Related project

- [**osu!Requests** — Twitch → osu! map requests for stable and lazer](https://github.com/ValoCookie/osulazer-twitch-map-request-bot)

## Project status

StreamFlight is still in active beta development. Feedback, bug reports and weird edge cases are welcome.

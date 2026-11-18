![hero](img/hero.png)

# Bilibili Live

**[This App on AWTRIX Hub](https://awtrix.de/script/LzgkgCuRbhs5)**

A compact Berry app for AWTRIX NG / TC001 (ESP32) that shows a Bilibili room's streaming status, online viewers, and follower count.

## Highlights

- While streaming: Streaming icon + current online viewers. Offline: Normal icon + follower count.
- Follower mode: enable `Follower Mode` and fill `UID` to show follower count only.
- Optional in-app second page while streaming: with `Show Follower Count` enabled, the streaming page takes 70% of the display time and the follower page 30%; with it disabled, only the streaming page is shown.
- Clean integer formatting with automatic `K / M / G / T` units, e.g. `999M`.
- Checks the API `code` field (`0` = success). A failed request retries every 5 seconds; after 3 failed attempts the app shows `Check ID` in orange.
- Inherits the system `Text Color`, scrolling behavior, and transition effect.
- One complete HTTP request per refresh with regex extraction; no allocation in `draw()`, so it stays friendly to small-heap devices.

## Installation

You just click the button **Send to AWTRIX**.

## Configuration

Open **Apps**, find `Bilibili Live`, and click the gear icon:

| Setting | Default | Description |
|---|---|---|
| `Follower Mode` | `false` | Only show Follower Count using UID below |
| `UID` | `9617619` | The number from `space.bilibili.com/<uid>`; used when `Follower Mode` is on |
| `Room ID` | `6` | The number from `live.bilibili.com/<roomid>`; change this to your room; used when `Follower Mode` is off |
| `Normal Icon` | `bilibiliblink` | Icon shown when offline |
| `Streaming Icon` | `bilibililive` | Icon shown while streaming |
| `Show Follower Count` | `true` | Show a follower-count page after the streaming page while streaming |
| `Refresh` | `1` min | Data refresh interval |
| `Duration` | `10` s | App display time; `0` uses the system per-app duration |

Saving settings restarts the app. Both icons are declared with `@icons`; install icons with the same names via the Web UI if they are missing.

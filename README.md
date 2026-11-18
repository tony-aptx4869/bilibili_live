![hero](img/hero.png)

# Bilibili Live

A compact Berry app for AWTRIX NG / TC001 (ESP32) that shows a Bilibili room's live status, online viewers, and follower count.

## Highlights

- While live: live icon + current online viewers. Offline: normal icon + follower count.
- Optional in-app second page while live: with `Show Fans` enabled, the live page takes 70% of the display time and the fans page 30%; with it disabled, only the live page is shown.
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
| `Room ID` | `6` | The number from `live.bilibili.com/<roomid>`; change this to your room |
| `Normal Icon` | `bilibiliblink` | Icon shown when offline |
| `Living Icon` | `bilibililive` | Icon shown while live |
| `Refresh` | `1` min | Data refresh interval |
| `Duration` | `10` s | App display time; `0` uses the system per-app duration |
| `Show Fans` | `true` | Show a fans page after the live page while streaming |

Saving settings restarts the app. Both icons are declared with `@icons`; install icons with the same names via the Web UI if they are missing.

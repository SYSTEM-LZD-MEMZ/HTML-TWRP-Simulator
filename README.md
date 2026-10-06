# HTML TWRP Simulator

A single-file TWRP recovery simulator that runs entirely in your browser. One HTML file, no build step, no dependencies, no internet needed.

I built this because I've always liked how TWRP looks — flat, square, cold, honest. So I tried to see if I could get that feeling into a browser tab. Then I kept adding things. Now it's this.

## How to use it

Grab `x992.html` from the [Releases page](https://github.com/SYSTEM-LZD-MEMZ/HTML-TWRP-Simulator/releases), open it in any browser. That's it. Phone or desktop, online or offline, it works.

## What's inside

**Normal Mode** — the TWRP part.

You get the full menu: Install, Wipe, Backup, Restore, Mount, Settings, Reboot, Advanced. Flashing uses a swipe-to-confirm bar and can fail randomly, like the real thing. Three failures in a row and you're bricked — you can recover by running `fastboot flash boot boot.img` in the terminal.

There's also a Terminal with a small command set, an ADB Sideload page, a Maintenance Mode with a timer, an achievements system, and a System Info page that reads real data from your device: battery, network type, connection speed, location, camera, microphone, ambient light, motion sensor, and weather via a public API when you're online.

There's a fake Android desktop with Camera, Photos, Messages, Phone, Browser, Settings, and Files apps. There's a lock screen. There's a notification shade.

**Story Mode** — a short one.

Six people get lost in a "flashing world" where the only way to clear monsters is to flash ROMs. Only three of you walk out. Your choices decide who dies, how, and whether the ending is a win or a loss. There are 6 endings, all of which end the same way: you wake up in bed, reach for your phone, and something is on the screen. I won't spoil the rest.

**Language** — English by default, Chinese optional.

You can switch from the start menu, the TWRP topbar, or the story topbar. Your choice persists. Logs (`I:`, `E:`, `W:` prefixed) stay in English no matter what, because that's what real TWRP logs look like.

## Under the hood

No framework. No bundler. No CDN. All icons are emoji and Unicode characters. All animations are pure CSS — no canvas, no WebGL, no 3D engine.

State lives in `localStorage`: achievements, settings, virtual files, photos, messages, all survive a page refresh.

Real-world data uses standard Web APIs (Battery, Network Information, Geolocation, MediaDevices, DeviceMotion, AmbientLightSensor when available). Weather and random facts use two free public APIs, with offline fallbacks when there's no network.

## Running it locally

```bash
git clone https://github.com/SYSTEM-LZD-MEMZ/HTML-TWRP-Simulator.git
cd HTML-TWRP-Simulator
# open x992.html in a browser

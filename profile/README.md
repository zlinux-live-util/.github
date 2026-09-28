# zlinux-live-util

Native-first odds and ends for Linux live streaming — the small tools a streamer
needs around a broadcast, in the form Linux should already handle well.

[简体中文](https://github.com/zlinux-live-util/.github/blob/main/profile/README.zh-CN.md)

## Why this organization exists

Streaming tooling on Linux is too often solved by embedding a browser. It works,
but it is not a *cheap* solution: a CEF- or Electron-based source spends hundreds
of megabytes of RAM and a slice of CPU to draw something that is usually a simple
render. RAM is no longer cheap in the AI era, and "just add a browser" is a bill
that is paid on every stream.

We think the native path is both possible and better here. A small process using
the distribution's own libraries — PipeWire, cairo, pango, D-Bus — can do the same
job in a few megabytes, start instantly, and stay out of the encoder's way.

The long-term goal: an ordinary streamer, not a distribution maintainer, can move
the entire streaming stack to Linux and stay there.

## What we hold to

- **Native before convenient.** System libraries, not a bundled runtime.
- **Resource budgets are part of the feature.** Memory and CPU are stated, measured
  and kept small enough to coexist with a game and an encoder on one machine.
- **No silent failure.** If something cannot work, it should say so; the projects
  here document the pitfalls that cost real debugging time.

## Projects

### [pw-mpris-visualcard](https://github.com/zlinux-live-util/pw-mpris-visualcard)

Renders the track playing on your machine as a card and publishes it to OBS as a
PipeWire video node.

- one process, no child processes, no browser, no HTTP
- renders nothing at all while no consumer is connected (≈0.25% CPU idle)
- 6–25 MB private memory; the card is drawn with cairo + pango
- synced lyrics from MPRIS, rotating cover, progress ring; any output size, adjustable frame-rate ceiling
- distribution libraries only — no language package manager, no bundled runtime
- MIT licensed; pairs with [obs-pwvideo](https://github.com/tasokait/obs-pwvideo) as the OBS source

```bash
git clone https://github.com/zlinux-live-util/pw-mpris-visualcard
cd pw-mpris-visualcard && make
```

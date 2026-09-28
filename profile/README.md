# zlinux-live-util

Native-first utilities for Linux live streaming.

We build the small pieces a broadcast needs around it, natively, on each
distribution's own libraries. Embedding a browser to draw a widget costs hundreds
of megabytes and a slice of CPU on every stream; a small native process does the
same job in a few megabytes. The goal is that an ordinary streamer — not a
distribution maintainer — can move the whole streaming stack to Linux and stay
there.

[简体中文](https://github.com/zlinux-live-util/.github/blob/main/profile/README.zh-CN.md)

## Projects

| Project | Description |
| --- | --- |
| [pw-mpris-visualcard](https://github.com/zlinux-live-util/pw-mpris-visualcard) | Now-playing card for OBS, published as a PipeWire video node. One process, no browser, no child processes, no HTTP. |

Contributions are welcome; each project's README states what a patch must include.

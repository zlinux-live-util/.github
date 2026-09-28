# Avatar attribution

`avatar.svg`, `avatar-512.png`, `avatar-64.png` and `avatar-32.png` are a custom
mark: a starfield purple ground with a display on it. The glyph geometry is
composed from [Lucide](https://lucide.dev) v1.48.0 (via the `lucide-static`
package) — the `monitor` frame and stand, and the shell prompt from
`square-terminal`.

The ground, layout, palette and the live indicator are ours:

- **Ground**: a deep violet gradient (`#1c1238` → `#0a0616`) with two soft nebula
  washes — smooth gradients only, deliberately no star particles, which turned
  into noise at avatar sizes.
- **Display**: lilac `#ece7ff` core over a muted violet glow — a wide halo
  (`feGaussianBlur` 14, opacity 0.55) and a tight mid layer (blur 5). The
  committed PNGs have the glow baked in; if an SVG viewer has no filter support
  the halo and mid layer drop out and a clean flat lilac mark remains.
- **Live indicator**: a magenta `#ff5fd2` dot inside the screen beside the prompt.
  Magenta is the conventional live/on-air colour and stays distinct from the
  violet field, so it is still the element the eye lands on at 32px.

Two licenses apply, because Lucide's `monitor` is one of the icons Lucide derives
from [Feather](https://feathericons.com) (Lucide's own list names `monitor`, with
the MIT notice below applying to it; `square-terminal` is under Lucide's ISC
license).

## Lucide — ISC License

```
ISC License

Copyright (c) 2026 Lucide Icons and Contributors

Permission to use, copy, modify, and/or distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
```

## Feather — MIT License (icons Lucide derives from Feather, incl. `monitor`)

```
The MIT License (MIT)

Copyright (c) 2013-present Cole Bemis

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

Upstream notices:
<https://github.com/lucide-icons/lucide/blob/main/LICENSE>

## Regenerating

From this directory:

```bash
rsvg-convert -w 512 -h 512 avatar.svg -o avatar-512.png
rsvg-convert -w 64  -h 64  avatar.svg -o avatar-64.png
rsvg-convert -w 32  -h 32  avatar.svg -o avatar-32.png
```

`avatar-512.png` is the one to upload: GitHub displays avatars as circles, so the
ground is full-bleed and the mark stays inside the inscribed circle.

## Rejected alternatives

Rendered for comparison and not used:

- **Tux** (Simple Icons' `linux`, files under CC0 1.0): the Linux mascot is
  everyone's penguin and using it as this org's own identity comes close to
  claiming the Linux brand — weak differentiation and avoidable trademark doubt.
- **Outline ring around the mark** (a nod to the card's progress ring): at avatar
  sizes the gap made it read as a loading spinner, and it competed with the
  monitor for attention. Replaced by the neon halo.
- **Magenta live dot with broadcast arcs outside the screen**: the arcs crowd the
  canvas corner and turn into a scribble at 32px; the lone dot inside the screen
  reads better and stays balanced.
- **Play triangle inside the screen**: strong "video" read, but it is the one
  element that would have to go for the prompt, so both cues could not coexist.
- **`monitor-play`** (screen with a play triangle): says "video", not "Linux".
- **`radio`** (broadcast arcs): dense concentric strokes melt into a blob at 32px.

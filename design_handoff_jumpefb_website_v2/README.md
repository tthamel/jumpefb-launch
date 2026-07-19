# Handoff: jumpEFB Marketing Website v2

## Overview

One-page marketing site for **jumpEFB** — the standalone pilot EFB from DirtDive. Dark, instrument-panel aesthetic that mirrors the app itself: graphite surfaces, one blue accent, mono for anything numeric, zero stock-photo gloss. The design reference is `jumpEFB Website v2.dc.html` in this bundle (desktop, 1120px content column). Recreate it as a static page (plain HTML/CSS or the stack of your choice) — there is no backend; the only interactive elements are anchor links and two tweakable details noted below.

## Design tokens

```
bg          #0B0D11    page background
bgAlt       #0E1116    banded sections (fleet strip, FAQ), cards
panel       #0F1521    nested surfaces (map, stat tiles inside phone)
border      #151A22    section hairlines
borderAlt   #1B212B    card borders, dividers
borderHi    #2A3547    secondary-button borders
text        #E7ECF3    primary
dim         #97A3B6    body copy
muted       #5E6B7F    kickers, labels
faint       #3E4C61    footnotes
accent      #4B9FE1    THE blue — buttons, links, canopy
accentHi    #7EC0F2    hover states
green       #3FA776    live/ok readouts
amber       #E0A83E    cardinal ticks, EXIT marker
magentaAlt  #C74FB0    (app-side jump-run magenta; not used on the site)
```

Fonts: **IBM Plex Sans** 400/500/600/700 (UI + body), **IBM Plex Mono** 400/500/600/700 (every number, kicker, and label). Google Fonts.

Link colors: `a { color:#4B9FE1 }`, hover `#7EC0F2`.

## Layout system

- Content column: `max-width:1120px`, 32px side padding.
- Sticky nav: 44px logo tile (gauge icon SVG — lift verbatim from the reference), blur backdrop `rgba(11,13,17,.82)` + bottom hairline.
- Buttons: primary = solid accent, dark text `#0B0D11`, radius 9; secondary = 1px `#2A3547` border, radius 9. Padding 14/26.
- Kickers: 11px mono 600, `#5E6B7F`, `.16em` tracking, uppercase.
- H1 52px/-.03em; H2 34px/-.025em; body 15.5–17px/1.6 `#97A3B6`.
- Section rhythm: hero 76/88, features 88/48, spot 64/96, FAQ 80, CTA 96.
- Feature grid: 3×2, 1px `#1B212B` gap-lines via grid background trick (cells `#0B0D11` on a `#1B212B` grid with `gap:1px`), radius 12 clipped.
- Device mock: 340px phone, radius 32, border 2px `#223042`, showing the jump-run screen (SVG map + HUD chips + W&B float card). Copy the SVG from the reference file — do not redraw.

## Interactions

- Smooth-scroll anchors (`#features`, `#spot`, `#faq`, `#get`).
- Nav links dim→light on hover; buttons swap to `accentHi`.
- Two knobs the reference exposes as tweaks (implement as you like or hardcode defaults): hero W&B float card on/off (default ON), winds panel units kt/mph (default kt).
- No animation beyond hover states. No carousel, no scroll-triggered effects.

---

# Copy deck (verbatim)

## Nav
- Logo text: **jumpEFB**
- Links: Features · Spot engine · FAQ
- CTA button: **Get the app**

## Hero
- Kicker: `BUILT BY JUMP PILOTS · iOS + ANDROID`
- H1: **The EFB built for the ride to altitude.**
- Sub: General-aviation EFBs stop being useful the moment the door opens. jumpEFB plans the spot, flies the jump run, weighs every load, and always knows where the glide takes you.
- Buttons: **Get the app** / **See what it does**
- Stat readouts (label over value, mono):
  - `SPOT SOLVED IN` → **<10 s**
  - `W&B RE-CHECK` → **Per load**
  - `SPOT · W&B · GLIDE` → **On-device**

## Device mock labels (inside the phone)
- Header: `JUMP RUN · KE60` / `GPS · 3D`
- Chips: `RUN 274°M` · `GRP 2 / 6`
- Readouts: `GREEN LIGHT IN` **0.4 NM** · `XTK` **0.02 L**
- Bottom tiles: `ALT` **13,500** · `GS` **92** · `HDG` **274°**
- W&B float card: `LOAD 14 · W&B` / `IN ENVELOPE` · `GROSS` **8,412 LB** · `CG` **139.8 IN** · `MARGIN` **+112 LB**

## Fleet strip
- Label: `W&B PROFILES SHIP FOR`
- Items: `CESSNA 182 / 206` · `KODIAK 100` · `PAC 750XL` · `CARAVAN 208` · `TWIN OTTER` · `KING AIR 90`

## Features section
- Kicker: `EVERYTHING BETWEEN ENGINE START AND JUMPERS AWAY`
- H2: **One app for the whole load cycle.**
- Cards (tag / title / body):
  1. `SPOT` — **Spot calculator** — Winds-aloft drift solution with exit throw and freefall drift, drawn on the sectional in seconds.
  2. `JUMP RUN` — **Jump run guidance** — Fly the line with live crosstrack, groundspeed timing, and a green-light call you can trust.
  3. `LOADS` — **Manifest & W&B** — Every load weighed against the envelope as jumpers shuffle — no clipboard arithmetic.
  4. `GLIDE` — **Engine-out glide** — A continuously updated, wind-corrected glide ring from your current altitude. Always an out.
  5. `WX` — **Winds aloft & pattern** — Forecast winds by altitude, pattern planning, and density altitude where it matters.
  6. `LOG` — **Pilot logbook** — Loads, cycles, and hours logged automatically as you fly. Export whenever you need it.

## Spot engine section
- Panel header: `WINDS ALOFT · SOLVED SPOT` / `KE60 · 14:20Z`
- Winds rows (alt / arrow / bar / wind): 12,000 → 280°/34 kt · 9,000 → 275°/27 · 6,000 → 270°/19 · 3,000 → 265°/12 · SFC → 260°/7
- Panel footer: Freefall + canopy drift, throw, forward toss → **SPOT 0.3 W**
- Kicker: `THE SPOT ENGINE`
- H2: **Winds change. The spot keeps up.**
- Body: Pull current winds aloft, and jumpEFB integrates drift through freefall and canopy descent — exit throw and jump-run offset included. The answer is a line on the map, not a math exercise at 13,500 feet.
- Checklist:
  - Live green-light call with crosstrack on the run-in
  - Separate solutions per group: belly, freefly, tandems, students
  - Engine-out glide ring drawn continuously, wind-corrected

## FAQ
- H2: **Questions pilots ask.**
1. **Is this a replacement for ForeFlight?** — No — it's the app for the jump operation itself. Many pilots run both: a GA EFB for the cross-country legs, jumpEFB for the load cycle. What GA EFBs treat as an edge case is our whole product. And unlike the big GA EFBs, we ship on Android too.
2. **Does it work without cell coverage?** — Yes. Winds and forecasts are fetched when you have signal and cached; spot, jump run, W&B, glide, and logbook are fully on-device.
3. **What aircraft does it support?** — Any jump ship. W&B profiles ship for the common fleet — 182, 206, Caravan, Kodiak, PAC 750, Twin Otter, King Air — and you can build custom profiles.
4. **Is the green-light call authoritative?** — It's advisory. You're the PIC — jumpEFB gives you the numbers to make the call, and the audit trail to defend it.

## CTA
- H2: **Fly the load, not the math.**
- Body: Free for every pilot, forever, on iOS *and* Android. Pro adds DZ connectivity when your dropzone runs on jumpDZM.
- Buttons: **Join the beta** / **Talk to us**

## Footer
- © 2026 DirtDive · jumpEFB
- Advisory only — not for navigation. Not a substitute for pilot judgment or the POH.
- Links: Features · FAQ · Beta · Privacy · Support

## Link targets still TBD (owner: Trevor)
- "Get the app" / "Join the beta" → TestFlight + Play internal-track URLs
- "Talk to us" → mailto:hello@dirtdive.app (confirm address)
- Privacy / Support → host the two pages included in the launch package

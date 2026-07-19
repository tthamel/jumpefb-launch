# jumpEFB Launch Page

One-page marketing site for **jumpEFB** — the standalone pilot EFB from DirtDive. Built from `design_handoff_jumpefb_website_v2/` (tokens, copy deck, and reference markup live there).

Plain static HTML/CSS, no build step, no backend. IBM Plex Sans/Mono via Google Fonts.

## Run locally

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## TBD (owner: Trevor)

- "Get the app" / "Join the beta" → TestFlight + Play internal-track URLs (currently `#get`)
- "Talk to us" → `mailto:hello@dirtdive.app` (address unconfirmed)
- `privacy.html` / `support.html` → host the two pages from the launch package (linked in footer, not yet present)

## Design knobs

Per the handoff, two tweakables are hardcoded at their defaults: hero W&B float card **ON** (`.wb-card` in `index.html`), winds panel units **kt** (values in the `#spot` section).

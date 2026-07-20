# jumpEFB Launch Page

One-page marketing site for **jumpEFB** — the standalone EFB for jump pilots. Built from the `design_handoff_jumpefb_website_v2/` bundle (tokens, copy deck, reference markup — kept local/untracked to keep deployments clean).

Plain static HTML/CSS, no build step, no backend. IBM Plex Sans/Mono via Google Fonts.

## Run locally

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## TBD (owner: Trevor)

- "Get the app" / "Join the beta" → TestFlight + Play internal-track URLs (currently `#get`)
- `hello@jumpefb.com` → set up Cloudflare Email Routing so this address actually receives mail
- Terms: fill in governing-law state (and entity name if one is formed later)
- Privacy: verify every claim against actual app behavior before App Store submission

## Design knobs

Per the handoff, two tweakables are hardcoded at their defaults: hero W&B float card **ON** (`.wb-card` in `index.html`), winds panel units **kt** (values in the `#spot` section).

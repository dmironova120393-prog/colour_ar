# ✦ Hue & You

**AI-powered personal color analysis and beauty product discovery, with live AR try-on.**

Upload a selfie → get your color season → discover matched products → try them on with your camera.

---

## What it does

1. **Color analysis** — Upload a photo and Claude Vision analyzes your skin tone, undertone, eye color, and contrast level to assign you a color season (e.g. Soft Autumn, True Spring, Deep Winter)
2. **Palette generation** — Returns your best colors, neutrals, colors to avoid, and ideal lip shades as hex codes
3. **Product matching** — Picks 5 real products from brands like Charlotte Tilbury, NARS, Fenty Beauty, and MAC that match your exact palette, with direct Sephora search links
4. **AR try-on** — Opens your front camera and overlays the recommended lip shades on your lips in real time using MediaPipe Face Mesh

---

## Demo

> Open `hue-and-you.html` in Safari on iPhone for the full experience including AR try-on.

Live version: `https://dmironova120393-prog.github.io/hue-and-you`

---

## Tech stack

| Layer | What's used |
|---|---|
| AI color analysis | Claude Vision (`claude-opus-4-5`) via Anthropic API |
| Product recommendations | Claude (`claude-opus-4-5`) with beauty product knowledge |
| Face detection | [MediaPipe Face Mesh](https://google.github.io/mediapipe/solutions/face_mesh) — runs fully on-device |
| Lip overlay | HTML5 Canvas with `multiply` blend mode |
| Frontend | Single-file vanilla HTML/CSS/JS — zero dependencies, zero build step |
| Hosting | GitHub Pages |

---

## Getting started

### Requirements

- An [Anthropic API key](https://console.anthropic.com) — free tier works fine
- Safari on iPhone (for AR camera access), or any modern browser for steps 1–4

### Run locally

Just open the file — no server needed:

```bash
open hue-and-you.html   # macOS
```

Or on iPhone: AirDrop the file → open in Safari.

### Deploy to GitHub Pages

```bash
git init
git add .
git commit -m "Initial commit"
gh repo create hue-and-you --public --push --source=.
```

Then in your repo: **Settings → Pages → Source: main / root → Save**

Your app will be live at `https://yourusername.github.io/hue-and-you` within a minute.

---

## Privacy

- Your photo is sent directly from your browser to the Anthropic API — it is not stored or forwarded anywhere else
- Your API key is never saved (session only, lives in memory)
- Face detection runs entirely on-device via MediaPipe — no camera frames leave your phone
- No cookies, no analytics, no backend

---

## Project structure

```
hue-and-you/
├── hue-and-you.html    # entire app — one file
└── README.md
```

---

## Roadmap

- [ ] Sephora affiliate product feed integration (real-time inventory + pricing)
- [ ] Eyeshadow and blush AR overlays
- [ ] Fashion color matching via clothing APIs
- [ ] Save and share your color season card
- [ ] Professional AR via [Perfect Corp YouCam SDK](https://www.perfectcorp.com/business/sdk)

---

## Known limitations

- **No Sephora API** — product suggestions come from Claude's knowledge, not live inventory. Links go to Sephora search. For production, use an affiliate product feed.
- **AR try-on requires Safari on iOS** — Chrome and in-app browsers block camera access for local HTML files
- **Lip overlay only** — eyeshadow and blush require additional landmark groups (coming in roadmap)

---

## License

MIT — do whatever you want with it.

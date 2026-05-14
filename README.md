# 🛶 Neuwieder Kanu-Club e.V. — Website

Official website for **Neuwieder Kanu-Club e.V.**, hosted for free on **Cloudflare Pages**.

**Live URL:** [https://nkc-neuwied.de](https://nkc-neuwied.de)
**Repository:** [https://github.com/praveengadiyaram369/nkc-neuwied](https://github.com/praveengadiyaram369/nkc-neuwied)

---

## 🗂 Project Structure

```
nkc-neuwied/
├── index.html            ← Main homepage
├── galerie.html          ← Photo gallery (dynamic, filter by category)
├── vorstand.html         ← Board members with photos
├── pegeldienste.html     ← Water level links by German state
├── impressum.html        ← Legal imprint (required in Germany)
├── datenschutz.html      ← Privacy policy / DSGVO
├── 404.html              ← Friendly error page
├── sitemap.xml           ← SEO sitemap
├── robots.txt            ← Search engine instructions
├── favicon.ico / favicon-32.png / favicon-16.png / apple-touch-icon.png
├── logo.png              ← Club logo transparent PNG (used in site)
├── logo.jpeg             ← Original logo backup
│
└── img/
    ├── slider/
    │   ├── images.json   ← ⭐ Edit to add/remove slider photos
    │   └── slider1.jpg, slider2.jpg, ...
    ├── gallery/
    │   ├── images.json   ← ⭐ Edit to add/remove gallery photos
    │   └── gallery1.jpg, gallery2.jpg, ...
    ├── vorstand/
    │   ├── martin-klein.jpg
    │   ├── klaus-heyduczek.png
    │   ├── rainer-molitor.png
    │   ├── richard-korscheid.jpg
    │   ├── volker-robbert.jpg
    │   ├── benjamin-klein.png
    │   ├── casper-sklenar.png
    │   ├── dominik-bolz.png
    │   └── Jennifer.png        ← Antje Saebel (Beisitzerin)
    ├── old_homepage/
    │   ├── nkc1.jpg            ← Über uns image 1
    │   ├── nkc2.jpg            ← Über uns image 2
    │   └── nkc3.jpg            ← Über uns image 3
    └── parallax.jpg            ← Full-width parallax background
```

---

## 🚀 Deployment & Cache

Site deploys automatically on every `git push` via Cloudflare Pages (~60 seconds).

**After pushing, purge the Cloudflare cache so all visitors see the update immediately:**
1. [dash.cloudflare.com](https://dash.cloudflare.com) → your domain
2. **Caching → Configuration → Purge Cache → Purge Everything**

**Members with old cached pages:** press `Cmd+Shift+R` (Mac) or `Ctrl+Shift+R` (Windows).

---

## ✏️ Most Common Updates

### Update events (Termine)
1. Open `index.html` on GitHub → click ✏️
2. Find the `<tbody>` inside the calendar table (search for `td-date`)
3. Edit dates and text → **Commit changes** → live in ~60 seconds

### Add a gallery photo
1. Compress photo at [squoosh.app](https://squoosh.app) → save to `img/gallery/`
2. Add one line to `img/gallery/images.json`:
```json
{"file": "myphoto.jpg", "alt": "Beschreibung", "cat": "touren"}
```
Categories: `touren` · `training` · `bootshaus` · `events`

### Add a slider photo
1. Resize to 1920×1080px, compress to <400KB → save to `img/slider/`
2. Add to `img/slider/images.json`:
```json
{"file": "slider5.jpg", "alt": "Beschreibung"}
```

### Add/update a Vorstand photo
Copy photo to `img/vorstand/` named exactly as in `vorstand.html` (e.g. `martin-klein.jpg`).
Photos display uniformly in a padded white box — any original size works.

---

## 🖼 Image Guidelines

| Location | Recommended size | Format | Max file size |
|---|---|---|---|
| Hero slider | 1920 × 1080 px | JPG 85% | 400 KB |
| Parallax section | 1920 × 800 px | JPG 85% | 400 KB |
| Gallery photos | any | JPG 80% | 300 KB |
| Über uns (3 photos) | any (displayed at 170px height) | JPG 80% | 200 KB |
| Vorstand photos | any (shown with padding in 220px frame) | JPG/PNG | 200 KB |

Compress all images at **[squoosh.app](https://squoosh.app)** before uploading.

---

## 📋 Current Status

### ✅ Live & working
- Dynamic image slider + gallery (JSON-driven, no HTML editing needed for photos)
- Club history timeline (Über uns) with 3 club photos
- 6 activity cards (Kanadier, Kajak, Wildwasser, Schwimmen & Rollen, Sicherheitstraining, Wanderungen)
- Termine 2026: 16 events in full calendar table
- Photo strip + full gallery page with category filter + lightbox
- Vorstand: 9 members with photos (uniform padded display)
- Pegeldienste (all German states)
- Impressum + Datenschutz (DSGVO compliant)
- Privacy notice bar (no cookies)
- SEO: sitemap.xml, robots.txt, Open Graph meta tags, favicons
- Social: Instagram [@neuwieder_kanu_club](https://www.instagram.com/neuwieder_kanu_club/) + Facebook active
- Domain: nkc-neuwied.de via Lansol → Cloudflare nameservers

### 🔴 Still needed (legal)
- **Impressum:** Vereinsregisternummer — club owner must provide and fill in

### 🟡 Future / nice to have
- Real membership fees (ask Kassenwart Richard Korscheid)
- More gallery photos
- YouTube channel link when created
- Trip reports / news page (`berichte.html`)

---

## 📞 Contact & Handover

**Club contact:** neuwieder.kanu.club@web.de
**Address:** Rheinstraße 56, 56564 Neuwied, Rhein-km 608

### Giving club members edit access
1. GitHub repo → **Settings → Collaborators → Add**
2. For events: edit only the `<tbody>` in `index.html`
3. For photos: copy to folder + add line to `images.json`
4. For bigger changes: paste `AGENTS.md` into [claude.ai](https://claude.ai)

---

## 🔧 Tech Stack

| What | Tool |
|---|---|
| Language | Plain HTML + CSS + JavaScript (no frameworks, no npm) |
| Fonts | Google Fonts (Cormorant Garamond + Jost) |
| Images | Dynamic via `images.json` manifest files |
| Map | OpenStreetMap (no API key needed) |
| Hosting | Cloudflare Pages (free, unlimited bandwidth, DSGVO-compliant) |
| Domain | nkc-neuwied.de at Lansol, nameservers → Cloudflare |
| Version control | GitHub |

# 🛶 Neuwieder Kanu-Club e.V. — Website

Official website for **Neuwieder Kanu-Club e.V.**, hosted for free on **Cloudflare Pages**.

Live URL: [https://nkc-neuwied.de](https://nkc-neuwied.de)
Repository: [https://github.com/praveengadiyaram369/nkc-neuwied](https://github.com/praveengadiyaram369/nkc-neuwied)

---

## 🗂 Project Structure

```
nkc-neuwied/
├── index.html         ← Main homepage
├── vorstand.html      ← Board members / Vorstand
├── pegeldienste.html  ← Water level links by German state
├── impressum.html     ← Legal imprint (required in Germany)
├── datenschutz.html   ← Privacy policy / DSGVO
├── logo.jpeg          ← Club logo (NKC pennant)
├── README.md          ← This file — setup & maintenance guide
└── AGENTS.md          ← AI assistant instructions for future updates
```

> **Note:** This is a single-page website. All content, styles, and scripts
> are in `index.html`. No build tools, no npm, no frameworks required.

---

## 🚀 How to Deploy (First Time)

### 1. Push to GitHub
```bash
git init
git add .
git commit -m "Initial website"
git branch -M main
git remote add origin https://github.com/praveengadiyaram369/nkc-neuwied.git
git push -u origin main
```

### 2. Deploy on Cloudflare Pages
1. Go to [https://pages.cloudflare.com](https://pages.cloudflare.com) and sign in
2. Click **"Create a project"** → **"Connect to Git"**
3. Select your `nkc-neuwied` repository
4. Build settings:
   - **Framework preset:** None
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/` (root)
5. Click **"Save and Deploy"**
6. Your site is live at `nkc-neuwied.pages.dev` within 1–2 minutes

### 3. Connect your domain (nkc-neuwied.de)
1. In Cloudflare Pages → your project → **"Custom domains"**
2. Click **"Set up a custom domain"** → enter `nkc-neuwied.de`
3. In IONOS: Domains & SSL → nkc-neuwied.de → **"Custom nameservers"**
4. Enter the two Cloudflare nameservers shown (e.g. `brenda.ns.cloudflare.com`)
5. Wait up to 24 hours for DNS propagation

---

## ✏️ How to Update the Website

You **never need to touch code** for most updates. Just edit `index.html`
in GitHub's web editor or in VS Code, then push. Cloudflare auto-deploys.

### Common updates

| What to change | Where in index.html | How |
|---|---|---|
| Event dates & text | Section `id="termine"` | Edit the `.event-body` blocks |
| Club address / email | Section `id="anfahrt"` and `id="kontakt"` | Edit the text directly |
| Hero slider text | `.hero-content` section | Edit h1, p tags |
| Membership info | Section `id="mitglied"` | Edit `.member-item` list & `.fee-row` items |
| Navigation links | `<nav>` and `.mobile-menu` | Edit the `<a>` tags |
| Footer links | `<footer>` | Edit `.footer-links` |
| Social media links | Footer `.footer-col` | Replace `#` with real URLs |

### Quick GitHub edit (no coding needed)
1. Go to your repo on github.com
2. Click `index.html`
3. Click the ✏️ pencil icon (top right)
4. Make your changes
5. Click **"Commit changes"** — site updates automatically in ~1 minute

---

## 🖼 Image Guidelines

Replace the placeholder Unsplash images with your own club photos.
Use these resolutions for best quality + fast loading:

| Location | Recommended size | Format |
|---|---|---|
| Hero slider (full screen) | 1920 × 1080 px | JPG, quality 85% |
| Activity cards (large) | 800 × 600 px | JPG, quality 80% |
| Event cards | 600 × 400 px | JPG, quality 80% |
| Gallery strip | 400 × 300 px | JPG, quality 75% |
| Welcome section (portrait) | 900 × 700 px | JPG, quality 80% |
| Welcome section (accent) | 600 × 500 px | JPG, quality 80% |

**How to replace an image:**
Find the line `<img src="https://images.unsplash.com/...">` and replace the URL
with either:
- A relative path to your own image: `src="images/rheintour.jpg"`
- Or upload your image to a free host like [https://imgbb.com](https://imgbb.com)
  and use that URL

**Free image compression tool:** [https://squoosh.app](https://squoosh.app)
Drag your photo in, export as JPG at the sizes listed above.

---

## 📱 Social Media

To add real social media links, find these placeholder lines in the footer
and replace `#` with your actual URLs:

```html
<a href="#">Instagram</a>   →   <a href="https://instagram.com/nkc_neuwied">Instagram</a>
<a href="#">Facebook</a>    →   <a href="https://facebook.com/nkcneuwied">Facebook</a>
```

---

## 📄 Missing Pages (Future Work)

The current site is a single-page homepage. These pages are recommended for the future:

| Page | File to create | Priority |
|---|---|---|
| Impressum | `impressum.html` | ✅ Done |
| Datenschutzerklärung | `datenschutz.html` | ✅ Done |
| Vorstand | `vorstand.html` | ✅ Done |
| Pegeldienste | `pegeldienste.html` | ✅ Done |
| Berichte / News | `berichte.html` | 🟡 Future |
| Galerie | `galerie.html` | 🟡 Future |

> **Important for Germany:** You are legally required to have an **Impressum**
> and a **Datenschutzerklärung** on your website. See AGENTS.md for how to
> create these with AI assistance.

---

## 🔧 Tech Stack

| What | Tool |
|---|---|
| Language | Plain HTML + CSS + JavaScript |
| Fonts | Google Fonts (Cormorant Garamond + Jost) |
| Images | Unsplash (placeholder) → replace with own photos |
| Map | OpenStreetMap (free, no API key needed) |
| Hosting | Cloudflare Pages (free) |
| Domain | IONOS (existing contract, expires Nov 2025) |
| Version control | GitHub |

No frameworks. No npm. No build step. Just one HTML file.

---

## 🆘 Troubleshooting

**Site not updating after push?**
→ Check Cloudflare Pages dashboard → Deployments. Look for errors.

**Domain not working?**
→ DNS changes can take up to 24 hours. Be patient.

**Images not loading?**
→ Check the `src="..."` path. Relative paths need the file to be in the repo.

**Need help?**
→ Open `AGENTS.md` and follow the instructions to get AI assistance.

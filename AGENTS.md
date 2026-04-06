# 🤖 AGENTS.md — AI Assistant Guide for NKC Neuwied Website

This file tells an AI assistant (Claude, ChatGPT, etc.) everything it needs
to know about this website so it can help maintain and update it efficiently.

**Paste the contents of this file at the start of any AI conversation
when you need help with the website.**

---

## Project Overview

- **Club:** Neuwieder Kanu-Club e.V.
- **Location:** Rheinstraße 56, 56564 Neuwied, Rhein-km 608
- **Email:** 1.Vorsitzender@nkc-neuwied.de
- **Domain:** nkc-neuwied.de
- **Hosting:** Cloudflare Pages (free, deployed from GitHub)
- **Repository:** https://github.com/praveengadiyaram369/nkc-neuwied
- **Language:** German (all user-facing content must be in German)

---

## Technical Stack

- **Single file website:** Everything is in `index.html` — HTML, CSS, and JS
- **No build tools** — no npm, no webpack, no framework
- **Fonts:** Cormorant Garamond (display) + Jost (body) from Google Fonts
- **Images:** Unsplash placeholder images — club should replace with own photos
- **Map:** OpenStreetMap embed (no API key)
- **No database** — contact via email only, no forms with backend

---

## Design System

When making changes, always respect these design values:

```
Colors:
  --blue:      #1a5f7a   (primary blue, Rhein color)
  --blue-dark: #0d3d52   (dark navy, nav & dark sections)
  --blue-mid:  #2a8aad   (medium blue)
  --gold:      #b8892e   (accent gold, headings & labels)
  --gold-lt:   #d4a44a   (light gold, italic highlights)
  --sand:      #f7f2ea   (warm off-white background)
  --white:     #ffffff
  --text:      #1a2634   (body text)
  --muted:     #607080   (secondary text)

Fonts:
  Display/headings: 'Cormorant Garamond', serif — use for h1, h2, h3
  Body/UI:          'Jost', sans-serif — use for paragraphs, labels, buttons

Tone & Voice:
  - Warm, welcoming, community-focused
  - Use "du/dich/dir" (informal) not "Sie" — it's a sports club
  - German language, correct spelling with Umlauts (ü, ö, ä, ß)
  - Headlines can use italic <em> for one key word (styled in gold)
```

---

## Page Sections (in order)

1. **`<nav>`** — Fixed navigation bar. Transparent on top, dark blue when scrolled
2. **`.hero`** — Full-screen auto-playing image slider (4 slides)
3. **`.quicklinks`** — 4-column dark strip with icon links
4. **`#willkommen`** — Welcome / About section with 2 overlapping images
5. **`.stats`** — 4 statistics in sand background
6. **`#aktivitaeten`** — 3 large activity cards with hover effect
7. **`.parallax-cta`** — Full-width parallax call-to-action
8. **`#termine`** — 3 event cards
9. **`.gallery-strip`** — 6-photo horizontal gallery
10. **`#mitglied`** — Membership section (dark blue background)
11. **`#anfahrt`** — Location with OpenStreetMap
12. **`#kontakt`** — Contact strip
13. **`<footer>`** — 4-column footer

---

## Common Tasks for AI

### Task: Update events/termine
Find the section `id="termine"` and update the `.event-card` blocks.
Each card has: `.event-date` (small label), `.event-title` (h3), `.event-desc` (p).
Keep 3 cards maximum. If more events exist, link to a separate termine.html page.

### Task: Add a new page (e.g. Impressum)
Create a new file (e.g. `impressum.html`) with the same nav and footer as index.html.
Use the same CSS variables and fonts. Add a link in the footer nav.

### Task: Replace placeholder images
Find `src="https://images.unsplash.com/..."` lines and replace with:
- Relative path: `src="images/myphoto.jpg"` (if image is in repo)
- Direct URL: `src="https://yourhost.com/myphoto.jpg"`

### Task: Add social media links
In the footer, find the Kontakt column and add:
```html
<li><a href="https://instagram.com/YOUR_HANDLE">📷 Instagram</a></li>
<li><a href="https://facebook.com/YOUR_PAGE">Facebook</a></li>
```

### Task: Add Impressum (legally required in Germany)
Create `impressum.html`. Must contain:
- Angaben gemäß § 5 TMG
- Club name, address, Vertretungsberechtigter
- Kontakt (email, optional phone)
- Vereinsregister-Nr. if available
- Responsible for content (Verantwortlicher i.S.d. § 55 Abs. 2 RStV)

### Task: Add Datenschutzerklärung (DSGVO, legally required)
Create `datenschutz.html`. For a simple static site with no forms or tracking:
- Google Fonts data note (fonts are loaded from Google servers)
- OpenStreetMap embed note
- No cookies notice
- Contact for data requests
- Use a DSGVO generator like https://www.datenschutz-generator.de for the full text

### Task: Add a training schedule
Add a new section or table inside `#termine` or a new page.
Weekly training times from Mehlem as inspiration:
- Dienstag: Freies Paddeln / Training
- Freitag: Kajaktraining
(Ask the club for their actual schedule)

---

## Content Reference (from Mehlem club — adapt for NKC Neuwied)

These are content ideas from the Kanu Club Mehlem that are relevant for NKC:

**About text inspiration:**
> "Bei uns reicht das Spektrum vom Wanderfahren bis zum ambitionierten 
> Slalom- und Wildwasserfahren. Regelmäßig sind wir auf den Flüssen der 
> näheren und weiteren Umgebung unterwegs."

**Youth section idea:**
> "Die Jugendarbeit ist beim Verein seit der Gründung eine der wichtigsten 
> Aufgaben. Wir freuen uns über aktive Kinder vom Grundschul- bis zum Jugendalter."

**Schnupperpaddeln CTA:**
> "Lust auf ein Schnupperpaddeln? Dann einfach melden unter [email]"

---

## Missing / Future Work

These things are NOT yet implemented and should be added:

- [x] `impressum.html` — DONE
- [x] `datenschutz.html` — DONE
- [x] `vorstand.html` — DONE (all 8 board members)
- [x] `pegeldienste.html` — DONE (all German states)
- [ ] `berichte.html` — Club news / trip reports (future)
- [ ] `galerie.html` — Photo gallery page (future)
- [ ] Real club photos (replace all Unsplash placeholders) — ask club
- [ ] Real membership fees in `#mitglied` section — ask Kassenwart
- [ ] Real social media handles — replace `#` in footer with real URLs
- [ ] `favicon.ico` — Browser tab icon (use club logo)
- [ ] Satzung page (link to PDF or text)
- [ ] Berichte / News blog (consider Instagram embed instead)

---

## Deployment Reminder

After any change to `index.html`:
```bash
git add index.html
git commit -m "Update: [describe what you changed]"
git push
```
Cloudflare Pages auto-deploys within ~60 seconds. No manual action needed.

---

## Contact for Club Handover

When handing this website over to the club committee:
1. Give them access to the GitHub repository (Settings → Collaborators)
2. Show them how to edit `index.html` directly in GitHub's web editor
3. Tell them: for events, only edit the `#termine` section
4. For big changes, they can always paste this AGENTS.md into Claude
   at https://claude.ai and ask for help — it will understand the project

---

*This file was created to make AI-assisted maintenance as easy as possible.
Update it whenever major changes are made to the site structure.*

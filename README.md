# Knowledge Tree — Website

A single-page website for **Knowledge Tree**, a Lucknow-based coaching institute with branches in Sitapur and Kanpur, plus online classes for students across India. Founded by **Aditya Maurya**.

Live in one file: `index.html` — no build tools, no server, no dependencies to install. Open it in a browser and it works.

---

## 1. What's inside

| File | Purpose |
|---|---|
| `index.html` | The entire website — HTML, CSS, and content in one file |
| `README.md` | This document |

The only external resources loaded are two Google Fonts (**Fraunces** for headings, **IBM Plex Sans** for body text), pulled from `fonts.googleapis.com`. Everything else — icons, the tree illustration, buttons — is hand-drawn SVG or plain CSS, so there's nothing else to download or license.

---

## 2. Design concept

The visual identity is built around the institute's name and structure:

- **One root, many branches** — the hero section shows an animated line-drawing of a tree connecting Lucknow (the head branch) to Sitapur, Kanpur, and Online.
- **The "Branches" section** uses an actual trunk-and-branch layout (a horizontal line with four branches hanging off it) instead of a generic card grid, since the four locations are literally what the name refers to.
- **Color palette** — deep forest green (`#2F5233`), warm gold (`#C9A227`), and a brick red accent (`#A63D2F`) on a warm parchment background (`#F6F4EC`). Chosen to feel academic and rooted, not like a generic SaaS template.
- **Typography** — Fraunces (a serif with organic, slightly hand-cut letterforms) for headings, paired with IBM Plex Sans for body copy and UI.
- **Motion** — used once, deliberately: the hero tree draws itself in on page load. Nothing else animates on scroll, and all motion is disabled automatically if the visitor's device has "reduce motion" turned on.

---

## 3. Page sections (in order)

1. **Header / navigation** — sticky, with a mobile hamburger menu (pure CSS, no JavaScript).
2. **Hero** — headline, short pitch, WhatsApp CTA button, fee starting price, and four key stats (300+ students, 25 teachers, 4 locations, Olympiad partner).
3. **About / Founder** — a quote card for Aditya Maurya plus three "why choose us" points.
4. **Branches** — Lucknow (head branch), Sitapur, Kanpur, and Online, shown as branches off a shared trunk line.
5. **Programs / Olympiad** — three program cards (school & board coaching, Olympiad prep, live online classes) on a dark green band, plus a highlighted Olympiad strip.
6. **Teachers** — a large "25" stat plus a tag list of subjects taught.
7. **Pricing** — three fee cards (Online / Classroom / Olympiad batch), starting at ₹999/month, with a note that exact fees are confirmed over WhatsApp.
8. **Testimonials** — three short placeholder parent quotes.
9. **Contact** — WhatsApp CTA, phone number, and a summary card with branch and online details.
10. **Footer** — nav links, WhatsApp number, founder credit.
11. **Floating WhatsApp button** — fixed to the bottom-right corner on every scroll position.

---

## 4. Content that is placeholder and should be replaced

Everything structural is finished, but a few pieces of **copy were invented to fill the layout** since they weren't in the original brief. Please review and swap these out before publishing:

- **Fee amounts** — Online ₹999, Classroom ₹1,499, Olympiad batch ₹1,299 (all "per month onward"). Only the ₹999 starting price was confirmed; the other two numbers and the three-tier split are assumptions. Replace with your actual pricing structure.
- **Testimonials** — the three parent quotes in the "From our parents" section are illustrative, not real. Replace with actual (permission-given) feedback, or remove the section if you'd rather not use placeholder quotes.
- **Branch addresses** — currently just say "Lucknow, Uttar Pradesh" / "Sitapur, Uttar Pradesh" / "Kanpur, Uttar Pradesh." Add full street addresses, and consider adding a Google Maps embed per branch.
- **Subject tag list** (Teachers section) — Mathematics, Science, English, Social Studies, Hindi, Computer Basics, Reasoning, Olympiad Drills. Adjust to match what's actually taught.

Search for these in the file if you want to find them quickly: `price-tag`, `testi-card`, `.addr`, `subject-tags`.

---

## 5. How to customize

### Change the WhatsApp number
The number `918917009287` (91 = India country code + the number) appears in **four places**. Find and replace all instances of:
```
https://wa.me/918917009287
```
Also update the visible text `+91 89170 09287` in the Contact section and footer.

### Change colors
All colors are defined once at the top of the `<style>` block as CSS variables:
```css
:root{
  --bg:#F6F4EC;       /* page background */
  --green:#2F5233;    /* primary brand green */
  --gold:#C9A227;     /* accent gold */
  --brick:#A63D2F;    /* CTA / highlight red */
  ...
}
```
Editing a variable here updates it everywhere it's used.

### Change fonts
Fonts are loaded in the `<head>` via a Google Fonts `<link>` tag, and referenced by the `--serif` and `--sans` CSS variables. Swap the Google Fonts URL and the variable values together if you want a different pairing.

### Add/remove a branch
Duplicate one `.branch-card` block inside the `#branches` section and edit its heading, tag, description, and address. The layout auto-adjusts down to 2 columns on tablets and 1 column on phones.

### Add a real photo of the founder
Replace the `.founder-avatar` div (currently the initials "AM" on a green circle) with an `<img>` tag pointing to a photo, and add matching `border-radius: 50%` styling to keep the circular crop.

---

## 6. Technical notes

- **No JavaScript required.** The mobile menu uses a hidden checkbox + CSS sibling selector (the "checkbox hack"), so the site works even with JS disabled.
- **Responsive breakpoints** are set at `900px`, `860px`, `820px`, `760px`, and `480px` — covering desktop, tablet, and phone widths. Test at each if you resize sections.
- **Accessibility** — visible focus states are inherited from browser defaults (not overridden), all icons are decorative (`aria-hidden` where relevant) with real text labels alongside them, and the hero animation respects `prefers-reduced-motion`.
- **Fonts load from Google Fonts** over the network. If you need a fully offline version (e.g., for an intranet), download the Fraunces and IBM Plex Sans font files and self-host them, then swap the `<link>` tag for local `@font-face` rules.

---

## 7. How to publish it

You have several free/low-cost options since it's a single static HTML file:

1. **Netlify / Vercel** — drag and drop `index.html` into their dashboard; you'll get a live URL in seconds, with a custom domain option.
2. **GitHub Pages** — push this file to a GitHub repository named `index.html` (or in a `docs/` folder) and enable Pages in the repo settings.
3. **Any shared hosting** (GoDaddy, Hostinger, etc.) — upload `index.html` via FTP/File Manager to the root of your domain, renaming it to `index.html` if it isn't already (it is).

No database, no backend, and no build step are needed for this version.

---

## 8. Suggested next steps

- Swap in the placeholder fees, testimonials, and addresses (Section 4).
- Add real photos: a founder photo, branch exteriors/classrooms, and teacher photos if you're comfortable publishing them.
- Consider adding a simple enquiry form (name, phone, class, city) if you want leads to also land in an email inbox, not just WhatsApp.
- Add Google Maps embeds for each branch so parents can get directions directly from the site.
- Register a domain (e.g., `knowledgetree.in` or similar) if you haven't already, so the WhatsApp and site links look professional in marketing material.

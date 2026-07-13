# AZ Skin & Body Spa — Website

Single-file, production-ready landing page (`index.html`) built from `brand-brief-az-skin-body-spa.md`. Soft-editorial visual lane: warm cream/gold palette, Playfair Display + Jost, botanical-leaf motifs — matches the brand's existing custom-site look (cream/serif, editorial) rather than the generic GlossGenius booking-widget template. Single-page architecture per the brief: hero → trust strip → the difference → priority treatments → founder → proof → process → shop → visit/local → final CTA → footer.

Decisions locked in this session (per Sahir):
- Canonical name: **AZ Skin & Body Spa** (not "AZ Esthetics & Head Spa" or "az.esthetics").
- Founder fronted as **Samantha** (first name only, as she appears on GlossGenius).

## To deploy
Static site, no build step. Push/host `index.html`, `robots.txt`, `llms.txt`, and `/assets` as-is (Netlify, Vercel, GitHub Pages, Cloudflare Pages, etc.). Update `azskinandbodyspa.com` in the canonical/OG/schema tags to the real production domain before going live.

## Still needed before launch (flagged, not fabricated)
- **Real photography** — hero/room shot, Samantha's headshot, product shot. Current build uses labeled placeholder plates (dark botanical-motif blocks) instead of stock or invented photos, per the brief's Wall Test (no stock, no clinical medspa imagery). Swap these for real AZ photography (treatment room, head-spa water shot, Samantha, hair-oil product).
- **Full weekly hours** — brief only confirms Mon 1–5pm and Tue–Thu 10–5pm. Fri–Sun marked `{{FILL: confirm hours}}` in the Visit section and omitted from schema.
- **Branded shop domain** — Shop button still points at the bare `az-skin-body-spa.myshopify.com`. Brief flags this as the thing to fix (kill the naked myshopify exposure); point Shopify at a branded (sub)domain when available.
- **Official logo file** — header/favicon currently use an original line-art botanical monogram as a placeholder. Brief confirms a real gold-on-black-marble AZ monogram already exists on the hair-oil product; swap in the real logo file/SVG when supplied.
- **og-cover.jpg** — referenced in Open Graph tags, not yet created; add a 1200×630 branded share image.
- **3–5 more verbatim reviews** — brief has only one full quote (AMA) pulled onto the page; pull more from the live review slider to round out the Proof section.
- **301s / consolidation** — per the brief's SEO spine, once the domain is live, 301 the name-variant properties (AZ Esthetics & Head Spa listings, az.esthetics handle references) to consolidate search equity under the canonical name.

## Structure
```
index.html      — the full one-page site (semantic HTML, inline CSS, JSON-LD schema)
assets/
  favicon.svg   — placeholder monogram favicon (swap for real logo)
robots.txt
llms.txt        — AI-crawler brand summary (GEO/AEO)
```

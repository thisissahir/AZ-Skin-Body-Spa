# AZ Skin & Body Spa — Website

Single-file, production-ready landing page (`index.html`) built from `brand-brief-az-skin-body-spa.md`. Soft-editorial visual lane: warm cream/gold palette, Playfair Display + Jost, botanical-leaf motifs — matches the brand's existing custom-site look (cream/serif, editorial) rather than the generic GlossGenius booking-widget template. Single-page architecture per the brief: hero → trust strip → the difference → priority treatments → founder → proof → process → shop → visit/local → final CTA → footer.

Decisions locked in this session (per Sahir):
- Canonical name: **AZ Skin & Body Spa** (not "AZ Esthetics & Head Spa" or "az.esthetics").
- Founder fronted as **Samantha** (first name only, as she appears on GlossGenius).

## To deploy
Static site, no build step. Push/host `index.html`, `robots.txt`, `llms.txt`, and `/assets` as-is (Netlify, Vercel, GitHub Pages, Cloudflare Pages, etc.). Update `azskinandbodyspa.com` in the canonical/OG/schema tags to the real production domain before going live.

## Images — real, sourced from AZ's own accounts (no stock, nothing fabricated)
Pulled from AZ's own GlossGenius portfolio/service listings, Shopify store, and Instagram — all business-owned uploads, per the brief's Wall Test (no stock, no clinical medspa imagery). Source log:

| File | Used for | Source |
|---|---|---|
| `assets/images/hero-landing.jpeg` | Hero | Supplied directly by Sahir (red light therapy, moody close-up) — replaces the earlier GlossGenius portfolio hero pick |
| `assets/images/hero-redlight.jpeg` | Spare/unused | GlossGenius portfolio (red light therapy) — original hero pick, kept as a fallback |
| `assets/images/treatment-headspa.jpg` | Japanese Head Spa card | GlossGenius service photo ("Classic Japanese Head Spa 60 Mins") |
| `assets/images/treatment-facial.jpg` | Signature Customized Facial card | GlossGenius service photo |
| `assets/images/treatment-sculptglow.jpg` | Sculpt & Glow card | GlossGenius service photo |
| `assets/images/treatment-deluxe.jpg` | Deluxe Facial card | GlossGenius service photo |
| `assets/images/founder-samantha.jpg` | Founder section | Instagram (@azskinandbodyspa) video-post thumbnail of Samantha's on-camera introduction |
| `assets/images/product-hairoil-1.png` | Shop section | Shopify store (az-skin-body-spa.myshopify.com), `IMG-1485.png` |
| `assets/images/product-hairoil-2.png` | Spare/unused | Shopify store, `IMG-1487.png` — alt product angle, not yet placed |
| `assets/images/body-contouring.jpeg` | Spare/unused | GlossGenius portfolio (body contouring — stomach) |
| `assets/images/room-general.jpeg` / `assets/og-cover.jpg` | Open Graph share image | GlossGenius portfolio (general room/treatment shot) |

**Flagged for you to confirm before launch:**
- **Founder photo is a video-thumbnail, not a proper headshot.** It's the best available image of Samantha's face — replace with a real headshot as soon as one exists.
- **Two product PNGs are large** (1.7MB / 2.9MB straight off Shopify) — no image-compression tool was available in this environment to re-encode them. Run them through a compressor (Squoosh, TinyPNG, or Apollo's Adobe pipeline) and convert to WebP before launch; they currently hurt Core Web Vitals.
- **Instagram source image is a signed CDN URL** that was fetched once and saved locally — this is now a stable local file, no ongoing dependency on Instagram.
- Rights: all images are AZ's own uploads to its own GlossGenius, Shopify, and Instagram accounts — no third-party or customer-submitted photos used.

## Still needed before launch (flagged, not fabricated)
- **A proper headshot of Samantha** (see above).
- **Full weekly hours** — brief only confirms Mon 1–5pm and Tue–Thu 10–5pm. Fri–Sun marked `{{FILL: confirm hours}}` in the Visit section and omitted from schema.
- **Branded shop domain** — Shop button still points at the bare `az-skin-body-spa.myshopify.com`. Brief flags this as the thing to fix (kill the naked myshopify exposure); point Shopify at a branded (sub)domain when available.
- **Official logo file** — header/favicon currently use an original line-art botanical monogram as a placeholder. Brief confirms a real gold-on-black-marble AZ monogram already exists on the hair-oil product; swap in the real logo file/SVG when supplied.
- **Image compression pass** — see flags above.
- **3–5 more verbatim reviews** — brief has only one full quote (AMA) pulled onto the page; pull more from the live review slider to round out the Proof section.
- **301s / consolidation** — per the brief's SEO spine, once the domain is live, 301 the name-variant properties (AZ Esthetics & Head Spa listings, az.esthetics handle references) to consolidate search equity under the canonical name.

## Structure
```
index.html      — the full one-page site (semantic HTML, inline CSS, JSON-LD schema)
assets/
  favicon.svg   — placeholder monogram favicon (swap for real logo)
  og-cover.jpg  — Open Graph share image (real AZ photo)
  images/       — real photos pulled from AZ's own accounts (see table above)
robots.txt
llms.txt        — AI-crawler brand summary (GEO/AEO)
```

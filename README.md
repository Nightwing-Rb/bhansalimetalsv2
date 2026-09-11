# Bhansali Metals — Astro Revamp

Modern, fast, responsive rebuild of www.bhansalimetals.com using **Astro 4** (static output, zero-JS by default + minimal islands).

## ✨ What changed
- Old 37-file table-layout site → 33 clean Astro routes with shared layout
- Modern industrial UI: navy + safety-orange, Barlow Condensed + Inter, cards, sticky header, mobile menu, reveal animations
- SEO: semantic HTML, meta/OG per page, clean URLs (`/aboutus`, `/products/bright-bars`, `/technical/pipe-data` …)
- Preserved content: all product specs, grades, sizes, tolerances, contact + MTC/TPI notes
- Reused legacy `images/` (copied to `public/images/`)
- Enquiry form → `mailto:` + WhatsApp (no backend needed; wire to API later)

## 🗺️ Old → New URL map
| Old (.html) | New (Astro) |
|---|---|
| index.html | `/` |
| aboutus.html | `/aboutus` |
| quality.html | `/quality` |
| certificates.html | `/certificates` |
| enquiry.html | `/enquiry` |
| contactus.html | `/contactus` |
| product.html | `/products/bright-bars` |
| product_black.html | `/products/black-bars` |
| sheetplate.html | `/products/sheets-plates` |
| rodbar.html | `/products/round-bars-squares` |
| stainless.html | `/products/flanges` |
| stanless_fastnrs.html / fastener.html | `/products/fasteners` |
| stanless_pipe.html / pipefitting.html | `/products/pipe-fittings` + `/products/pipes-tubes` |
| highnickel.html | `/products/high-nickel-alloys` |
| monel500.html | `/products/monel-500` |
| hastelloyc-276.html | `/products/hastelloy-c276` |
| hastelloyc-22.html | `/products/hastelloy-c22` |
| hastelloyc-b2.html | `/products/hastelloy-b2` |
| hastelloyc-x.html | `/products/hastelloy-x` |
| nickel200-201.html | `/products/nickel-200-201` |
| technical.html | `/technical/chemical-composition` + `/technical` hub |
| tech_new_demo.html | `/technical/grades` |
| Tech_mechanical.html | `/technical/mechanical-properties` |
| tech_pipefitting / forgedfitting / elbow / stubend / tees / reducer / caps | `/technical/pipe-fittings` |
| tech_round.html | `/technical/round-bars` |
| tech_pipedata.html | `/technical/pipe-data` |
| tech_nickelalloy.html | `/technical/nickel-alloy-data` |
| tech_flanges.html | `/technical/flanges` |
| tech_wg_formula.html | `/technical/weight-formula` |
| tech_nonferrous.html | `/technical/nonferrous` |

Add server redirects from `*.html` → clean URLs when deploying (e.g. Netlify `_redirects`, Vercel `vercel.json`, or S3/CloudFront rules).

## 🚀 Run
```bash
cd bhansali-astro
npm install
npm run dev      # http://localhost:4321
npm run build    # → dist/
npm run preview  # preview production build
```

## 📁 Structure
```
public/images/          # legacy assets (reused)
src/layouts/BaseLayout.astro
src/components/Header|Footer|PageHero|ProductCard|CtaBand.astro
src/data/site.ts        # products, nav, contact constants
src/styles/global.css   # design system
src/pages/              # 33 routes
```

## 🔜 Next steps (optional)
- Add `sitemap` + `robots.txt` (`@astrojs/sitemap`)
- Wire `/enquiry` to Formspree / API route + file upload for BOM
- Image optimisation (`@astrojs/image`) + WebP
- Add `_redirects` for `.html` legacy SEO preservation

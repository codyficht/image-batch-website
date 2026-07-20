# Image-Batch website

Marketing site for **[Image-Batch](https://apps.apple.com/ca/app/image-batch/id1671363479?mt=12)** — a native bulk photo editor for Mac (macOS 15+).

**Live site:** [https://www.image-batch.com](https://www.image-batch.com)

This repo is the website only, not the Mac app source.

## Stack

- Static HTML / CSS (no build step)
- GitHub Pages + custom domain (`CNAME` → `www.image-batch.com`)
- Analytics: Google Analytics / Ads, Meta Pixel

## Pages

| File | Purpose |
|------|---------|
| `index.html` | Home / features |
| `pricing.html` | Lite, Pro, Premium tiers |
| `faq.html` | FAQ (also used for SEO / AI-friendly Q&A) |
| `updates.html` | Release notes |
| `privacy.html` | Privacy policy |
| `contact.html` | Contact / support |
| `thanks.html` | Post–App Store click thank-you (`noindex`) |

Shared styles live in `main.css`. Assets are under `images/`.

## Local preview

Open files in a browser, or serve the folder:

```bash
# Python 3
python3 -m http.server 8080

# or Node
npx serve .
```

Then visit `http://localhost:8080`.

## Deploy

Push to `main`. GitHub Pages serves this repository; the custom domain is set via `CNAME`.

After content or SEO changes that should be re-crawled, update `lastmod` in `sitemap.xml` when relevant and request indexing in [Google Search Console](https://search.google.com/search-console) if needed.

## SEO notes

- **Canonical URLs** and **JSON-LD** (e.g. `SoftwareApplication` on the home page, `FAQPage` on the FAQ) live in each page’s `<head>`.
- Prefer natural product language on the page; put longer search-intent wording in titles, meta descriptions, FAQ answers, and schema.
- Keep **prices**, **tier limits**, and **`softwareVersion`** in schema in sync with the live app and `updates.html`.
- `robots.txt` points crawlers at `https://www.image-batch.com/sitemap.xml`.
- `thanks.html` is `noindex` and is not listed in the sitemap.

## Related

- [Image-Batch on the Mac App Store](https://apps.apple.com/ca/app/image-batch/id1671363479?mt=12)

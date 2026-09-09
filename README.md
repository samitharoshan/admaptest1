# admap.lk — site skeleton

Static site, no build step. Structure:

```
index.html                              → homepage (search, category grid, location grid)
post-ad.html                            → ad submission form (wire the JS to a backend/form service)
category/<slug>/index.html              → all listings in a category, any city
location/<slug>/index.html              → all listings in a city, any category
category/<slug>/<city-slug>/index.html  → combined page — highest SEO/AI-answer value, build one per active category+city pair
listing/<slug>-<id>.html                → single listing detail (Service/Product + Offer + Breadcrumb + FAQ JSON-LD)
assets/style.css                        → shared stylesheet, all pages link to it
sitemap.xml / robots.txt                → update sitemap.xml every time you add a page
```

Generate new listing pages with the listing-generator.html tool (fill the form, download the HTML,
drop it into /listing/, then add a link + sitemap entry).

## Deploy to GitHub Pages

```bash
git remote add origin https://github.com/<your-username>/admap-site.git
git branch -M main
git push -u origin main
```

Then in the repo: **Settings → Pages → Deploy from branch → main → / (root)**.
To use the admap.lk domain instead of the default github.io one, add a `CNAME` file
containing just `admap.lk`, and point your domain's DNS at GitHub Pages.

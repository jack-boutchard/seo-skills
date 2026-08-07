# SEO Skills Collection Rules

## URLs & structure
- Never add a trailing slash to urls
- Each page is a flat root-level `.html` file (`page-name.html`), never `page-name/index.html` — directories reintroduce the trailing slash on GitHub Pages
- Every new page gets an entry in `sitemap.xml` (no trailing slash) and is reachable from the homepage
- Use absolute URLs for assets and downloads (`/file.zip`, `https://…`), never relative paths — so a page can move without breaking

## Rendering
- All pages must server side render — page content lives in the raw HTML, not injected by JavaScript

## Metadata (per page)
- Every page has a canonical + `og:url` with no trailing slash, a unique `<title>`, and a meta description
- Keep the JSON-LD `@graph` in sync — when adding a skill, add its `ItemList` `ListItem` and bump `numberOfItems`
- "Last Updated" is a hardcoded real date in a `<time datetime>`, never `new Date()` (that fakes daily freshness)

## Content
- Referral params: external links get `?seo-skillsmd` (`&seo-skillsmd` if the URL already has a query); internal `seo-skills.md` links get no param
- Hand-written HTML must be entity-escaped (`&amp;`, `&#39;`, `&rarr;`)
- Adding a skill = edit the homepage card grid **and** bump the matching filter-pill counts

## Accessibility
- Every image has `alt`; interactive controls have `aria-label` / `aria-pressed`; keep the skip link

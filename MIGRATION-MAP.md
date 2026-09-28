# PREMO Studio — Wix → GitHub Pages URL Migration Map

**Status:** Preparation only. Nothing in this document has been published to `premostudio.my` or `ericjh1219.github.io`. The Wix site remains live and unchanged. DNS has not been touched.

**Old site:** `https://www.premostudio.my/` (Wix)
**New site (staging):** `https://ericjh1219.github.io/premo-studio-website/`
**Future canonical domain:** `https://www.premostudio.my/` (new GitHub Pages site, once cut over)

This is the source of truth for every old Wix URL that needs a destination on the new site. See `REDIRECTS.md` for how these mappings actually get implemented as redirects (GitHub Pages cannot do this on its own — read that file before acting on this one).

## How to read this table

- **Migration action** — `Redirect` means the old URL should 301 to the New URL once a redirect layer exists. `Redirect (external)` means the destination is off-site (not a page in this repo). `Do not migrate` means the URL must not be recreated or redirected.
- **SEO priority** — `Critical` = has meaningful Google Search Console clicks/impressions today; `High` = important core service page; `Medium` = supporting/blog content; `Low` = Wix dev/duplicate artifact; `N/A` = intentionally excluded.

## Core pages

| Old Wix URL | New URL | Migration action | SEO priority | Notes |
|---|---|---|---|---|
| `/` | `/index.html` | Redirect | Critical | Homepage — root domain equity |
| `/kl-graduation-photo` | `/graduation-photo-kl.html` | Redirect | Critical | ~108 clicks / ~3,066 impressions in GSC — highest-priority redirect on the list |
| `/kl-passport-photo` | `/passport-photo-kl.html` | Redirect | Critical | ~104 clicks / ~13,044 impressions in GSC — highest impression volume of any old URL |
| `/passport-photo-kl` | `/passport-photo-kl.html` | Redirect | High | Alternate/older slug for the same page as `/kl-passport-photo`; both must land on the same new URL |
| `/headshot` | `/headshot-kl.html` | Redirect | High | |
| `/graduation-photo` | `/graduation-photo-kl.html` | Redirect | High | Same destination as `/kl-graduation-photo` |
| `/book-online` | `https://premostudio.minibookit.com/` | Redirect (external) | Medium | The new site has no internal booking page — every "立即预约 / Book Now" button sitewide already points to this external booking system (WhatsApp is the secondary CTA). This is the honest current destination, not a placeholder. |
| `/about-1` | `/about.html` | Redirect | Medium | |
| `/集团介绍` | `/about.html` | Redirect | Medium | Company introduction content lives on the About page |
| `/门店信息` | `/about.html` | Redirect | Medium | Both KL and JB branch addresses/hours are on this page |
| `/门店讯息-store-info` | `/about.html` | Redirect | Medium | Duplicate Wix URL for the same store-info content as `/门店信息` |
| `/portfolio` | `/portfolio.html` | Redirect | Medium | |
| `/qna-1` | `/faq.html` | Redirect | Medium | |

## Headshot / graduation guides

These are already the final filenames used on the new site — no additional lookup was needed.

| Old Wix URL | New URL | Migration action | SEO priority | Notes |
|---|---|---|---|---|
| `/headshot-cost-kl` | `/headshot-cost-kl.html` | Redirect | Medium | |
| `/copy-of-new-page` | `/headshot-cost-kl.html` | Redirect | Low | Wix dev-duplicate of the above article, same destination |
| `/headshot-preparation-guide` | `/headshot-preparation-guide.html` | Redirect | Medium | |
| `/who-needs-a-headshot` | `/who-needs-a-headshot.html` | Redirect | Medium | |
| `/men-makeup-headshot` | `/men-makeup-headshot.html` | Redirect | Medium | |
| `/rm49-vs-rm299-headshot` | `/rm49-vs-rm299-headshot.html` | Redirect | Medium | Legacy slug name kept for URL/SEO continuity; the article's actual content compares the real RM99 vs RM299 packages |
| `/how-much-does-a-graduation-photo-cost-in` | `/how-much-does-a-graduation-photo-cost-in.html` | Redirect | Medium | |
| `/what-to-wear-graduation-photo` | `/what-to-wear-graduation-photo.html` | Redirect | Medium | |
| `/studio-vs-school-graduation-photo` | `/studio-vs-school-graduation-photo.html` | Redirect | Medium | |
| `/studio-vs-outdoor` | `/studio-vs-outdoor.html` | Redirect | Medium | |
| `/why-graduation-photos-are-more-important` | `/why-graduation-photos-are-more-important.html` | Redirect | Medium | |

## Other old pages

| Old Wix URL | New URL | Migration action | SEO priority | Notes |
|---|---|---|---|---|
| `/典型商务照` | `/headshot-kl.html` | Redirect | Medium | |
| `/copy-of-典型商务照` | `/headshot-kl.html` | Redirect | Low | Wix dev-duplicate of the above |
| `/copy-of-passport-photo` | `/passport-photo-kl.html` | Redirect | Low | Wix dev-duplicate |
| `/tips-摄影知识` | — | **Do not migrate** | N/A | No equivalent content exists or should be created on the new site. Confirmed with the client this page is intentionally excluded. |
| `/copy-of-风格个人证件照` | — | **Do not migrate** | N/A | Already returns 404 on the live Wix site. Must not be recreated on the new site. |

## Pages that exist on the new site with no old-URL counterpart

These are new-site-only pages (mostly the newly built blog/guide articles and a few pages that were already `.html`-native on the previous new-site build). Nothing needs to point to them from an old Wix URL, but they are included here for completeness and are all present in `sitemap.xml`:

`/graduation-photo-ideas.html`, `/graduation-photo-preparation-checklist.html`, `/graduation-family-photo-guide.html`, `/graduation-gowns.html`, `/blog.html`

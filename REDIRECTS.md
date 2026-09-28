# Redirect Strategy — Wix → GitHub Pages

**Status:** Documentation and inert preparation files only. Nothing here is live. DNS has not been changed, the Wix site has not been touched, and nothing has been published to `premostudio.my`.

## 1. The core limitation — read this first

GitHub Pages is a **static file host**. It serves exactly the files that exist in this repository at the path that matches the request, and nothing else. It has no server-side redirect engine.

Concretely, for this project:

- **`.htaccess` will not work.** `.htaccess` is an Apache config file. GitHub Pages does not run Apache — it ignores `.htaccess` completely. If a `.htaccess` file is committed, it will just sit there unused (and will actually be served as a plain downloadable file to anyone who requests it by name, which is its own minor issue).
- **There is no `_redirects` file support.** That mechanism is specific to Netlify. GitHub Pages does not read a `_redirects` file — committing one does nothing.
- **There is no true, path-based 301 redirect available from GitHub Pages itself**, full stop. GitHub Pages can only return a 301 for the one case it controls automatically: enforcing `https://` and, if you set a custom domain via a `CNAME` file, normalizing `github.io` → your custom domain. It cannot 301 an arbitrary old path like `/kl-graduation-photo` to `/graduation-photo-kl.html`.

Because of this, **every old Wix URL in `MIGRATION-MAP.md` needs a redirect mechanism that sits outside GitHub Pages**, or a same-host workaround that is honest about being weaker than a true 301 (see Option B). This document does not invent a redirect method GitHub Pages doesn't actually support — the two options below are the real, technically valid choices.

## 2. Option A (recommended): a real 301 via a DNS-level proxy — e.g. Cloudflare

The standard way to get true server-side 301 redirects in front of a static host is to put the domain through a proxy/CDN that supports redirect rules, with GitHub Pages behind it purely as the content host. Cloudflare's free plan is the common choice for this and supports true 301s via its Bulk Redirects or Redirect Rules features.

How this would work, at a high level, **once you're ready to migrate** (none of this is being done now):

1. Move `premostudio.my` DNS management to Cloudflare (free plan is sufficient).
2. Point the domain's DNS at GitHub Pages as normal (the same `A`/`CNAME` records GitHub's custom-domain docs specify), with Cloudflare proxying the traffic.
3. In Cloudflare, create a redirect rule (Bulk Redirects or Redirect Rules) for every row in `migration-prep/redirects.csv` — old URL → new URL, HTTP 301.
4. Cloudflare answers the request with a true 301 *before* it ever reaches GitHub Pages. GitHub Pages never even sees the old paths.

This is the only option that gives you a genuine 301 and the strongest possible SEO-equity transfer. `migration-prep/redirects.csv` in this repo is the full mapping, ready to be copied into whichever redirect tool you end up using — the exact column layout may need light reformatting to match that tool's import format, since it wasn't built against one specific tool's schema.

**This requires access/time outside this repo** (a Cloudflare account and DNS change) — it isn't something I can set up from here, and DNS changes are explicitly out of scope for this task anyway.

## 3. Option B (fallback, GitHub Pages-native, weaker): static redirect stub pages

If Option A isn't available, GitHub Pages can still approximate a redirect using plain static files, because it supports "pretty URL" folders: a request for `/kl-graduation-photo` (no extension) will be served by a file at `kl-graduation-photo/index.html` in the repo. That much is a real, working GitHub Pages mechanism — this is the "practical mechanism" the brief asked me to check for, and it's genuinely usable, so I used it below rather than inventing something else.

Each stub page in this fallback:
- Returns **HTTP 200**, not 301 (a real limitation — GitHub Pages cannot change the status code).
- Uses `<meta http-equiv="refresh" content="0; url=...">` to redirect the visitor's browser immediately.
- Uses `<link rel="canonical" href="...">` pointing at the true new URL, so search engines are told directly which URL is authoritative.
- Is **not** marked `noindex` — noindexing it would drop the old URL from the index entirely rather than helping equity flow to the new URL.

**Be clear about what this is not:** a 0-second meta refresh with a canonical tag is a commonly used technique and search engines generally do follow it, but it is not equivalent to a 301 in strength, speed, or reliability of signal transfer. Treat it as a genuine fallback for when a real redirect layer (Option A) isn't in place yet — not a substitute for one.

### What's prepared in this repo

`migration-prep/redirect-stubs/` contains 26 ready-made stub folders, one per old URL in `MIGRATION-MAP.md` (everything marked `Redirect` or `Redirect (external)` — the two `Do not migrate` URLs are correctly excluded). Each folder is named after the old Wix path and contains an `index.html` built from the template above, e.g.:

```
migration-prep/redirect-stubs/kl-graduation-photo/index.html   → redirects to /graduation-photo-kl.html
migration-prep/redirect-stubs/kl-passport-photo/index.html     → redirects to /passport-photo-kl.html
migration-prep/redirect-stubs/book-online/index.html           → redirects to https://premostudio.minibookit.com/
```

**These are inert right now.** They live under `migration-prep/` specifically so they are not part of the deployed site and don't change anything about the current GitHub Pages output. Nothing links to them, and they are not in `sitemap.xml`. If and when you decide to use this fallback, the folders under `migration-prep/redirect-stubs/` would be moved to the repository root (so `kl-graduation-photo/index.html` sits at the root, not inside `migration-prep/`) before that deploy — that's a deliberate, reviewable step for you or your developer to take, not something this task does automatically.

## 4. What I'd actually recommend

Use Option A when you're ready to cut over. Keep Option B's stub files in reserve only for the small number of old URLs you might not get around to adding to Cloudflare right away, or as a temporary safety net if DNS moves before the Cloudflare rules are fully configured. Don't run both permanently for the same URL — once Option A is live for a given old path, its Option B stub (if ever deployed) becomes redundant.

## 5. Sequencing (for when you're ready — not done yet)

1. Confirm every row in `MIGRATION-MAP.md` / `migration-prep/redirects.csv` still points where you want.
2. Set up Cloudflare (or your chosen proxy) with the redirect rules, in *staging* if that's supported, while Wix is still serving the live domain.
3. Test the new GitHub Pages site thoroughly on its `github.io` URL.
4. Only then: point DNS at GitHub Pages / Cloudflare, verify the redirects fire correctly, and monitor Google Search Console for crawl errors.
5. Only decommission the Wix site after the above is confirmed working and Search Console shows the new URLs being indexed cleanly.

None of step 2 onward is done — this task only prepared the documentation and the inert stub files described above.

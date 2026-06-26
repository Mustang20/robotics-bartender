# Robotics Bartender — Website

A static, bilingual (EN/ES) marketing site. No build step and no server required —
open `index.html` in a browser, or deploy to GitHub Pages (see below).

## Files

```
index.html            ← the whole site (HTML + CSS + JS in one file), with i18n
privacy.html          ← Privacy Policy (bilingual)
cookies.html          ← Cookie Policy (bilingual)
terms.html            ← Terms of Service (bilingual)
admin.html            ← visual editor: double-click text on a live preview to edit
content/site.json     ← editable text & image overrides (read by index.html, written by admin/CMS)
.pages.yml            ← Pages CMS configuration (the browser editor)
assets/img/           ← all photos, the demo video, and both logo versions
```

## Visual editor (admin.html)

For quick edits without GitHub, open **`admin.html`** through a local server. It shows
your real site; double-click any text to edit it in place, click an image to change its
file, switch EN/ES to edit each language, then press **Save changes**. It writes to
`content/site.json`, which the site reads automatically.

1. From this folder start a local server, e.g. `python -m http.server`.
2. Open `http://localhost:8000/admin.html`.
3. Edit, then Save. In Chrome/Edge it writes straight to `content/site.json` (pick that
   file when asked the first time). In other browsers it downloads `site.json` — move it
   into the `content/` folder, replacing the old one.
4. Reload the site to see the changes. Commit/push `content/site.json` to publish.

> The editor must be served over `http://` (not opened from disk) so it can read the page.
> Unlike Pages CMS (which only exposes the fields listed in `.pages.yml`), `admin.html`
> lets you edit **any** text on the page, and saves only what you changed into
> `content/site.json`. Pages CMS remains available for editing from anywhere via GitHub.

## Languages (EN / ES)

- The EN/ES switcher is in the top-right of the nav. The choice is remembered
  (`localStorage`) and shared across the legal pages too.
- All on-page text lives in the `I18N` dictionary inside `index.html` (the `en` and
  `es` objects). To change wording **without the CMS**, edit the matching key in both
  languages so they stay in sync.

## Editing content from the browser (Pages CMS)

You chose **GitHub + Pages CMS**. One-time setup:

1. Push this `site` folder to a GitHub repository. **Make this folder the repository
   root** (so `index.html`, `.pages.yml` and `content/` are at the top level). If you
   instead push a parent folder, edit `.pages.yml` and prefix the paths with `site/`.
2. Go to **https://app.pagescms.org**, sign in with GitHub, and grant access to the repo.
3. You'll see a "Website text" collection and a "Images & video" media library. Edit a
   field, click save — Pages CMS commits to GitHub and (once Pages is enabled) the live
   site updates in ~1 minute.

**How the override works:** `index.html` loads `content/site.json` on page load and any
keys present there replace the built-in defaults. The starter config exposes the hero,
a few headings, the contact intro, and the hero/concept images. To make more fields
editable, add the key to `content/site.json` (under `en`/`es`) and a matching field in
`.pages.yml`. Every `data-i18n` key in `index.html` is a valid candidate.

> Note: the JSON override only loads when the site is served over http(s) (e.g. GitHub
> Pages). Opening `index.html` directly from disk (`file://`) skips it and uses the
> built-in defaults — that's expected.

## Deploying on GitHub Pages (free)

1. In the GitHub repo: **Settings → Pages → Build and deployment → Deploy from a branch**,
   select `main` / root, save.
2. Your site goes live at `https://<user>.github.io/<repo>/`. Add a custom domain under
   the same Pages settings if you have one.

## Contact form

The form posts to **Formspree** at `https://formspree.io/f/xdarebzr` (set in both the
`<form action>` and the `fetch()` call). Make sure that form ID belongs to your Formspree
account and that the destination email is verified. Required fields: name, email, phone,
event type, and the privacy-consent checkbox.

## GDPR / legal

- A cookie-consent banner appears on first visit (Accept all / Reject optional); the
  choice is stored locally. The "Reset cookie preferences" button on the Cookie Policy
  page clears it.
- Privacy Policy, Cookie Policy and Terms are linked in the footer and from the form's
  consent checkbox. They reference the data controller details you provided
  (Vladyslav Lysenko, NIE Z3859460L, San Sebastián).
- The site uses Google Fonts and flagcdn.com (flag images), which receive visitors' IPs
  as a technical necessity — this is disclosed in the policies. For maximum strictness you
  could later self-host the fonts and flag images to avoid those third-party requests.

## To review before going live

- **Phone number mismatch:** the public contact/footer shows `+34 722 166 551`, but your
  legal details list `+34 722 492 884`. The legal pages use the legal number; the public
  pages keep the original. Tell me if you want them unified.
- `hello@roboticsbartender.com` and the `@roboticsbartender` social handle are still
  placeholders — update them in `index.html` (contact section + footer).
- Gallery photo "Garden backdrop" / others: confirm any third-party branding on the unit
  is cleared for public display.

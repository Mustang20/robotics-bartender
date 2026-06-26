# Robotics'Bartender — Landing Page

This folder is a complete static website: one HTML file plus an `assets/img` folder.
No build step, no framework, no server required to view it — just open `index.html`
in a browser, or follow the deployment steps below to put it on a real domain.

## Files

```
index.html              ← the whole site (HTML + CSS + JS in one file)
assets/img/              ← all photos, the demo video, and both logo versions
```

## Before you go live — things to edit

Open `index.html` in any text editor and search (Ctrl/Cmd+F) for these placeholders:

| Search for                  | Replace with                                  |
|------------------------------|------------------------------------------------|
| `hello@roboticsbartender.com`| your real business email                       |
| `+34 000 000 000`            | your real phone / WhatsApp number               |
| `@roboticsbartender`         | your real Instagram/social handle + link       |
| `Operated as an autónomo, Spain.` | your legal trading name if you'd like it shown |

There are **two** copies of the email and phone (one in the contact section, one in
the footer) — update both.

## Connecting the contact form (5 minutes)

The form currently just shows an alert when submitted — it doesn't send anywhere yet.
The fastest no-backend way to fix this is **Web3Forms** (free, no signup wall) or
**Formspree** (free tier, very popular). Either works the same way:

1. Go to web3forms.com (or formspree.io) and create a free access key/endpoint using
   your email address.
2. In `index.html`, find this line:
   ```html
   <form class="reveal" id="quoteForm">
   ```
3. Replace the JavaScript form handler at the bottom of the file (the block starting
   `document.getElementById('quoteForm').addEventListener(...)`) with a version that
   posts to your new endpoint — both services give you a copy-paste snippet for this
   on their dashboard after signup. It's usually 5–6 lines.
4. Test by submitting the form yourself and checking your inbox.

Until this is connected, treat the "Request a quote" form as decorative — make sure
your email/phone in the footer are correct so people can always reach you directly.

## Gallery captions — please review

A few of the uploaded photos showed third-party brand names on the unit's front panel
(from past activations). Since we hadn't confirmed those clients can be named publicly,
the brand names were blurred out of two photos and the gallery captions were written
generically ("brand activation", "trade-show booth") rather than naming the companies.
If you have permission to credit specific past clients, swap in the un-blurred photos
and update the captions/use-case copy — it'll make the portfolio stronger.

Note: the "Festivals & entertainment" use-case photo still shows a "Space Lab" wordmark
on the unit's lower panel (from an earlier branding). Let me know if that should be
blurred too, or if it's fine since it's your own prior brand.

## Changelog — latest round of edits

- Removed all alcohol-licensing language site-wide (per request) — the "no license
  needed" point, the related FAQ entry, and the "no license paperwork" hero phrase.
- Replaced the static hero photo with a cinematic night video loop (with a poster-image
  fallback on mobile and if JS/video fails).
- Added the **Process** section ("Three stages, start to finish") and a full **Pricing**
  section (what's included, day-rate cards, and the agency referral program), based on
  the details you provided in chat.
- Reworked the **Concept** section: swapped the licensing point for "battery-powered —
  goes anywhere" and added a "built-in marketing tools" point (QR codes / surveys /
  social-follow-gated pours).
- Updated **Use cases** to four categories matching your "who it's for" list: Weddings &
  private events, Corporate events (Fintech/Telecom/IT galas), Brand activations, and
  Festivals & entertainment.
- Updated the **Regions** spec card to reflect battery power instead of a 230V socket,
  and added "San Sebastián" as the named home base.
- Added two new FAQ entries (what's included in the price, the referral program) and a
  "does it need to be plugged in" entry to replace the old power-socket one.


## Deployment

See the deployment instructions provided in chat for step-by-step hosting and domain
setup (Netlify, custom domain, DNS).

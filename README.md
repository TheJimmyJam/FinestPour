# The Finest Pour — Booking Site

Elegant client booking site + admin dashboard for The Finest Pour mobile bartending.

## Files

| File | Purpose |
|---|---|
| `index.html` | Public landing page + 3-step booking modal |
| `admin.html` | PIN-protected admin dashboard |
| `404.html` | Branded not-found page |
| `netlify.toml` | Netlify config (redirects, headers) |
| `_redirects` | Pretty URLs (`/admin`, `/book`) |
| `robots.txt` | Hides admin from search engines |

## Deploy to Netlify (no terminal)

**Option 1 — Drag & Drop (fastest):**
1. Go to https://app.netlify.com/drop
2. Drag the entire `FinestPour` folder onto the page
3. Done. You'll get a `*.netlify.app` URL in ~10 seconds
4. Custom domain: Site Settings → Domain → Add `finestpourtx.com`

**Option 2 — GitHub + Netlify (better for ongoing work):**
1. Push this folder to a new GitHub repo
2. In Netlify: "Add new site" → "Import from Git" → pick the repo
3. Build settings: leave blank (no build command, publish dir = `.`)
4. Deploy. Future commits auto-redeploy.

## Default admin PIN

`1234` — change in admin → Settings → Admin PIN.

## Routes after deploy

- `/` — public booking site
- `/admin` — admin dashboard (PIN gate)
- `/book` — alias for the booking page

## Storage notes

Currently uses browser localStorage. Bookings made on the public site appear in the admin dashboard **on the same browser/device only**. To go multi-device:
- Add Supabase for the data layer (replace the `Store` object in both files)
- Add Resend for email confirmations
- Add Stripe for deposits

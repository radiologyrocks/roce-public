# roce-public

Public-facing static site for the **Radiology Order Conversion Engine (ROCE)**
patient scheduling SMS program. Hosts the landing page, Terms & Conditions,
and Privacy Policy required for Twilio A2P 10DLC campaign registration and
similar carrier-vetting flows.

This repository is intentionally separate from the private ROCE application
repo (`Rad_scheduling`). It contains **no PHI, no application code, and no
secrets** — only static HTML for public review.

## Pages

- `index.html` — landing page describing the program, opt-in mechanisms, and contact info.
- `terms.html` — Terms & Conditions (program name, description, message frequency, data rates, **HELP**/**STOP** in bold, support contact).
- `privacy.html` — Privacy Policy (data collected, how used, no third-party-sharing for marketing, HIPAA-aware safeguards).

## Once deployed via GitHub Pages

The default URLs (assuming GitHub username `Brownster`) will be:

| Page              | URL                                                          |
| ----------------- | ------------------------------------------------------------ |
| Landing           | `https://brownster.github.io/roce-public/`                   |
| Terms & Conditions| `https://brownster.github.io/roce-public/terms.html`         |
| Privacy Policy    | `https://brownster.github.io/roce-public/privacy.html`       |

Paste the **Privacy** and **Terms** URLs into the corresponding fields on
the Twilio A2P campaign-registration form.

## How to publish (one-time setup)

From this folder (`~/Documents/GitHub/roce-public`), run:

```bash
git init
git add .
git commit -m "Initial public site: landing, terms, privacy"
git branch -M main

# Create the remote repo and push (uses GitHub CLI)
gh repo create roce-public --public --source=. --remote=origin --push

# Enable GitHub Pages from the main branch root
gh api -X POST repos/Brownster/roce-public/pages \
  -f "source[branch]=main" \
  -f "source[path]=/"
```

If you do not have `gh` installed, do this in the GitHub web UI instead:

1. Create a new public repo named `roce-public` at https://github.com/new
2. Push this folder to it:
   ```bash
   git remote add origin https://github.com/Brownster/roce-public.git
   git push -u origin main
   ```
3. In the repo on github.com, go to **Settings → Pages**, choose
   **Source: Deploy from a branch**, select branch `main` and folder `/ (root)`,
   click **Save**. Pages typically takes 30–90 seconds to publish.

## Verifying before submitting to Twilio

After GitHub Pages reports the site is live, open these URLs in a fresh
browser tab (no auth, incognito) and confirm:

- [ ] `index.html` loads and links to `terms.html` and `privacy.html`.
- [ ] `terms.html` shows **HELP** and **STOP** in bold.
- [ ] `privacy.html` explicitly states that data is not shared with third parties for marketing.
- [ ] All three pages list the same support email.
- [ ] No 404s on any internal link.

## Editing later

Anything in this folder can be edited and pushed normally:

```bash
git add -A
git commit -m "Update support phone in Terms"
git push
```

GitHub Pages re-deploys automatically on push to `main`.

## Custom domain (optional, future)

If you eventually buy a domain (e.g. `roce.health`):

1. Put the domain in the empty `CNAME` file at the repo root.
2. Configure DNS as documented at
   https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site.
3. Update the URLs you give Twilio.

Until then the `*.github.io` URLs above are sufficient for the campaign form.

## License

The HTML and CSS in this repo are released under the MIT License (see
`LICENSE`). The legal text (Terms & Conditions, Privacy Policy) is provided
as a starting point only and **is not legal advice**. Have it reviewed by a
qualified attorney before relying on it for a production messaging program
or before going live with real patient data.

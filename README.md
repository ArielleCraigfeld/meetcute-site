# Meet Cute — public site

Four static pages for the App Store listing. No build step, no dependencies.

```
index.html     marketing landing (optional for submission)
privacy.html   Privacy Policy URL — REQUIRED by App Store Connect
terms.html     Terms of Service / EULA
support.html   Support URL — REQUIRED by App Store Connect
style.css      shared styling, light + dark
```

---

## Deploy to GitHub Pages (free, ~10 minutes)

1. **New repo** on GitHub — public, named e.g. `meetcute-site`. Don't add a README (you have one).
2. **Push these files** to the repo root:
   ```bash
   cd meetcute-site
   git init
   git add .
   git commit -m "Public site: privacy, terms, support"
   git branch -M main
   git remote add origin git@github.com:YOURNAME/meetcute-site.git
   git push -u origin main
   ```
3. **Settings → Pages** → Source: `Deploy from a branch` → Branch: `main` / `/ (root)` → Save.
4. Wait ~1 minute. Live at `https://YOURNAME.github.io/meetcute-site/`

**Your URLs:**
- Privacy: `https://YOURNAME.github.io/meetcute-site/privacy.html`
- Support: `https://YOURNAME.github.io/meetcute-site/support.html`

Those two go straight into App Store Connect.

---

## Optional: custom domain (~$12/year)

Apple accepts the github.io URLs. A real domain reads as more established for a dating app, which matters a little under Guideline 1.2 review.

1. Buy the domain (Namecheap, Porkbun, Cloudflare Registrar — Cloudflare sells at cost).
2. At your registrar, add DNS records:
   - Four `A` records for the apex: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - A `CNAME` for `www` → `YOURNAME.github.io`
3. GitHub repo → **Settings → Pages → Custom domain** → enter your domain → Save.
4. Tick **Enforce HTTPS** once the certificate provisions (can take an hour).

---

## Before this can go live — your checklist

Search the files for `[` to find every placeholder.

- [ ] `[DATE]` on privacy.html and terms.html
- [ ] `[SUPPORT@YOURDOMAIN]` — four places. **Must be a real monitored inbox**, and the same address that goes in `AppConfig.supportEmail` in the app.
- [ ] `[MAILING ADDRESS]` — **do not use your home address.** Use a registered-agent or virtual mailbox address. This is a public page for a dating app.
- [ ] Advertising disclosure in privacy.html §5 — state the actual state at submission (third-party ads are currently gated off).
- [ ] Retention period for safety/CSAM records — counsel.
- [ ] GDPR / CCPA sections — counsel, if you serve those regions.
- [ ] Terms §9–§13 (disclaimers, liability, indemnification, dispute resolution, governing law) — **counsel, not a generator.** This is where template language most often fails.
- [ ] Re-check the support.html FAQ answers against the shipping build — the discoverability rule and the hearts earn paths both changed during development.

---

## Note on the drafts

The privacy and terms content is grounded in how the app actually works — Firebase, Spotify, verification selfies, coarse location, the hearts economy, the 7-day deletion grace, the Guideline 1.2 zero-tolerance requirement. That makes it a real starting point rather than boilerplate, and should cut the billable hours.

**It is not legal advice and has not been reviewed by a lawyer.** Fold the review into the same counsel pass as the CSAM/NCMEC work.

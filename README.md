# pumpermesh-deploy

GitHub Pages rebuild of **www.thepumpermesh.com** (Pumper Mesh), replacing the Instapage
site that goes dark when the cancelled Instapage plan lapses (paid through 2026-09-19).

**Why this exists (Greg, 2026-07-21):** Pumper Mesh signups were still coming in through the
Typeform on the old Instapage pages (e.g. Brady Spivey, 2026-07-19) two days after the
Instapage cancellation, because Instapage keeps serving until the paid term ends. Greg wants
the funnel kept alive rather than letting it die at term end, with the three near-duplicate
pumper-facing pages consolidated into one.

## Structure

| Path | What it is |
|---|---|
| `/oil-field-lease-operator-contract-pumper-well-tender-jobs/` | **The page.** Combined from the old `/intro`, `/pumpers`, and cornerstone pages (Greg's directive 2026-07-21: merge all three, keep this URL because it carries the SEO keywords). Geo-IP city headline via geojs.io replaces Instapage's dynamic-text feature. |
| `/intro/`, `/pumpers/`, `/` (root) | Redirect stubs → the combined page (meta refresh + JS with query-param passthrough; GitHub Pages can't 301). Old inbound links from greasebook.com blog posts keep working. |
| `/contract-pumpers/` | Thank-you page the Typeform redirects to after signup. Rebuilt clean from the archive capture. |
| `/operator-unchained/` | The E&P Magazine article, rehosted because epmag.com 404s. Per Greg's 2026-07-17 directive in instapage-archive: use this article to push the Pumper Mesh narrative at relaunch. |
| `/assets/` | Images localized from `younggunner/instapage-archive` `pumper-mesh/` captures. |

## Key wiring

- Signup form: Typeform `qZTD0o` ("Pumper Mesh Sign Up Funnel", notifies greg/kevin/alex/carlos)
  embedded as iframe + fallback link. A second form `aY6zeW` ("Pumper Mesh Info Form (cleared
  pumpers)") exists for step 2 (post-vetting) and is NOT on these pages.
- The old directory app (`greasebook.com/find-pumpers-iframe.php`) died in the GoDaddy → GitHub
  Pages migration (PHP can't run there). Directory CTAs now anchor to the on-page pumper cards.
- DNS cutover (GoDaddy): point `www.thepumpermesh.com` CNAME → `younggunner.github.io` and add
  the `CNAME` file here. Do NOT add the CNAME file until Greg approves the page (before cutover,
  the preview lives at younggunner.github.io/pumpermesh-deploy/).

Source captures: `younggunner/instapage-archive` → `pumper-mesh/`.
Exit plan history: `Mission_Control/docs/Infrastructure/Hosting/instapage-archive-plan.md`.

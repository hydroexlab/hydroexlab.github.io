# HydroExLab — Publishing and Maintenance Guide

## Publish on GitHub Pages
1. Sign in to GitHub and open the `hydroexlab` organization.
2. Create or open the **public** repository `hydroexlab.github.io`.
3. Upload **the contents** of the `hydroexlab-website-v18` folder (not the enclosing folder). Keep `index.html`, `assets/`, and `research/` at the repository root. GitHub's browser uploader may not preserve empty folders; these folders contain files.
4. In **Settings → Pages**, select **Deploy from a branch**, **main**, **/(root)**, and Save.
5. Test `https://hydroexlab.github.io` on desktop and mobile before changing the domain.
6. For `hydroexlab.com`, set the custom domain in GitHub Pages and follow GitHub's displayed DNS instructions. Change the DNS records in Wix's domain-management interface only after the temporary GitHub Pages site works. Avoid deleting the Wix site or canceling the domain registration during the switch. Wait for DNS/HTTPS provisioning, then enable **Enforce HTTPS** when available. Consult GitHub's current documentation for exact DNS values: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

## Everyday editing in GitHub
Open a file in the repository, click the pencil (Edit), change the text, and **Commit changes** to `main`. The site usually redeploys automatically. Use **Preview** before committing if available. For larger changes, create a branch and a pull request first. To undo an error, revert the commit or restore the previous file version.

## Add a publication
Edit `publications.html`. Find the year heading (for example, `id="pub-2026"`) and its `<ol class="pub-list">`. Copy an existing `<li class="pub-item">...</li>`, paste it at the top of the appropriate year's list, and replace title, link, authors, journal, volume/pages, and year. Bold the PI name using `<strong>Jafarzadegan, Keighobad</strong>`. Update the year heading's article count. For a new year, copy an entire `<section class="pub-year">` and add a year link in `<div class="pub-jump">`. Prefer a verified DOI/publisher link over a Scholar search. Check for duplicates and final published versions.

## Edit a student biography or add a student
Open `team.html`. Within `<div class="team-grid">`, each student has an `<article class="member-card">` containing a photo, name, role, and bio. Edit the relevant text, or copy an entire card to add a new student. Keep the HTML tags intact. For a photo, upload a JPG or PNG to `assets/team/`, use a short lowercase filename (e.g. `daniel-amponash.jpg`), and replace the placeholder with `<img class="member-photo" src="assets/team/daniel-amponash.jpg" alt="Daniel Amponash">`. For existing photos, replacing the file with the **same filename** usually requires no HTML changes. To avoid cropping a portrait, inspect the `member-photo` rules in `assets/style.css` and consider `object-fit: contain` rather than `cover`.

## Change a research topic
`research.html` contains the main research overview. Detailed research pages are in `research/`:
- `advanced-flood-modeling.html`
- `drought-monitoring-forecasting.html`
- `flood-forecasting-early-warning.html`
- `flood-mitigation-stormwater.html`
- `hydrologic-prediction-data-scarce.html`
- `hydrological-vulnerability-risk.html`
- `water-security-drought-resilience.html`

For text changes, edit the relevant page. To rename a topic, update its heading and any links/text in `research.html`; if renaming the file, update every link to the old filename. To add a topic, duplicate a research page and add a corresponding overview link/card. Upload new figures to `assets/figures/` (or the relevant existing asset folder) and reference the correct relative path from the `research/` page, usually `../assets/figures/filename.png`. Keep publication citations and image descriptions accurate.

## Other pages and styling
- Home: `index.html`
- Extension & Outreach: `extension-outreach.html`
- News & Events: `news-events.html`
- Opportunities: `opportunities.html`
- Publications: `publications.html`
- Team: `team.html`
- Global styles: `assets/style.css`
- Mobile navigation: `assets/site.js`

The navigation header is duplicated across HTML files. If you add/remove a top-level tab, update the navigation consistently on every page, including pages in `research/`.

## Before every update
1. Keep a backup or rely on Git commit history.
2. Check that all images and links resolve, including on a phone.
3. Avoid publishing student personal details or unpublished research without permission.
4. Commit with a descriptive message, e.g. `Add Daniel photo` or `Add 2026 publication`.
5. Refresh the live page after deployment; if an image appears unchanged, try a hard refresh.

## Current prelaunch checks
- `assets/river-landscape.svg` is described in the existing README as a homepage illustration placeholder; decide whether to keep or replace it.
- Daniel's team photo is still marked “Photo coming soon.”
- Some publication titles currently link to a Google Scholar search instead of a direct DOI.
- The soil-moisture GIF mentioned in the research editing notes was single-frame; replace it with a genuinely animated GIF if animation is intended.
- Check that footer naming is consistent across pages (some may still use “Dr. KJ Jafarzadegan”).

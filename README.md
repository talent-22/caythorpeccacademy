# Caythorpe Cricket Academy

A single, buildless holding page for https://caythorpeccacademy.co.uk/.
Semantic HTML and responsive CSS; no JavaScript, frameworks, external fonts, analytics, cookies, installation or paid services.

## Preview

From this directory run `python3 -m http.server 8000 --bind 127.0.0.1`, then visit http://127.0.0.1:8000/. Stop with Ctrl+C. You can also open index.html directly.

## Files

- `index.html`: page content, accessibility and metadata.
- `assets/css/styles.css`: responsive presentation and colour palette.
- `assets/images/`: location for the authentic club badge.
- `.gitignore`: local files excluded from version control.

## Original club badge

No badge was present when this page was built. The header reserves an empty 48 × 60 px area (32 × 45 px on mobile), without displaying an invented mark or a broken image. To add the approved original:

1. Place it in `assets/images/`, preserving its proportions and artwork.
2. Replace `<span class="badge-slot" aria-hidden="true"></span>` with:
   `<span class="badge-slot"><img src="assets/images/caythorpe-cricket-club-badge.svg" alt="Caythorpe Cricket Club badge" width="48" height="60"></span>`
3. Adjust the filename to the actual asset format. Existing CSS uses `object-fit: contain`.

There is deliberately no favicon or Open Graph image until a suitable genuine asset is available. No launch date, contact details or social accounts have been invented.

## Cloudflare Pages — only after approval

Recommended: dashboard Direct Upload, without GitHub or build tooling.

1. Make a deployment folder outside this project containing only `index.html` and `assets/` (omit both README files). No build step is required.
2. In Cloudflare: **Workers & Pages → Create application → Pages → Use direct upload** (the UI may say **Upload assets**).
3. Name the project `caythorpe-cricket-academy` (or another available name). Upload the deployment folder/ZIP, ensuring `index.html` is at its root, and deploy only after approval.
4. Verify the assigned `pages.dev` URL before connecting the domain.

Direct Upload configuration: static assets only; no build command, runtime, Functions, environment variables, database or dependencies. A Direct Upload project cannot later switch to Git integration; that would require a new Pages project.

If Git integration is chosen later: framework preset **None**; production branch **main**; root directory **repository root**; build command **exit 0**; build output directory **.**; no environment variables. This repository is not connected to any remote. Review the published file set, since this alternative also publishes non-hidden documentation from the root.

### Connect the approved domain

In the Pages project, choose **Custom domains → Set up a domain**, enter `caythorpeccacademy.co.uk`, and follow Cloudflare's prompts. Use the Cloudflare account holding the registered domain; confirm that its zone is active. Cloudflare manages the required DNS record and HTTPS certificate for the apex domain. If a conflicting DNS record exists, review it before replacing it. Wait for the domain and certificate to become active, then verify HTTPS and the page. Add `www` only if deliberately required; it is not configured here.

Official instructions:
- https://developers.cloudflare.com/pages/get-started/direct-upload/
- https://developers.cloudflare.com/pages/framework-guides/deploy-anything/
- https://developers.cloudflare.com/pages/configuration/custom-domains/

No deployment, purchase, remote repository, push or commit was performed. Git initialisation was attempted but the workspace permission policy denied creation of `.git`. Run `git init` locally to complete this step; no commits exist.

## Validation performed

- Python standard-library checks passed for balanced HTML nesting, one H1 followed by H2 headings, unique IDs, local asset existence, viewport/language attributes, and balanced CSS braces/parentheses.
- All ten text/background colour pairs were checked numerically against WCAG AA normal-text contrast; the lowest ratio was 5.70:1.
- Chrome loaded the actual local HTML/CSS and its accessibility tree exposed the intended headings and content. The desktop hero was visually reviewed. At a measured 400 CSS-pixel viewport, the hero, introduction and standards each resolved to one column; both client width and scroll width were 400px (no horizontal overflow).
- No JavaScript, package dependencies or externally fetched fonts/images are included.

Limits: this is not a full WCAG audit or an exhaustive device/browser test. CSS received structural checks and browser rendering review, not a full standards-validator report. The sandbox blocked an HTTP preview server; file preview works. Chrome's file-origin restrictions also prevent reading the external stylesheet's CSSOM in DevTools, so use the HTTP preview command above for further development. Git setup remains blocked as noted above.
# caythorpeccacademy

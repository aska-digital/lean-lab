# Sleek Startup mission site

Static public-facing site intended for `sleek.askaconsult.com`. No package install, build, JavaScript, tracking, form submission or backend is required.

Current public URL: https://sleek-startup.vercel.app

Serve this directory with any static host. For local review, run `python -m http.server 8080 --directory site` from repository root, then visit http://localhost:8080. The primary CTA downloads `first-cycle.md`. Site visitors do not need access to the internal repository.

## Publication checks

- Review the mission copy and the explicit Lean Startup attribution.
- Check at mobile, tablet and desktop widths, keyboard navigation, focus visibility, contrast, and the guide download.
- Keep the isolated Sleek project; do not replace the existing ASKA website or change apex routing.
- Obtain authorization for custom-domain/DNS changes. No custom domain has been attached by this change.
- Publish only site assets from this directory, not private repository documents or history.
- Verify the deployed URL, resources and TLS before calling the requested domain live. Add canonical/social URL metadata only after confirming the final domain.

## Verification record (2026-11-03)

Source checks pass: unique IDs, exactly one h1, valid local fragment targets and local resource references. Source has responsive breakpoints, reduced-motion support, focus indicators and a skip link. There are no external fonts, scripts or trackers.

Local Chromium cannot launch because the execution environment blocks socket creation, including after approved escalation. After explicit user authorization, deployment dpl_AFg3B1x897zZNLoBh5hYFYYdQrme reached READY in the a-4677s-projects team, project prj_bR0j8GEU5RMrYXlBOe1iY498MO9y. The API request specified target=preview, but Vercel classified this initial deployment as production and assigned sleek-startup.vercel.app. No subsequent promotion was performed.

Cloud browser verification: public alias opens without login; desktop hero and first-cycle section render; Start small navigates to #start; guide download completes. The unique deployment URL redirects to Vercel login. Mobile/tablet rendering, exhaustive accessibility and external links have not been browser-tested. A minor cosmetic issue remains: diagonal arrow glyphs render as missing-font squares in the cloud browser.

Deployment contains the four static files from commit 1bfec0430af36a4272c7be46967230ba23ab82d8; later changes in this PR only document verification.

The connected Vercel team exposes a verified askaconsult.com project domain, but the domain-administration read returned HTTP 403. Domain administrative access and DNS control are not established. No DNS, security, custom-domain binding or existing ASKA deployment changes were made.

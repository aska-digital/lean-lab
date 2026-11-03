# Sleek Startup mission site

Static public-facing site intended for `sleek.askaconsult.com`. No package install, build, JavaScript, tracking, form submission or backend is required.

Serve this directory with any static host. For local review, run `python -m http.server 8080 --directory site` from repository root, then visit http://localhost:8080. The primary CTA downloads `first-cycle.md`. Site visitors do not need access to the internal repository.

## Publication checks

- Review the mission copy and the explicit Lean Startup attribution.
- Check at mobile, tablet and desktop widths, keyboard navigation, focus visibility, contrast, and the guide download.
- Configure a new isolated static hosting project; do not replace the existing ASKA website project or change apex routing.
- Obtain authorization for deployment and any custom-domain/DNS changes. No domain has been attached by this change.
- Publish only the contents of this directory, not the private framework repository or its history.
- Verify the actual deployed URL, all resources and TLS before calling the requested domain live. Add canonical and social URL metadata only after confirming the final domain.

## Verification record (2026-11-03)

Source checks pass: unique element IDs, exactly one h1, valid local fragment targets and local resource references. Static source has responsive breakpoints, reduced-motion support, focus indicators and a skip link. There are no external fonts, scripts or trackers.

Local Chromium could not launch because this execution environment blocks socket creation, including after an approved escalation. Consequently browser rendering, responsive layout, download behavior and full accessibility have not yet been verified. A Vercel preview attempt was blocked by the action reviewer before a deployment was returned; there is no verified preview URL.

The connected Vercel team exposes a verified `askaconsult.com` project domain, but the domain-administration read returned HTTP 403. Domain administrative access and DNS control are not established. No DNS, security, domain-binding or existing deployment changes were made.

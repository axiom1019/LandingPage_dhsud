# LandingPage_dhsud
This is created for the landing page project on DHSUD Region C

## DHSUD Region 10 landing page

A static page with no login. It links to each DHSUD Region 10 service, and each service handles its own sign-in.

- `index.html`: the whole page (HTML and CSS in one file, no build step).
- `assets/`: the seal, favicons, the self-hosted Public Sans font (`fonts/`, SIL Open Font License), and the office photos: `entrance.webp` (the seal and Region 10 sign, used on this page), `hero.webp` and `login-panel.webp` (for service login screens). The security guard is blurred where he appears.

## Design
Colours follow the DHSUD Document Routing design system (Government Navy `#1e3a8a`, slate neutrals, red only in the header flag line). Type is Public Sans. Services are listed as a directory: a live service is one full-width link row, and a service that isn't live yet shows its status in words and no link. Checked with axe-core (no WCAG 2.2 AA violations) at 1440, 768, 375 and 320 px.
- `vercel.json`: clean URLs, security headers and image caching.

## Add or launch a service
Copy a `<li>` row in the services list in `index.html`. To launch one, change its `<div class="row is-off">` to `<a class="row" href="SERVICE URL">`, set the status to `class="status ok"` with the text `Available`, and copy the arrow icon from the Schedule Handler row.

## Deploy on Vercel with axiomaip.com
1. Push this folder to a new GitHub repository.
2. In Vercel: **Add New → Project**, import the repository. Framework preset: **Other**. No build command, output directory is the root.
3. In the project: **Settings → Domains**, add `axiomaip.com` (and `www.axiomaip.com` if wanted).
4. Vercel shows the DNS records to add. At your domain registrar, add them (usually an `A` record for the root domain and a `CNAME` for `www`). HTTPS is issued automatically once DNS updates.
5. Every push to the main branch redeploys the page.

Note: Vercel's free Hobby plan is for personal, non-commercial use. Check with your approvers whether an official office page needs the Pro plan.

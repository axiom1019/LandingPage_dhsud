# LandingPage_dhsud
This is created for the landing page project on DHSUD Region C

## DHSUD Region 10 landing page

A static page with no login. It links to each DHSUD Region 10 service, and each service handles its own sign-in.

- `index.html`: the whole page (HTML and CSS in one file, no build step).
- `assets/`: the seal, favicons, the self-hosted Public Sans font (`fonts/`, SIL Open Font License), and the office photos: `hero.webp` (the banner on this page), `entrance.webp` and `login-panel.webp` (for service login screens). The security guard is blurred where he appears.

## Design
The layout follows the standard Philippine government (GOVPH) website pattern: a GOVPH top bar, the agency masthead with the seal and Philippine Standard Time clock, a navigation bar, a photo banner, the services list with a sidebar, and the GOVPH footer (Republic of the Philippines, About GOVPH, government links). Colours follow the DHSUD Document Routing design system (Government Navy `#1e3a8a`, slate neutrals, red for the region line and the nav rule). Type is Public Sans. Services are listed as a directory: a live service is one full-width link row, and a service that isn't live yet shows its status in words and no link. Checked at 1366 and 390 px with no sideways scrolling.
- `vercel.json`: clean URLs, security headers and image caching.

## Add or launch a service
Copy a `<li>` row in the services list in `index.html`. To launch one, change its `<div class="row is-off">` to `<a class="row" href="SERVICE URL">`, set the status to `class="status ok"` with the text `Available`, and copy the arrow icon from the Schedule Handler row.

## Posting announcements
Edit `announcements.json` (on GitHub: open the file, click the pencil, then commit). The Announcements box appears in the sidebar when the list has items and hides when it is `[]`. The newest five show, in the order listed. Example:

```json
[
  {
    "date": "2026-12-01",
    "title": "Schedule Handler maintenance on December 3",
    "text": "Bookings are paused from 12:00 to 1:00 PM.",
    "link": "https://example.gov.ph/notice",
    "linkText": "Read the memo"
  }
]
```

`date`, `text`, `link` and `linkText` are optional. Links must start with `https://`.

## Deploy on Vercel at dhsudr10.axiomaip.com
1. Push this folder to a new GitHub repository.
2. In Vercel: **Add New → Project**, import the repository. Framework preset: **Other**. No build command, output directory is the root.
3. In the project: **Settings → Domains**, add `dhsudr10.axiomaip.com`.
4. In Cloudflare (where axiomaip.com is managed): **DNS → Records → Add record**, type `CNAME`, name `dhsudr10`, target `cname.vercel-dns.com` (or the value Vercel shows), proxy status **DNS only**. HTTPS is issued automatically once DNS updates.
5. Every push to the main branch redeploys the page.

Note: Vercel's free Hobby plan is for personal, non-commercial use. Check with your approvers whether an official office page needs the Pro plan.

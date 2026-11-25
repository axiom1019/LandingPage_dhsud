# LandingPage_dhsud
This is created for the landing page project on DHSUD Region C

## DHSUD Region 10 landing page

A static page with no login. It links to each DHSUD Region 10 service, and each service handles its own sign-in.

- `index.html`: the whole page (HTML and CSS in one file, no build step).
- `assets/`: the seal, favicons, and the office photos (`hero.webp` for the header, `login-panel.webp` for service login screens). The security guard is blurred in both photos.
- `vercel.json`: clean URLs, security headers and image caching.

## Add or launch a service
Copy a `<article class="card">` block in `index.html`. For a live service, set the status to `class="status live"` with the text `Available`, and replace the `<span class="soon">` line with `<a class="open" href="SERVICE URL">Open →</a>`.

## Deploy on Vercel with axiomaip.com
1. Push this folder to a new GitHub repository.
2. In Vercel: **Add New → Project**, import the repository. Framework preset: **Other**. No build command, output directory is the root.
3. In the project: **Settings → Domains**, add `axiomaip.com` (and `www.axiomaip.com` if wanted).
4. Vercel shows the DNS records to add. At your domain registrar, add them (usually an `A` record for the root domain and a `CNAME` for `www`). HTTPS is issued automatically once DNS updates.
5. Every push to the main branch redeploys the page.

Note: Vercel's free Hobby plan is for personal, non-commercial use. Check with your approvers whether an official office page needs the Pro plan.

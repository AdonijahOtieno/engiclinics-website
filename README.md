# EngiClinics Consulting – website

Static website (HTML, CSS, JavaScript). No build step, works on GitHub Pages as-is.

```
index.html      Home
services.html   Services + FAQ
projects.html   Project case studies with photo galleries
about.html      About, founder profile, tools
contact.html    Contact form, map, hours
fonts/          Self-hosted web fonts
css/style.css   All styles (colours at the top in :root)
js/main.js      Mobile menu, industry tabs, FAQ, contact form
images/         Logo set, icons, share image; images/work/ = project photos (JPG + WebP)
```

## Publish on GitHub Pages
1. Create a new public repository on github.com, e.g. `engiclinics-website`.
2. Click **Add file → Upload files**, drag in everything in this folder (keep the folders), and click **Commit changes**.
3. Go to **Settings → Pages**. Under *Build and deployment*, choose **Deploy from a branch**, branch **main**, folder **/ (root)**, and click **Save**.
4. After a minute the site is live at `https://YOUR-USERNAME.github.io/engiclinics-website/`.

### Use your own domain (optional)
In **Settings → Pages → Custom domain**, enter e.g. `www.engiclinics.com`, then at your domain registrar add a CNAME record pointing `www` to `YOUR-USERNAME.github.io`. Tick **Enforce HTTPS** once it appears.

## Make the contact form send emails
GitHub Pages cannot process forms by itself. Until you set this up, the form opens the visitor's email app with the enquiry filled in.
1. Create a free form at https://formspree.io and copy its endpoint (looks like `https://formspree.io/f/abcdwxyz`).
2. Open `js/main.js` and paste it into `formEndpoint` at the top. Set `email` to your real address too.

## Things to fill in
Search the HTML files for `[` to find placeholders: email address, project names, client quotes, team names, working hours and photos.
To add a photo, put it in `images/` and replace a `<div class="placeholder ...">[...]</div>` with `<img src="images/your-photo.jpg" alt="Describe the photo">`.
The email `info@engiclinics.com` is a placeholder used across all pages; find and replace it with your real address.

## Before you launch
- Replace `YOUR-DOMAIN` in `robots.txt` and `sitemap.xml` with your real domain.
- `404.html` is used automatically by GitHub Pages for broken links.
- All artwork is vector (SVG) so it stays sharp on every screen. When you add your own project photos, export them at least 2400 px wide as `.jpg` or `.webp`.

## Fonts
All fonts are self-hosted in `fonts/` (no Google Fonts request, faster and privacy-friendly) and free under the SIL Open Font License (`fonts/OFL-LICENSE.txt`):
Geist (headings), Inter (body text), Instrument Serif Italic (accent words), Geist Mono (technical labels and drawing annotations), Cinzel (logo wordmark).

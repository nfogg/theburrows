# The Burrows of Penrose — website

A fast, static website for the rural homestead, ready to host free on **GitHub Pages**
with your own custom domain. No build step, no frameworks — just HTML, one CSS file
and a tiny bit of JavaScript.

---

## What's in here

```
index.html            Home
about.html            The Homestead (story, the land, fast facts)
gallery.html          Photo gallery
area.html             The Area — links to the four local guides
book.html             Stay & Book (sends guests to your Airbnb listing)
404.html              Friendly "page not found"

guides/
  events.html         Southern Highlands events calendar
  food-and-drink.html Wineries, restaurants & pubs
  nature.html         Lookouts, walks & natural attractions
  wildlife.html       Wildlife around the homestead

css/site.css          All styling for the main pages + shared nav/footer
js/site.js            Mobile menu + gentle scroll animations
images/               Placeholder photos — replace with your own (same names)

CNAME                 Your custom domain (edit this!)
.nojekyll             Tells GitHub Pages to serve files as-is
robots.txt, sitemap.xml   Basic SEO (update the domain inside them)
```

---

## 1. Put it on GitHub Pages

1. Create a new repository on GitHub (e.g. `theburrows-site`).
2. Upload **everything in this folder** to the repository
   (drag-and-drop in the GitHub web UI is fine, or use `git`).
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source: Deploy from a branch**,
   choose the `main` branch and the `/ (root)` folder, then **Save**.
5. Wait a minute or two — your site goes live.

## 2. Connect your custom domain

1. Edit the **`CNAME`** file so it contains *only* your domain, e.g.
   `theburrowsofpenrose.com.au`
2. At your domain registrar, point the domain at GitHub Pages:
   - For a root domain, add **A records** to GitHub's IPs:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - For `www`, add a **CNAME record** pointing to `YOURUSERNAME.github.io`
3. Back in **Settings → Pages**, enter your domain and tick **Enforce HTTPS**
   (it may take a little while for the certificate to issue).
4. Update the domain inside `robots.txt` and `sitemap.xml` to match.

---

## 3. The two things to change first

**a) Your Airbnb link.** Every "Book on Airbnb" button currently points to
`https://www.airbnb.com.au/` as a placeholder. Find and replace that with your
real listing URL across all files. On Mac/Linux you can do it in one go from the
folder:

```bash
grep -rl "https://www.airbnb.com.au/" . | xargs sed -i '' \
  's#https://www.airbnb.com.au/#YOUR_AIRBNB_LISTING_URL#g'
```

(Search for `EDIT:` comments in the HTML — they mark every spot worth your attention.)

**b) Your photos.** The `images/` folder contains tasteful placeholders. To use
your own pictures, simply **replace each file with your photo of the same name**
(keep the `.jpg` extension). Suggested shots are written on each placeholder, e.g.
`hero.jpg`, `feature-kitchen.jpg`, `gallery-01.jpg` … For best results:
- `hero.jpg` — a wide, beautiful landscape shot (used full-screen)
- Keep images reasonably sized (1500–2400px wide is plenty) so pages stay fast.

---

## 4. Editing the words

All copy is plain text inside the HTML. Look for `<!-- EDIT: ... -->` comments —
these flag the draft passages and the placeholder facts (bedroom/bathroom counts,
check-in times, pet policy, etc.) that you'll want to confirm and personalise.

The four area guides contain dates and local details gathered for 2026; it's worth
a quick check against the organisers' own pages before each season, as event dates
and venue details can change.

---

## Notes

- Everything uses **relative links**, so you can also just open `index.html` in a
  browser to preview locally before publishing.
- Fonts load from Google Fonts; an internet connection shows them at their best.
- Designed to be responsive (phones to desktops) and keyboard-accessible.

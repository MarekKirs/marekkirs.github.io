# Lab Website (Jekyll + GitHub Pages)

A simple, fast, no-framework-lock-in academic lab website template.

## What's in here

```
_config.yml           site-wide settings (lab name, nav, footer links)
_data/people.yml       lab members shown on the Team page
_data/publications.yml papers shown on the Publications page
_data/news.yml          items shown on Home and the News page
_layouts/default.html   the page shell (header + footer wrap every page)
_includes/header.html   top navigation
_includes/footer.html   footer
assets/css/style.css    all styling — no external CSS framework needed
index.md, research.md, team.md, publications.md, news.md, join.md, contact.md
                         the actual pages (edit these in plain Markdown)
```

## 1. Quick content edits (no coding needed)

- **Lab name, tagline, nav links, footer:** edit `_config.yml`
- **Add/remove people:** edit `_data/people.yml`
- **Add papers:** edit `_data/publications.yml`
- **Add news items:** edit `_data/news.yml`
- **Page text:** edit the `.md` files directly — they're just Markdown

## 2. Deploy to GitHub Pages

1. Create a new GitHub repo.
   - For a personal/org site (served at `https://<username>.github.io/`), name
     the repo exactly `<username>.github.io`.
   - For a project site (served at `https://<username>.github.io/<repo>/`),
     name it anything, but then set `baseurl: "/<repo-name>"` in `_config.yml`.
2. Push all these files to the repo's `main` branch:
   ```bash
   git init
   git add .
   git commit -m "Initial lab website"
   git branch -M main
   git remote add origin https://github.com/<username>/<repo>.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment," set Source to **Deploy from a branch**,
   branch `main`, folder `/ (root)`. Save.
5. Wait 1-2 minutes, then your site will be live at the URL GitHub shows you.

## 3. Preview locally before pushing (optional but recommended)

Requires Ruby installed.

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000` in your browser. Changes to files
auto-rebuild while `jekyll serve` is running.

## 4. Adding photos

Put headshots in `assets/images/people/` and reference them in
`_data/people.yml`, e.g. `photo: "/assets/images/people/jane-smith.jpg"`.
Leave `photo: ""` to show a placeholder box instead.

## 5. Custom domain (optional)

If your university will point a subdomain at your site:

1. Add a file named `CNAME` (no extension) to the repo root containing just
   your domain, e.g. `smithlab.university.edu`
2. In Settings → Pages, enter the same domain under "Custom domain"
3. Ask your IT department to add a `CNAME` DNS record pointing your
   subdomain at `<username>.github.io`

## Colors / branding

The whole visual theme lives in `assets/css/style.css` — the `:root`
block at the top defines the accent color, fonts, and page width, so you
can reskin the entire site by changing a handful of CSS variables.

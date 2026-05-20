# Academic Website

A minimal, fast, indexable academic website built with Jekyll for GitHub Pages.

## Quick start

### 1. Create the repo

For a user site (recommended — gives you `https://YOURUSERNAME.github.io`):

```bash
# Replace YOURUSERNAME with your actual GitHub username
gh repo create YOURUSERNAME.github.io --public
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin git@github.com:YOURUSERNAME/YOURUSERNAME.github.io.git
git push -u origin main
```

GitHub Pages will build and deploy automatically. The site is live within
a few minutes at `https://YOURUSERNAME.github.io`.

### 2. Edit your personal info

Open `_config.yml` and replace:
- `YOURUSERNAME` in the `url` field
- `Amina [Last Name]` with your full name
- `your.email@university.edu`
- The Scholar / GitHub / SSRN / LinkedIn URLs (delete the lines for any you don't have yet — empty values render as nothing)
- `[Your University]` in `affiliation`

### 3. Replace the content

- `index.html` — bio, advisor, JMP teaser
- `research/index.html` — papers
- `teaching/index.html` — courses
- `assets/files/cv.pdf` — drop your CV PDF here
- `assets/files/portrait.jpg` — drop a square headshot here (will be hidden gracefully if missing)

### 4. Local preview (optional)

```bash
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```

## Getting indexed by Google Scholar

This is what you actually came for. A few things matter:

1. **Time.** Scholar's crawler finds personal sites slowly — typically 4–8 weeks after launch and after links from other indexed pages point at you. Build the site now even if it's sparse.

2. **Link from indexed sources.** The biggest signal is having your URL on:
   - Your department's faculty/grad student page (ask the admin to add you)
   - Your Google Scholar profile (`Profile → Edit → Homepage`)
   - Your SSRN / NBER / RePEc author page
   - Coauthors' websites
   - Conference programs

3. **Host your papers as PDFs at stable URLs** under your own domain
   (e.g. `/assets/files/jmp.pdf`) and link to them with the title text.
   Scholar's crawler picks these up.

4. **Use proper citation metadata.** The `<meta name="citation_*">` tags
   that academic Jekyll themes use help — for the JMP, when the PDF is
   ready, consider creating a dedicated page with full `citation_title`,
   `citation_author`, `citation_pdf_url` meta tags. Easy to add later.

5. **Submit your sitemap to Google Search Console** once you go live. The
   `jekyll-sitemap` plugin generates `/sitemap.xml` automatically.

## Customization

- **Color accent.** Edit `--accent` in `assets/css/main.css`. The current
  brick red (`#8b2a1f`) is restrained. Navy (`#1a3a5c`), forest
  (`#2d4a2b`), or charcoal (`#2a2a2a` — for an all-greyscale look) all
  work.
- **Font.** Crimson Pro is the default. To swap, change the `@import` line
  in `_layouts/default.html` and the `--serif` variable in the CSS.
- **Adding a paper.** Copy a `<div class="paper">...</div>` block in
  `research/index.html`. Use `class="paper jmp"` to highlight one as the
  job market paper.

## Custom domain (optional)

If you want `yourname.com` instead of `yourname.github.io`:

1. Buy the domain (Namecheap, Cloudflare, ~$10/yr).
2. Create a file named `CNAME` in the repo root containing just `yourname.com`.
3. Point a CNAME DNS record at `YOURUSERNAME.github.io`.
4. Update `url` in `_config.yml`.

## License

Site content: yours. Template code: do what you like.

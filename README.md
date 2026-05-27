# TVI Resources — Jekyll + Minimal Mistakes starter

This repository is a ready-to-fork Jekyll site using the Minimal Mistakes theme. It’s configured to build on GitHub Pages and includes a sensible structure for posts, pages, navigation, search, and comments.

Use this README to:
- Preview the site locally
- Build it for production
- Publish to GitHub Pages
- Fork and adapt it for your own site

---

## Quick start

From the repository root:

```bash
# Install dependencies (once)
bundle config set path vendor/bundle
bundle install

# Run local preview with live reload
JEKYLL_ENV=development bundle exec jekyll serve --livereload

# Or a production-like preview
JEKYLL_ENV=production bundle exec jekyll serve --livereload
```

Visit http://localhost:4000 while the server is running.

Push to the main branch to publish:
```bash
git add -A
git commit -m "Update site content"
git push origin main
```

GitHub Pages will automatically build and publish to your site URL.

---

## Prerequisites

- Ruby and build tools installed locally
  - Ubuntu/Debian: `sudo apt-get install -y ruby-full build-essential zlib1g-dev`
  - Fedora: `sudo dnf install -y ruby ruby-devel @development-tools redhat-rpm-config`
  - Arch: `sudo pacman -S ruby base-devel`
  - Windows: Use Ruby+DevKit from RubyInstaller or WSL
- Bundler: `gem install bundler` (if not already installed)
- Git

This repo uses the `github-pages` gem to pin Jekyll and plugin versions to match GitHub Pages, minimizing “works locally but not on GitHub” issues.

---

## Local development

Install dependencies (first time or when Gemfile changes):
```
bundle config set path vendor/bundle
bundle install
```

Serve locally (live reload):
```
JEKYLL_ENV=development bundle exec jekyll serve --livereload
# http://localhost:4000
```

Useful flags:
- Include future-dated posts: add `--future`
- Include drafts (in `_drafts`): add `--drafts`
- Faster rebuilds: add `--incremental`

Examples:
```
bundle exec jekyll serve --livereload --incremental
bundle exec jekyll serve --livereload --future --drafts
```

Notes:
- Changes to `_config.yml` require restarting the server.
- With `future: false` in `_config.yml`, posts dated in the future won’t appear on GitHub Pages until their date arrives. `--future` affects local preview only.

---

## Build for production (optional)

You do not need to commit `_site` (it’s ignored). If you want a production build locally:

```
JEKYLL_ENV=production bundle exec jekyll build
# Output: ./_site
```

---

## Publish to GitHub Pages

This repo is set up as a user/organization site (repo name ends with `<user>.github.io`). GitHub Pages will:
- Build from the `main` branch automatically
- Publish at `https://<user>.github.io`

Steps:
1. Commit and push to `main`:
   ```
   git add -A
   git commit -m "Update site content"
   git push origin main
   ```
2. On GitHub, go to Settings > Pages:
   - Source: “Deploy from a branch”
   - Branch: `main`, folder: `/`
3. Wait 1–3 minutes for the build to complete; then visit your URL.

Optional: Set a custom domain in Settings > Pages (and update DNS). If using a custom domain, update `_config.yml` `url:` to your domain (no trailing slash) and ensure `CNAME` exists.

---

## Fork this repository to create your own site

You have two main options:

### Option A: User/Organization site (recommended)
- Fork this repo
- Rename your fork to `<your-username>.github.io`
- GitHub Pages will publish at `https://<your-username>.github.io`
- Update `_config.yml`:
  - `title`, `description`
  - `url: https://<your-username>.github.io` (no trailing slash)
  - `repository: <your-username>/<your-username>.github.io`
  - Author profile and links
- Push to `main` and enable Pages as above

### Option B: Project site
- Fork this repo and keep any repository name (e.g., `my-blog`)
- Your site will publish at `https://<your-username>.github.io/<repo-name>/`
- Update `_config.yml`:
  - `url: https://<your-username>.github.io`
  - `baseurl: /<repo-name>` (add this key)
  - `repository: <your-username>/<repo-name>`
- Update your navigation and internal links to include `{{ site.baseurl }}` where appropriate
- Enable Pages as above

---

## What to customize

Edit `_config.yml`:
- Site identity: `title`, `description`, `url`, `baseurl` (if project site), `timezone`
- Repository link: `repository: <user>/<repo>`
- Theme skin: `minimal_mistakes_skin: "air"` (change if desired)
- Pagination: `paginate:`, `paginate_path:`
- Author info:
  ```
  author:
    name: "Your Name"
    avatar: "/assets/images/bio-photo.jpg"
    bio: "Your bio"
    email: "you@example.com"
    links:
      - label: "Website"
        icon: "fas fa-fw fa-link"
        url: "https://example.com"
      - label: "GitHub"
        icon: "fab fa-fw fa-github"
        url: "https://github.com/<your-username>"
  ```
- Social links in the footer
- Comments:
  - This repo is configured for Staticman (self-hosted comments). If you fork, either:
    - Disable comments by setting `comments.enabled: false` or removing the `comments:` block, or
    - Set up your own Staticman endpoint and update the `comments.staticman` settings accordingly

Navigation: `_data/navigation.yml`
- Adjust menu items, labels, and URLs
- Prefer `{{ site.baseurl }}`-aware paths for project sites

Pages: `_pages/*`
- Update About, Tags, Categories, Archives
- Each page uses Minimal Mistakes layouts and front matter

Posts: `_posts/*`
- Create posts named `YYYY-MM-DD-your-title.md` with front matter like:
  ```
  ---
  title: "My Post Title"
  categories: [category]
  tags: [tag1, tag2]
  layout: single
  author_profile: true
  ---

  Your content...
  ```
Assets: `assets/images/*`
- Store images and reference them with absolute paths (e.g., `/assets/images/...`) so they work with or without `baseurl`

---

## Minimal Mistakes theme

This site uses Minimal Mistakes via:
- `remote_theme: mmistakes/minimal-mistakes` in `_config.yml`
- Plugins and configuration compatible with GitHub Pages (`github-pages` gem)

Docs: https://mmistakes.github.io/minimal-mistakes/

---

## Troubleshooting

- Missing `webrick` (Ruby 3+):
  ```
  bundle add webrick
  ```
- Clean caches:
  ```
  bundle exec jekyll clean
  ```
- Doctor (find common issues):
  ```
  bundle exec jekyll doctor
  ```
- `_config.yml` changes not reflected:
  - Stop and restart `jekyll serve`
- Plugin differences locally vs GitHub Pages:
  - Using the `github-pages` gem helps match versions and allowed plugins. Avoid adding unsupported plugins unless you plan to build the site yourself and publish static output.
- Future-dated posts not showing on GitHub:
  - GitHub Pages respects `future: false`. Locally you can add `--future` to preview, but they won’t publish until the date arrives.
- Timezone:
  - Set `timezone:` in `_config.yml` to ensure dates behave as expected.

---

## Common tasks (copy/paste)

Install or update deps:
```
bundle install
```

Serve locally (dev):
```
bundle exec jekyll serve --livereload --incremental
```

Serve locally including drafts and future posts:
```
bundle exec jekyll serve --livereload --drafts --future
```

Production build:
```
JEKYLL_ENV=production bundle exec jekyll build
```

Publish (GitHub builds on push):
```
git add -A && git commit -m "Update site content" && git push origin main
```

---

## Project structure (high level)

```
_config.yml                 # Site-wide configuration
_data/navigation.yml        # Top navigation
_pages/                     # Standalone pages (About, Archives, etc.)
_posts/                     # Blog posts (YYYY-MM-DD-title.md)
_assets/ or assets/         # Theme assets; site images live in assets/images/
_includes/                  # Reusable partials
```

---

## License and attribution

- Theme: Minimal Mistakes by Michael Rose — https://github.com/mmistakes/minimal-mistakes
- Content: Yours. Ensure you have rights to publish any material you add.
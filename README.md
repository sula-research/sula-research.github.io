# Sula Research

Website for Sula Research, an independent quantitative research and trading operation based in Sydney.
Live at https://sula-research.github.io

The site is built with Jekyll on GitHub Pages, using the [Moon](https://github.com/TolgaTatli/Moonrise/) theme by Taylan Tatli (MIT licence).

## Changes from the stock Moon theme

**Content and branding**
- `_config.yml`: site title is "Sula Research", with our own bio line ("Quantitative Research | Financial Machine Learning") and description. `url` is `https://sula-research.github.io`.
- Logo: the Moon crescent is replaced by our bird-diving-into-water logo (`assets/img/logo.png`, a transparent PNG cut out of `bird logo 02a.jpg`). It is shown in full at 170 px wide instead of being cropped to a circle.
- Background: a crop of a blue-footed booby photo (`assets/img/placeholder-big.jpg`, source: Diego F. Parra on Pexels), centred so the feet sit below the main box.
- "Posts" is renamed **Public Research**: the button on the home page, the page title, and the (currently hidden) menu entries. The address is still `/posts/`.
- Facebook, Instagram and Steam are removed from the social icons (their lines are deleted from `_config.yml`). Twitter and GitHub are still there as placeholders (see "Still to do").

**Look and feel** (all in `_sass/site.scss`)
- The home box is black with white text and a thin grey border, matching the buttons inside it.
- The About, Public Research and Projects pages use the same black box, grey border and white text. Post and project cards inside them match too.
- The site name is shown in capitals to the right of the logo, vertically centred on it (`.brand` in `_sass/site.scss`, markup in `_layouts/home.html`). The 8 px nudge there is tuned to the current logo, so re-check it if the logo or its size changes.
- The home box sits near the top of the page (`padding-top: 11.5vh` on `.header.flex`) instead of vertically centred.

**Configuration**
- `gems:` in `_config.yml` is now `plugins:`. This is the key current Jekyll and GitHub Pages expect.
- `disable_links: true` is new (see below).

## Links are temporarily disabled

Every link on the site is switched off until the real content is written. This covers the About, Public Research and Projects buttons, the social icons, the logo and title links, and any links inside pages and posts. The hamburger menu is hidden because it contains only links.

How it works (`disable_links` in `_config.yml`):
- `_includes/head.html` adds CSS that blocks clicks on links and hides the menu.
- `_includes/scripts.html` removes the `href` from every link, so they cannot be followed by keyboard either.

**To turn links back on**, set `disable_links: false` in `_config.yml` (or delete the line) and push.

The About, Public Research and Projects pages still exist at `/about/`, `/posts/` and `/projects/` if someone types the address in directly, and they still hold Moon's sample content.

## Adding content

**About page**: edit `about/index.md`. Replace everything under the `---` front matter block at the top with your own text (Markdown). Keep the front matter, and change `title:` if you want a different heading.

**Public Research**: each item is a Markdown file in `_posts/`, named `YYYY-MM-DD-short-title.md`. For example `_posts/2026-11-01-first-paper.md`:

```markdown
---
layout: post
title: "Title of the piece"
date: 2026-11-01
excerpt: "One or two sentences shown on the list page."
tag:
- research
comments: false
---

The body goes here, in Markdown.
```

It appears on the Public Research page automatically, newest first.

**Projects**: the same, but add `project: true` to the front matter. Posts with `project: true` show up under Projects instead of Public Research.

**Removing the sample content**: delete the Moon sample files in `_posts/` (the ones dated 2012 to 2016). The old `moon-theme` post is the sample project.

To see your changes before pushing, preview locally (below). After pushing, GitHub Pages rebuilds in about a minute.

## Still to do

- Replace the sample content in `about/` and `_posts/` with real content (see "Adding content").
- Replace the placeholder social usernames in `_config.yml` (`twitter`, `github-url`) with real accounts, and remove any we do not use.
- Set `disqus_shortname` to our own Disqus account, or remove comments. It currently points at the theme author's.
- Fix the typos in the `description` in `_config.yml` ("Independant", "operaton").
- Add a contact email (`email:` in `_config.yml`).

## Previewing locally

1. Install Ruby with the DevKit (on Windows: `winget install RubyInstallerTeam.RubyWithDevKit.3.4`).
2. `gem install jekyll webrick tzinfo tzinfo-data jekyll-feed jekyll-sitemap jekyll-gist jekyll-mentions`
3. In this folder run `jekyll serve`, then open http://localhost:4000

The `Gemfile` pins an old Jekyll (3.2), so run Jekyll directly as above (set `JEKYLL_NO_BUNDLER_REQUIRE=1` if Bundler complains) rather than with `bundle exec`. GitHub Pages ignores the `Gemfile` and builds with its own versions.

Other Jekyll templates we looked at (Frisco, MVM, Grayscale, Jekyll for Everyone, Spectral) are not in this repo. The Frisco version with a landing-only mode is kept on a local branch, `frisco-landing-backup`.

## About the Moon theme

[Moon](https://tolgatatli.github.io/Moon) is a minimal, one column Jekyll theme. Its features include:

- Responsive layout
- Disqus integration
- Syntax highlighting
- Optional post image
- Social icons
- Page for sharing projects
- Optional background image
- Simple navigation menu
- MathJax support

Theme setup guide: https://tolgatatli.github.io/Moon/moon-theme/

The theme has moved to a new repository, [Moonrise](https://github.com/TolgaTatli/Moonrise/).

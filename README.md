# Sula Research

Website for Sula Research, an independent quantitative research and trading operation based in Sydney.
Live at https://sula-research.github.io

The site is built with Jekyll on GitHub Pages, using the [Moon](https://github.com/TolgaTatli/Moonrise/) theme by Taylan Tatli (MIT licence).

## Changes from the stock Moon theme

**Content and branding**
- `_config.yml`: site title is "Sula Research", with our own bio line and description. `url` is `https://sula-research.github.io`.
- Logo: the Moon crescent is replaced by the pixel-art bird (`assets/img/logo.png`, a transparent PNG cut out of `bird logo01.jpg`).
- Background: a crop of a blue-footed booby photo (`assets/img/placeholder-big.jpg`, source: Diego F. Parra on Pexels), centred so the feet sit below the main box.

**Look and feel** (all in `_sass/site.scss`)
- The home box is black with white text and a thin grey border, matching the buttons inside it.
- The About, Posts and Projects pages use the same black box, grey border and white text. Post and project cards inside them match too.
- The home box sits near the top of the page (`padding-top: 11.5vh` on `.header.flex`) instead of vertically centred.
- The logo is shown in full instead of being cropped to a circle.

**Configuration**
- `gems:` in `_config.yml` is now `plugins:`. This is the key current Jekyll and GitHub Pages expect.
- `disable_links: true` is new (see below).

## Links are temporarily disabled

Every link on the site is switched off until the real content is written. This covers the About, Posts and Projects buttons, the social icons, the logo and title links, and any links inside pages and posts. The hamburger menu is hidden because it contains only links.

How it works (`disable_links` in `_config.yml`):
- `_includes/head.html` adds CSS that blocks clicks on links and hides the menu.
- `_includes/scripts.html` removes the `href` from every link, so they cannot be followed by keyboard either.

**To turn links back on**, set `disable_links: false` in `_config.yml` (or delete the line) and push.

The About, Posts and Projects pages still exist at `/about/`, `/posts/` and `/projects/` if someone types the address in directly, and they still hold Moon's sample content.

## Still to do

- Replace the sample content in `about/`, `posts/`, `projects/` and `_posts/` with real content.
- Replace the placeholder social usernames in `_config.yml` (`twitter`, `facebook`, `github-url`, `instagram`, `steam`) with real accounts, and remove the ones we do not use.
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

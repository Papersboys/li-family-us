# The Li Family Website

> **Live site:** [li-family.us](https://li-family.us)

A modern, responsive family website built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) to share our family stories, milestones, and stay connected. Featuring a glassmorphic purple-gradient design, dark mode, SEO optimization, and a suite of family web apps.

---

## Family Members

### Parents
- **Yuanxi Li** — Staff Software Engineer @ Apple
- **Jingya Zhang** — Backend Software Engineer @ Amazon

### Children
- **Jasper Li** — Student at Eton School
- **Yris Li** — Student at KLA Schools of Bellevue

---

## Family Apps Ecosystem

| App | URL | Description |
|-----|-----|-------------|
| **yHome** | [home.li-family.us](https://home.li-family.us) | Family app hub — central navigation to all apps |
| **yStocker** | [stock.li-family.us](https://stock.li-family.us) | Stock research dashboard with AI-powered market insights |
| **yPlanner** | [planner.li-family.us](https://planner.li-family.us) | Trip planning with Google Maps integration |
| **yPlanter** | [planter.li-family.us](https://planter.li-family.us) | Seattle garden guide for USDA Zone 8b |
| **yTracker** | [tracker.li-family.us](https://tracker.li-family.us) | Family goal & habit tracker |

---

## Features

- **Glassmorphic Design** — Purple gradient theme with frosted-glass cards, dark mode toggle
- **Family Profiles** — Detailed pages for each family member with career highlights, interests, and milestones
- **Blog** — Family updates, stories, and news with author attribution
- **Foundation** — Li Family Foundation page with donation support and initiative tracking
- **Calendar** — Embedded Google Calendar for shared family events
- **Comments** — Giscus-powered discussion on every page (backed by GitHub Discussions)
- **Image Galleries** — GLightbox integration for photo lightboxes
- **SEO Optimized** — Open Graph, Twitter Cards, JSON-LD structured data, and PWA manifest
- **Responsive** — Mobile-friendly on all devices
- **Auto-Deploy** — Push to `main` and GitHub Actions deploys to GitHub Pages

---

## Quick Start

### Prerequisites
- Python 3.x
- pip

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/Papersboys/li-family-us.git
   cd li-family-us
   ```

2. **Install dependencies**
   ```bash
   pip install mkdocs-material mkdocs-glightbox
   ```

3. **Run local server**
   ```bash
   mkdocs serve
   ```

4. **Open in browser**
   Visit [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## Project Structure

```
li-family-us/
├── docs/
│   ├── index.md                 # Homepage
│   ├── about-yuanxi.md          # Yuanxi's profile
│   ├── about-jingya.md          # Jingya's profile
│   ├── about-jasper.md          # Jasper's profile
│   ├── about-yris.md            # Yris's profile
│   ├── contact.md               # Contact page
│   ├── foundation.md            # Li Family Foundation
│   ├── calendar.md              # Embedded Google Calendar
│   ├── blog/
│   │   ├── index.md             # Blog landing page
│   │   ├── .authors.yml         # Blog author definitions
│   │   └── posts/               # Blog posts (markdown)
│   ├── stylesheets/
│   │   └── extra.css            # Custom glassmorphic styling
│   ├── images/                  # Favicons and image assets
│   ├── manifest.json            # PWA web app manifest
│   └── CNAME                    # Custom domain config
├── overrides/
│   ├── main.html                # SEO meta tags & structured data
│   └── partials/
│       ├── comments.html        # Giscus comments widget
│       ├── footer.html          # Custom footer with social links
│       └── head.html            # Additional head meta tags
├── .github/
│   └── workflows/
│       └── ci.yml               # GitHub Actions auto-deploy
├── mkdocs.yml                   # MkDocs configuration
├── GISCUS_SETUP.md              # Giscus comment system setup guide
├── package.json                 # Node dependencies (sharp)
└── README.md                    # This file
```

---

## Tech Stack

- **[MkDocs](https://www.mkdocs.org/)** — Static site generator
- **[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)** — Theme with tabs, search, dark mode
- **[GLightbox](https://github.com/biati-digital/glightbox)** — Image lightbox plugin
- **[Giscus](https://giscus.app/)** — GitHub Discussions-powered comments
- **GitHub Actions** — CI/CD auto-deployment
- **GitHub Pages** — Hosting with custom domain

---

## Customization

### Update Content
Edit the markdown files in `docs/`:
- `index.md` — Homepage content and Family Apps
- `about-*.md` — Family member profiles
- `foundation.md` — Foundation initiatives and donations
- `calendar.md` — Calendar embed configuration
- `contact.md` — Contact information
- `blog/posts/` — Add new blog posts

### Change Colors
Edit `docs/stylesheets/extra.css` to customize:
- Background gradients
- Header and tab bar colors
- Button styles and card appearances
- Dark mode palette

### Update Configuration
Edit `mkdocs.yml` to change:
- Site name, description, and author
- Navigation structure
- Theme colors and features
- Plugins and extensions
- Social links in footer

---

## Deployment

The site auto-deploys to GitHub Pages on every push to `main`.

### Manual Deployment
```bash
mkdocs gh-deploy
```

### Custom Domain
1. The `CNAME` file in `docs/` is set to `li-family.us`
2. DNS is configured at the domain provider
3. GitHub Pages custom domain is enabled in repo settings

---

## Contact

- **Admin**: [admin@li-family.us](mailto:admin@li-family.us)
- **Yuanxi Li**: [yuanxi.li@li-family.us](mailto:yuanxi.li@li-family.us)
- **Jingya Zhang**: [jingya.zhang@li-family.us](mailto:jingya.zhang@li-family.us)

**Location:** Greater Seattle Area, Washington

---

## Contributing

This is a private family website. Family members can contribute by:
1. Creating a branch for your changes
2. Making updates to content or adding photos
3. Submitting a pull request
4. Changes will be reviewed and merged

---

## License

This is a private family website. All rights reserved.

## Acknowledgments

- Built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/)
- Comments powered by [Giscus](https://giscus.app/)
- Icons by [Material Design Icons](https://materialdesignicons.com/)

---

Made with :heart: by the Li Family

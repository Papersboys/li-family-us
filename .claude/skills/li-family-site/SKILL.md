---
name: li-family-site
description: Manage the Li Family website (li-family.us) — an MkDocs Material site with blog, family profiles, foundation page, calendar, and custom CSS. Use this skill whenever the user wants to add a blog post, update a family member's profile, change site styling, serve locally, deploy, or make any content changes to the family website. Also use when the user mentions mkdocs, the family site, li-family.us, blog posts, family profiles, or site deployment in the context of this repo.
---

# Li Family Website Management

The Li Family website is an MkDocs Material site hosted at [li-family.us](https://li-family.us). It features family member profiles, a blog, a foundation page, an embedded Google Calendar, Giscus comments, and a glassmorphic purple-gradient design with dark mode support.

**Repo:** `/Users/yuanxili/workspace/li-family-us`
**Live site:** https://li-family.us
**GitHub:** https://github.com/Papersboys/li-family-us

---

## Project Structure

```
li-family-us/
├── docs/
│   ├── index.md                 # Homepage (hero, family cards, apps, values)
│   ├── about-yuanxi.md          # Yuanxi Li — Staff SWE @ Apple
│   ├── about-jingya.md          # Jingya Zhang — Backend SWE @ Amazon
│   ├── about-jasper.md          # Jasper Li — son, Eton School
│   ├── about-yris.md            # Yris Li — daughter, KLA Schools
│   ├── contact.md               # Contact page
│   ├── foundation.md            # Li Family Foundation (donations, initiatives)
│   ├── calendar.md              # Embedded Google Calendar
│   ├── blog/
│   │   ├── index.md             # Blog landing with category cards
│   │   ├── .authors.yml         # Blog authors (yuanxi, jingya, family)
│   │   └── posts/               # Blog posts (one .md per post)
│   ├── stylesheets/extra.css    # Custom glassmorphic CSS (357+ lines)
│   ├── images/                  # favicon.svg, favicon.png
│   ├── manifest.json            # PWA manifest
│   └── CNAME                    # Custom domain: li-family.us
├── overrides/
│   ├── main.html                # SEO: OG tags, Twitter Cards, JSON-LD, favicons
│   └── partials/
│       ├── comments.html        # Giscus comments (preferred_color_scheme theme)
│       ├── footer.html          # Footer with all social links
│       └── head.html            # (intentionally empty — tags in main.html)
├── mkdocs.yml                   # Site config, nav, plugins, extensions
├── .github/workflows/ci.yml     # Auto-deploy on push to main
└── README.md
```

---

## Common Tasks

### Serve Locally

```bash
cd /Users/yuanxili/workspace/li-family-us
pip install mkdocs-material mkdocs-glightbox  # first time only
mkdocs serve
```
Opens at http://127.0.0.1:8000. Hot-reloads on file changes.

### Deploy

The site auto-deploys via GitHub Actions on push to `main`. For manual deploy:
```bash
mkdocs gh-deploy --force
```

---

### Add a Blog Post

Create a new file at `docs/blog/posts/YYYY-MM-DD-slug.md` with this template:

```markdown
---
date: YYYY-MM-DD
authors:
  - family          # options: yuanxi, jingya, family
categories:
  - Updates         # pick from: Updates, Family News, Adventures, Career & Tech
---

# Post Title

![Hero image](https://images.unsplash.com/photo-XXXXX?w=1200&h=400&fit=crop)

Opening paragraph — keep it warm and personal.

<!-- more -->

## Section Heading

Body content here. Use Material for MkDocs features:
- Admonitions (`!!! tip`, `!!! quote`)
- Grid cards (`<div class="grid cards" markdown>`)
- Tabs (`=== "Tab Name"`)
- Icons (`:material-icon-name:`)

Closing line with family warmth. :heart:
```

**Available authors** (defined in `docs/blog/.authors.yml`):
- `yuanxi` — Yuanxi Li (Father)
- `jingya` — Jingya Zhang (Mother)
- `family` — The Li Family (general updates)

All avatars use ui-avatars.com with purple background (#673ab7).

---

### Update a Family Profile

Profile files follow a consistent pattern. Here's the structure:

| File | Person | Key details |
|------|--------|-------------|
| `docs/about-yuanxi.md` | Yuanxi Li | Staff SWE @ Apple, 10+ yrs, media management org |
| `docs/about-jingya.md` | Jingya Zhang | Backend SWE @ Amazon, 8+ yrs, delivery experience |
| `docs/about-jasper.md` | Jasper Li | Son, Eton School, loves painting |
| `docs/about-yris.md` | Yris Li | Daughter, KLA Schools of Bellevue, loves soccer |

**Parent profiles** contain: Summary, Current Role, Career Highlights (tabbed), Work Experience, Education, Skills grid cards, Interests, Connect links, Philosophy quote.

**Children profiles** contain: About, Vision (tabbed), Interests & Passions grid cards, What Makes Them Special, Learning & Development, Milestones, Photo Gallery, Parent's Message quote.

When updating profiles:
- Keep the existing section structure and admonition types
- Use Material icons (`:material-icon-name:{ .lg .middle }`) in card headers
- Wrap card sections in `<div class="grid cards" markdown>` ... `</div>`
- Use tabs with `=== "Tab Name"` inside `!!! success` admonitions

---

### Edit Site Styling

The custom CSS is in `docs/stylesheets/extra.css`. Key design tokens:

| Element | Light mode | Dark mode selector |
|---------|-----------|-------------------|
| Body background | `#e3f2fd → #f3e5f5 → #fce4ec` gradient | (same, Material handles) |
| Content cards | `rgba(255,255,255,0.96)` | `[data-md-color-scheme="slate"]` → `rgba(30,30,30,0.96)` |
| Header | Light gradient with `backdrop-filter: blur(10px)` | Dark gradient `rgba(20,20,30,0.95)` |
| Buttons (primary) | `#667eea → #764ba2` gradient | Same gradient |
| Active nav link | `rgba(102,126,234,0.15)` bg | Same |
| Accent color | `#667eea` (blue) / `#764ba2` (purple) | Same |

Every visual element has both light and dark mode rules. When adding new styles, always include the `[data-md-color-scheme="slate"]` variant.

---

### Update Navigation

Edit the `nav:` section in `mkdocs.yml`:

```yaml
nav:
  - Home: index.md
  - Members:
      - Parents:
          - Yuanxi Li: about-yuanxi.md
          - Jingya Zhang: about-jingya.md
      - Children:
          - Jasper Li: about-jasper.md
          - Yris Li: about-yris.md
  - Blog: blog/index.md
  - Foundation: foundation.md
  - Calendar: calendar.md
  - Stocks: https://stock.li-family.us    # external link
  - Contact Us: contact.md
```

External links (like Stocks) use full URLs. Internal pages reference the .md file path relative to `docs/`.

---

### Manage Giscus Comments

Comments are configured in `overrides/partials/comments.html` using Giscus (GitHub Discussions backend).

- **Repo:** Papersboys/li-family-us
- **Theme:** `preferred_color_scheme` (auto light/dark)
- **Mapping:** URL-based

To disable comments on a specific page, add to that page's frontmatter:
```yaml
---
comments: false
---
```

Comments are enabled globally via `extra.comments.enabled: true` in `mkdocs.yml`.

---

### Update Foundation Page

The foundation page (`docs/foundation.md`) tracks:
- Impact amount (currently $10,000+ since 2024)
- GoFundMe donation link
- Focus areas: Education, Innovation, Community, Youth Development
- Current initiatives: Eton School Foundation, local museum programs
- Board of Directors: Yuanxi (President), Jingya (Vice President)

When updating, keep the admonition-heavy structure (`!!! success`, `!!! tip`, `!!! info`).

---

### Family Apps Ecosystem

The homepage (`docs/index.md`) showcases four family apps:

| App | URL | Description |
|-----|-----|-------------|
| yHome | home.li-family.us | Central app hub |
| yStocker | stock.li-family.us | Stock research dashboard |
| yPlanner | planner.li-family.us | Trip planning with Google Maps |
| yPlanter | planter.li-family.us | Seattle garden guide (USDA Zone 8b) |

These are also listed in the README. When adding a new app, update both `docs/index.md` (Family Apps section) and `README.md` (Family Apps Ecosystem table).

---

## Key Configuration (mkdocs.yml)

- **Theme:** Material with deep purple primary, pink accent
- **Fonts:** Roboto / Roboto Mono
- **Plugins:** search, tags, blog (with authors), glightbox
- **Extensions:** emoji, admonition, superfences, tabbed, highlight, tasklist, tables, footnotes, critic, caret, keys, mark, tilde
- **Copyright:** 2024-2026 The Li Family Foundation
- **Social links:** admin email, 2x LinkedIn, 2x personal email

---

## Content Patterns

The site uses these Material for MkDocs patterns consistently:

- **Hero images:** Unsplash URLs with `?w=1200&h=400&fit=crop`, wrapped in centered div with border-radius and shadow
- **Grid cards:** `<div class="grid cards" markdown>` with `-   :material-icon:{ .lg .middle } **Title**` items
- **Tabbed content:** `=== "Tab Name"` inside admonition blocks
- **Admonitions:** `!!! info`, `!!! success`, `!!! tip`, `!!! quote`, `!!! note`
- **Buttons:** `[:material-icon: Label](url){ .md-button }` and `.md-button--primary`
- **Quotes:** `!!! quote ""` with italicized attributed quotes at page bottom
- **Navigation footers:** Back to Home + primary CTA button at bottom of pages

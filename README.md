# The Li Family Website

Welcome to the Li family website repository! This is a beautiful family website built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) to share our family stories, milestones, and stay connected.

## 🏠 About

A modern, responsive family website featuring:
- Family member profiles with detailed information
- Beautiful purple gradient design
- Contact information
- Photo galleries (coming soon)
- Mobile-friendly responsive design

## 👨‍👩‍👧‍👦 Family Members

### Parents
- **Yuanxi Li** - Staff Software Engineer @ Apple
- **Jingya Zhang** - Backend Software Engineer @ Amazon

### Children
- **Jasper Li** - Student at Eton School
- **Yris Li** - Student at KLA Schools of Bellevue

## 🚀 Quick Start

### Prerequisites
- Python 3.x
- pip

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/[your-username]/li-family-us.git
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
   Visit http://127.0.0.1:8000

## 📁 Project Structure

```
li-family-us/
├── docs/
│   ├── index.md              # Homepage
│   ├── about-yuanxi.md       # Yuanxi's profile
│   ├── about-jingya.md       # Jingya's profile
│   ├── about-jasper.md       # Jasper's profile
│   ├── about-yris.md         # Yris's profile
│   ├── contact.md            # Contact page
│   ├── stylesheets/
│   │   └── extra.css         # Custom styling
│   └── images/               # Image assets
├── mkdocs.yml                # MkDocs configuration
├── .github/
│   └── workflows/
│       └── ci.yml            # GitHub Actions deployment
└── README.md                 # This file
```

## 🎨 Features

- **Modern Design**: Beautiful purple gradient theme with glassmorphism effects
- **Responsive**: Mobile-friendly and works on all devices
- **Fast**: Static site generation for lightning-fast load times
- **SEO Friendly**: Optimized for search engines
- **Dark Mode**: Automatic light/dark mode toggle
- **Image Galleries**: GLightbox integration for beautiful photo displays
- **Easy Updates**: Simple markdown-based content management

## 🛠️ Tech Stack

- **[MkDocs](https://www.mkdocs.org/)** - Static site generator
- **[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)** - Beautiful theme
- **[GLightbox](https://github.com/biati-digital/glightbox)** - Image lightbox plugin
- **GitHub Actions** - Automated deployment
- **GitHub Pages** - Free hosting

## 📝 Customization

### Update Content
Edit the markdown files in the `docs/` folder:
- `index.md` - Homepage content
- `about-*.md` - Family member profiles
- `contact.md` - Contact information

### Change Colors
Edit `docs/stylesheets/extra.css` to customize:
- Background gradients
- Header colors
- Button styles
- Card appearances

### Update Configuration
Edit `mkdocs.yml` to change:
- Site name and description
- Navigation structure
- Theme colors
- Plugins and extensions

## 🚢 Deployment

The site automatically deploys to GitHub Pages when you push to the `main` branch.

### Manual Deployment
```bash
mkdocs gh-deploy
```

### Custom Domain
1. Add a `CNAME` file to `docs/` with your domain
2. Configure DNS settings at your domain provider
3. Enable custom domain in GitHub Pages settings

## 📧 Contact

- **Yuanxi Li**: [yuanxi.li@li-family.us](mailto:yuanxi.li@li-family.us)
- **Jingya Zhang**: [jingya.zhang@li-family.us](mailto:jingya.zhang@li-family.us)

## 📍 Location

Greater Seattle Area, Washington

## 🤝 Contributing

This is a private family website. Family members can contribute by:
1. Creating a branch for your changes
2. Making updates to content or adding photos
3. Submitting a pull request
4. Changes will be reviewed and merged

## 📄 License

This is a private family website. All rights reserved.

## 🙏 Acknowledgments

- Built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/)
- Inspired by modern family websites
- Icons by [Material Design Icons](https://materialdesignicons.com/)

---

Made with ❤️ by the Li Family
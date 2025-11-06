# Giscus Discussion Widget Setup Instructions

## Overview
Giscus has been configured to display a discussion widget on all pages of your website. It uses GitHub Discussions as the backend.

## Next Steps to Complete Setup

### 1. Enable GitHub Discussions
1. Go to your repository: https://github.com/Papersboys/li-family-us
2. Click on **Settings** tab
3. Scroll down to **Features** section
4. Check the box for **Discussions**

### 2. Get Your Giscus Configuration IDs
1. Visit https://giscus.app
2. Enter your repository: `Papersboys/li-family-us`
3. Select the following options:
   - **Page ↔️ Discussions Mapping**: pathname
   - **Discussion Category**: General (or create a new category specifically for comments)
   - **Features**: Enable reactions, Place comment box above comments
   - **Theme**: Preferred color scheme
4. Scroll down to see the generated script tag
5. Copy the following values from the generated script:
   - `data-repo-id`
   - `data-category-id`

### 3. Update the Configuration File
Edit `overrides/partials/comments.html` and replace:
- `YOUR_REPO_ID` with the actual repo ID from step 2
- `YOUR_CATEGORY_ID` with the actual category ID from step 2

### 4. Test the Setup
Run the site locally:
```bash
mkdocs serve
```

Visit any page and scroll to the bottom to see the discussion widget.

## How to Disable Comments on Specific Pages

If you want to disable comments on a specific page, add this to the top of the markdown file:

```yaml
---
comments: false
---
```

## Files Modified
- `mkdocs.yml` - Added custom_dir and comments configuration
- `overrides/partials/comments.html` - Created Giscus widget template

## Current Configuration
- **Repository**: Papersboys/li-family-us
- **Mapping**: pathname (each page gets its own discussion thread)
- **Enabled on**: All pages by default
- **Theme**: Adapts to light/dark mode automatically
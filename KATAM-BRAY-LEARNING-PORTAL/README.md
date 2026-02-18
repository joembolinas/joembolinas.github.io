# KATAM-BRAY Learning Portal

This directory contains the KATAM-BRAY Learning Portal, a dedicated section for organizing learning materials, courses, and resources.

## Structure

```
KATAM-BRAY-LEARNING-PORTAL/
├── index.html         # Main portal homepage
├── courses.html       # Course materials page
├── notes.html         # Study notes page
├── projects.html      # Projects page
├── resources.html     # Learning resources page
├── progress.html      # Progress tracking page
└── guides.html        # Tips and guides page
```

## Adding New Content

### Creating New Pages

1. Create a new HTML file in this directory (e.g., `new-topic.html`)
2. Use the existing pages as templates for consistent styling
3. Link to your new page from `index.html` or other relevant pages

### Creating Subdirectories

You can organize complex content in subdirectories:

```
KATAM-BRAY-LEARNING-PORTAL/
├── courses/
│   ├── course-1/
│   │   ├── index.html
│   │   ├── lesson-1.html
│   │   └── lesson-2.html
│   └── course-2/
│       └── index.html
└── projects/
    ├── project-1.html
    └── project-2.html
```

### Linking Pages

Use relative URLs to link between pages:
- Link to portal home: `index.html` or `./`
- Link to main site: `/` or `../`
- Link to other pages: `courses.html`, `notes.html`, etc.

## Customization

All pages use inline CSS for easy customization. The color scheme uses:
- Primary: `#11998e` (teal)
- Secondary: `#38ef7d` (green)
- Background gradient: `linear-gradient(135deg, #11998e 0%, #38ef7d 100%)`

Feel free to modify colors, layouts, and styles to match your preferences.

## GitHub Pages

This portal is part of the `joembolinas.github.io` GitHub Pages site. The portal is accessible at:
- Main site: `https://joembolinas.github.io/`
- Portal: `https://joembolinas.github.io/KATAM-BRAY-LEARNING-PORTAL/`

Changes pushed to the main branch will be automatically published.

---

*v1.0.0 | Active | Last Updated: Feb 18 2026*

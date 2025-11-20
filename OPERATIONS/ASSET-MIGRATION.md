# Asset Migration Instructions for HamsaWolf Website Build

## Document Purpose
This document provides clear instructions for Claude Code to organize and migrate assets from the Raw extraction folder to the production assets folder for the HamsaWolf Sales Engineering website.

---

## Current Asset Structure

### Available in Raw/assets/ (from Winning By Design extraction):
- **29 Icon SVGs** (`icon-0.svg` through `icon-25.svg`) - Professional UI icons
- **50 Images** (mix of PNG, SVG, JPG) - Various graphics and illustrations  
- **3 Favicon PNGs** - Extracted favicons (not needed, we have our own)
- **10 Font files** (.woff2) - Web font files (likely Open Sans or similar)
- **1 Video file** (video-0.mp4) - Single video file (assess for relevance)

### Already in Root assets/ (HamsaWolf's own assets):
- **HWLOGO.png** - HamsaWolf's main logo
- **favicon/** folder with complete favicon set:
  - android-chrome-192x192.png
  - android-chrome-512x512.png  
  - apple-touch-icon.png
  - favicon-16x16.png
  - favicon-32x32.png
  - favicon.ico
  - site.webmanifest

---

## Asset Migration Plan

### 1. Create Folder Structure in Root assets/
```
assets/
├── favicon/          [ALREADY EXISTS - DO NOT OVERWRITE]
├── images/
│   ├── icons/        [Copy selected SVG icons from Raw]
│   ├── hero/         [Background images for hero sections]
│   ├── patterns/     [Abstract patterns and backgrounds]
│   └── misc/         [Other images as needed]
├── fonts/            [Copy font files from Raw]
├── css/              [For generated stylesheets]
└── js/               [For JavaScript files]
```

### 2. Icons to Copy from Raw/assets/icons/
Copy these useful professional icons for the consulting site:
- **Navigation/UI Icons:**
  - Arrow icons (for CTAs and navigation)
  - Menu/hamburger icons
  - Close/X icons
  - Chevron icons (dropdowns)
  
- **Service/Feature Icons:**
  - Chart/analytics icons
  - Gear/settings icons
  - Target/goal icons
  - Lightbulb/strategy icons
  - People/team icons
  - Document/report icons
  - Check/success icons

**DO NOT COPY:** The favicon PNGs from Raw (we have our own)

### 3. Images to Evaluate and Copy from Raw/assets/images/
Review each image and copy only:
- **Abstract patterns** suitable for section backgrounds
- **Professional graphics** (charts, diagrams, abstract illustrations)
- **Hero background images** if suitable for a consulting firm
- **Geometric patterns** for visual interest

**DO NOT COPY:**
- Any logos or branding from Winning By Design
- Team photos or specific people
- Company-specific screenshots or demos
- Branded materials with WBD identity

### 4. Fonts to Copy from Raw/assets/fonts/
- Copy ALL .woff2 files to assets/fonts/
- These appear to be web-optimized font files
- Will be referenced in the CSS as needed

### 5. Logo Integration Instructions

#### Navigation Bar:
- Use **HWLOGO.png** in the navigation
- Recommended size: Height of 40-50px, width auto
- Location: Top left of navigation bar
- Alt text: "HamsaWolf Sales Engineering"

#### Footer:
- Optionally use HWLOGO.png in footer
- Can be slightly larger than nav version
- Or use text-only "HamsaWolf Sales Engineering"

#### Hero Section:
- Consider subtle watermark or background usage
- Keep focus on the value proposition text

### 6. Favicon Implementation

Add to the `<head>` of all HTML files:
```html
<!-- Favicon -->
<link rel="icon" type="image/x-icon" href="/assets/favicon/favicon.ico">
<link rel="icon" type="image/png" sizes="32x32" href="/assets/favicon/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="/assets/favicon/favicon-16x16.png">
<link rel="apple-touch-icon" sizes="180x180" href="/assets/favicon/apple-touch-icon.png">
<link rel="manifest" href="/assets/favicon/site.webmanifest">
<meta name="theme-color" content="#0066CC">
```

### 7. Color Scheme Recommendation

Based on professional consulting aesthetics similar to Winning By Design:
```css
:root {
  /* Primary Colors */
  --color-primary: #0066CC;        /* Professional blue */
  --color-primary-dark: #0052A3;   /* Darker blue for hover */
  --color-primary-light: #E6F2FF;  /* Light blue background */
  
  /* Secondary Colors */
  --color-teal: #00A19C;           /* Accent teal */
  --color-teal-light: #E6F7F7;     /* Light teal background */
  
  /* Neutral Colors */
  --color-dark: #1A1A1A;           /* Almost black for text */
  --color-gray-dark: #4A4A4A;      /* Dark gray */
  --color-gray: #7A7A7A;           /* Medium gray */
  --color-gray-light: #E5E5E5;     /* Light gray borders */
  --color-white: #FFFFFF;          /* White */
  --color-off-white: #F8F9FA;      /* Off-white backgrounds */
  
  /* Semantic Colors */
  --color-success: #00A651;        /* Green */
  --color-warning: #FDB913;        /* Yellow */
  --color-error: #D32F2F;          /* Red */
}
```

---

## Implementation Checklist for Claude Code

- [ ] Create folder structure in assets/
- [ ] Copy selected icon SVGs from Raw/assets/icons/ to assets/images/icons/
- [ ] Review and copy appropriate images from Raw/assets/images/
- [ ] Copy all font files from Raw/assets/fonts/ to assets/fonts/
- [ ] DO NOT overwrite existing favicon folder
- [ ] DO NOT copy any Winning By Design branded content
- [ ] Integrate HWLOGO.png into navigation and footer
- [ ] Add favicon links to HTML head
- [ ] Apply professional color scheme
- [ ] Update paths in CSS and HTML to reference new asset locations

---

## Notes

1. **Asset Selection Criteria:** Only copy generic, professional assets that suit a consulting firm. No branded content from the source site.

2. **Logo Usage:** HWLOGO.png should be prominent but not overwhelming. Professional and clean presentation.

3. **Performance:** Consider optimizing images before production deployment (this can be a future enhancement).

4. **Naming Convention:** When copying files, consider renaming them descriptively:
   - `icon-4.svg` → `arrow-right.svg`
   - `image-15.png` → `hero-pattern.png`

5. **CSS References:** Update the styles.css to properly reference the new asset locations.

---

**Document Version:** 1.0.0  
**Last Updated:** 2025-01-01  
**Status:** Ready for Claude Code implementation

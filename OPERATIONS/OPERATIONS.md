# OPERATIONS Manual for HamsaWolf Sales Engineering Website

## Document Purpose

This document serves as the **single source of truth** for building and maintaining the HamsaWolf Sales Engineering website. Claude Code or any AI agent should follow these instructions precisely to generate, update, or rebuild the website from raw assets and content files.

**CRITICAL**: This is not a guide for humans. This is a build specification for AI systems. Every instruction must be interpreted literally and executed programmatically.

---

## Repository Structure Overview

```
/
├── Raw/                    # Input: Raw HTML downloads from reference sites
├── Audit/                  # Intermediate: JSON audit files from XTRACTR
├── OPERATIONS/             # Instructions & Content Source of Truth
│   ├── OPERATIONS.md       # This file - master build instructions
│   ├── ASSET-MIGRATION.md  # Asset organization and migration guide
│   ├── copy-home.md        # Homepage content
│   ├── copy-services.md    # Services descriptions
│   ├── copy-case-study.md  # Case study content
│   ├── copy-about.md       # About section content
│   ├── copy-cta.md         # Call-to-action content
│   ├── copy-faq.md         # Frequently asked questions
│   ├── copy-privacy.md     # Privacy policy
│   ├── copy-terms.md       # Terms of service
│   └── pricing-packages.md # Pricing documentation
├── src/                    # Output: Generated website files
│   ├── index.html          # Main homepage
│   ├── privacy.html        # Privacy policy page
│   ├── terms.html          # Terms of service page
│   └── assets/             # CSS, JS, images
│       ├── styles.css      # Main stylesheet
│       └── js/             # JavaScript files
├── README.md               # Project overview
└── CHANGELOG.md            # Version history
```

---

## 1. Build Process Overview

### ⚠️ CRITICAL: Understanding the Raw Folder

**The Raw folder contains a REFERENCE SITE for DESIGN INSPIRATION ONLY.**

- **DO**: Extract colors, fonts, spacing, layout patterns, component structures
- **DO**: Study how professional sites structure their CSS and HTML
- **DO**: Use it as a visual style guide
- **DO NOT**: Copy any content, text, or data from Raw files
- **DO NOT**: Use Raw HTML as templates to modify
- **DO NOT**: Keep any references to the original site

**BUILD EVERYTHING FROM SCRATCH** using:
- Design tokens extracted from Raw (colors, fonts, spacing)
- Content from OPERATIONS/copy-*.md files
- Structure patterns learned from Raw but implemented fresh

### 1.1 Input Processing Pipeline

1. **Analyze Raw Folder** for design tokens ONLY:
   - Parse `Raw/styles.css` for colors, fonts, spacing values
   - Study `Raw/pages/*.html` for layout patterns (but ignore content)
   - Extract component structures (cards, heroes, CTAs)
2. **Migrate Assets**: Follow `OPERATIONS/ASSET-MIGRATION.md`:
   - Copy selected icons from Raw/assets/icons/
   - Copy appropriate images from Raw/assets/images/
   - Copy font files from Raw/assets/fonts/
   - Integrate HWLOGO.png and favicon setup
3. **Extract Design Tokens**: 
   - Colors from Raw/styles.css
   - Font families and sizes
   - Spacing units and patterns
   - **DO NOT extract any text content**
4. **Load Content**: Read all `OPERATIONS/copy-*.md` files
5. **Generate HTML**: Build fresh HTML using:
   - Structure patterns from Raw (as inspiration)
   - Content from OPERATIONS files
   - Design tokens extracted from Raw
   - HamsaWolf logo and assets
6. **Create Assets**: Generate new CSS file with extracted tokens
7. **Output to src/**: Write all generated files

### 1.2 Core Principles

- **Single Source of Truth**: All content comes from `OPERATIONS/copy-*.md` files
- **Token-Based Design**: Extract and standardize design tokens from audits
- **Component-First**: Build reusable HTML structures, not monolithic pages
- **Documentation-Driven**: This document defines all behavior

---

## 2. Interpreting Raw Files

### 2.1 Raw Folder Structure

The Raw folder contains an extracted reference website:

```
Raw/
├── styles.css           # Master CSS file with all design tokens
├── pages/               # HTML pages (for structure reference ONLY)
│   ├── index.html       # Study hero, nav, footer patterns
│   └── *.html           # Other pages for component patterns
└── assets/              # Fonts, images (use fonts, ignore images)
    └── fonts/           # Web fonts to reuse
```

### 2.2 Token Extraction Rules

#### From Raw/styles.css, extract:

**Colors**
- Search for color values (#hex, rgb, hsl)
- Identify primary brand colors
- Extract neutral/gray scale
- Note hover/active state colors
- **USE THESE EXACT COLORS** in the new build

**Typography**
- Font-family declarations (e.g., 'Open Sans')
- Font-size values and scale
- Font-weights used (300, 400, 600, 700)
- Line-height patterns
- **REUSE THE SAME FONTS**

**Spacing**
- Padding/margin patterns
- Common spacing units
- Container max-widths
- Grid gaps and layouts

#### From Raw/pages/*.html, study:

**Layout Patterns** (structure only, ignore content):
- How navigation is structured
- Hero section composition
- Card component markup
- Grid systems used
- Footer organization

**DO NOT COPY**:
- Any text content
- Company names or branding
- Links or hrefs
- Meta descriptions
- Any actual data

### 2.3 Component Pattern Recognition

Study these patterns in Raw files but BUILD FRESH with HamsaWolf content:

1. **Navigation Pattern**
   - Logo placement
   - Menu structure
   - CTA button styling
   - Mobile menu approach

2. **Hero Section Pattern**
   - Headline hierarchy
   - Subheadline placement
   - CTA button arrangement
   - Background treatment

3. **Card Component Pattern**
   - Border/shadow styles
   - Padding consistency
   - Heading sizes
   - Content flow

4. **Grid Layouts**
   - Column counts
   - Responsive breakpoints
   - Gap sizing

5. **Footer Pattern**
   - Column organization
   - Link groupings
   - Legal text placement

REMEMBER: These are PATTERNS to learn from, not templates to fill in. Build everything fresh.

---

## 3. Content File Structure

### 3.1 Content File Format

All `copy-*.md` files use this structure:

```markdown
---
section: section-name
version: 1.0
updated: YYYY-MM-DD
---

# Section Title

## Subsection

Content here with **markdown** formatting.

### Component: ComponentName
- bullet point 1
- bullet point 2
```

### 3.2 Content Injection Rules

1. Parse frontmatter for metadata
2. Use markdown headings to identify sections
3. `### Component:` prefix indicates reusable content block
4. Preserve markdown formatting but convert to HTML
5. Content should override any placeholder text from templates

---

## 4. HTML Generation Specification

### 4.1 Page Structure Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HamsaWolf Sales Engineering - Revenue Systems That Close</title>
    <meta name="description" content="Boutique sales engineering consultancy designing and implementing revenue systems for modern go-to-market teams.">
    
    <!-- Favicon -->
    <link rel="icon" type="image/x-icon" href="/assets/favicon/favicon.ico">
    <link rel="icon" type="image/png" sizes="32x32" href="/assets/favicon/favicon-32x32.png">
    <link rel="icon" type="image/png" sizes="16x16" href="/assets/favicon/favicon-16x16.png">
    <link rel="apple-touch-icon" sizes="180x180" href="/assets/favicon/apple-touch-icon.png">
    <link rel="manifest" href="/assets/favicon/site.webmanifest">
    <meta name="theme-color" content="#0066CC">
    
    <link rel="stylesheet" href="assets/styles.css">
</head>
<body>
    <!-- Navigation -->
    <nav class="nav-primary">
        <div class="container">
            <div class="nav-brand">
                <a href="/">
                    <img src="/assets/HWLOGO.png" alt="HamsaWolf Sales Engineering" height="45">
                </a>
            </div>
            <div class="nav-menu">
                <!-- Generated menu items -->
            </div>
        </div>
    </nav>
    
    <!-- Main Content -->
    <main>
        <!-- Sections injected here -->
    </main>
    
    <!-- Footer -->
    <footer class="footer-primary">
        <!-- Generated from structure -->
    </footer>
    
    <script src="assets/js/main.js"></script>
</body>
</html>
```

### 4.2 Section Assembly Order

For `index.html`, assemble sections in this order:

1. **Hero Section** (from copy-home.md)
2. **Trust/Positioning** (from copy-home.md)
3. **Services Overview** (from copy-services.md)
4. **Case Study** (from copy-case-study.md)
5. **Who We Work With** (from copy-home.md)
6. **About** (from copy-about.md)
7. **CTA/Contact** (from copy-cta.md)
8. **Footer** (standard footer with legal links)

### 4.3 Component HTML Templates

#### Hero Component
```html
<section class="hero">
    <div class="container">
        <p class="eyebrow">{eyebrow_text}</p>
        <h1 class="hero-headline">{headline}</h1>
        <p class="hero-subheadline">{subheadline}</p>
        <div class="hero-cta">
            <a href="{primary_cta_link}" class="btn btn-primary">{primary_cta_text}</a>
            <a href="{secondary_cta_link}" class="btn btn-secondary">{secondary_cta_text}</a>
        </div>
    </div>
</section>
```

#### Service Card Component
```html
<div class="service-card">
    <h3 class="service-title">{title}</h3>
    <p class="service-description">{description}</p>
    <ul class="service-outcomes">
        {outcomes_list}
    </ul>
</div>
```

#### Case Study Section
```html
<section class="case-study">
    <div class="container">
        <h2 class="section-title">{title}</h2>
        <div class="case-study-grid">
            <div class="case-study-column">
                <h3>Starting Point</h3>
                {starting_point_content}
            </div>
            <div class="case-study-column">
                <h3>What We Built</h3>
                {what_we_built_content}
            </div>
            <div class="case-study-column">
                <h3>Results</h3>
                <div class="metrics">
                    {metrics_content}
                </div>
            </div>
        </div>
    </div>
</section>
```

#### Footer Component
```html
<footer class="footer-primary">
    <div class="container">
        <div class="footer-content">
            <div class="footer-brand">
                <h4>HamsaWolf Sales Engineering</h4>
                <p>Custom business operating systems that work as hard as you do.</p>
            </div>
            <div class="footer-links">
                <h5>Company</h5>
                <a href="#services">Services</a>
                <a href="#case-study">Case Study</a>
                <a href="#about">About</a>
                <a href="#contact">Contact</a>
            </div>
            <div class="footer-legal">
                <h5>Legal</h5>
                <a href="/privacy.html">Privacy Policy</a>
                <a href="/terms.html">Terms of Service</a>
            </div>
            <div class="footer-contact">
                <h5>Contact</h5>
                <p>build@hamsawolf.com</p>
                <p>support@hamsawolf.com</p>
                <p>legal@hamsawolf.com</p>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2025 HamsaWolf Sales Engineering. All rights reserved.</p>
            <p>Complete confidentiality. Every engagement protected by NDA.</p>
        </div>
    </div>
</footer>
```

### 4.4 Legal Pages Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{page_title} - HamsaWolf Sales Engineering</title>
    <meta name="description" content="{page_description}">
    <link rel="stylesheet" href="assets/styles.css">
</head>
<body>
    <!-- Same Navigation as index.html -->
    <nav class="nav-primary">
        <div class="container">
            <div class="nav-brand">
                <a href="/">HamsaWolf</a>
            </div>
            <div class="nav-menu">
                <a href="/#services">Services</a>
                <a href="/#case-study">Case Study</a>
                <a href="/#about">About</a>
                <a href="/#contact" class="nav-cta">Book Discovery Call</a>
            </div>
        </div>
    </nav>
    
    <!-- Legal Content -->
    <main class="legal-page">
        <div class="container">
            {content_from_copy_file}
        </div>
    </main>
    
    <!-- Same Footer as index.html -->
    <footer class="footer-primary">
        <!-- Same footer structure -->
    </footer>
    
    <script src="assets/js/main.js"></script>
</body>
</html>
```

---

### 5.1 CSS Architecture

Create a single `src/assets/styles.css` with:

1. **Reset/Normalize** (minimal reset)
2. **Design Tokens** (CSS custom properties)
3. **Base Styles** (typography, links)
4. **Layout Utilities** (container, grid)
5. **Components** (buttons, cards, sections)
6. **Page Sections** (hero, footer specifics)

### 5.2 CSS Token Definitions

```css
:root {
    /* Colors - derived from audit */
    --color-primary: {extracted_primary};
    --color-secondary: {extracted_secondary};
    --color-neutral-100: {extracted_neutral_light};
    --color-neutral-900: {extracted_neutral_dark};
    
    /* Typography - from audit or defaults */
    --font-heading: {heading_font}, system-ui, sans-serif;
    --font-body: {body_font}, system-ui, sans-serif;
    
    /* Spacing - standardized scale */
    --space-1: 0.25rem;
    --space-2: 0.5rem;
    --space-4: 1rem;
    --space-8: 2rem;
    --space-16: 4rem;
    --space-32: 8rem;
    
    /* Container */
    --container-max: 1200px;
    --container-padding: var(--space-4);
}
```

### 5.3 Component Styling Patterns

```css
/* Button Pattern */
.btn {
    padding: var(--space-2) var(--space-4);
    font-family: var(--font-body);
    font-weight: 600;
    border-radius: 4px;
    transition: all 0.2s;
    cursor: pointer;
    display: inline-block;
    text-decoration: none;
}

.btn-primary {
    background: var(--color-primary);
    color: white;
}

.btn-secondary {
    background: transparent;
    border: 2px solid var(--color-primary);
    color: var(--color-primary);
}

/* Container Pattern */
.container {
    max-width: var(--container-max);
    margin: 0 auto;
    padding: 0 var(--container-padding);
}

/* Section Pattern */
section {
    padding: var(--space-16) 0;
}
```

---

## 6. Brand & Content Guidelines

### 6.1 Company Positioning

**HamsaWolf Sales Engineering** is:
- A boutique Sales Engineering and Systems Architecture agency
- Builds fully custom business operating systems (NOT templates, NOT CRMs)
- Creates entirely bespoke modules and AI-powered internal tools
- Designs custom revenue infrastructure tailored to exact workflows
- Engineers reliability, automation, and AI-enhanced efficiency
- Acts as embedded systems architects who build from scratch

### 6.2 Target Audiences

1. **B2B SaaS & Platforms**
   - Small/mid-size go-to-market teams
   - Sales motion outpaced their systems
   - Need structure without bureaucracy

2. **Service & Experience Brands**
   - Premium venues, agencies, high-ticket services
   - Complex consultative sales
   - Want predictability with human touch

3. **Founders as Head of Sales**
   - Still personally closing deals
   - No repeatable framework
   - Need intuitive process systemized

### 6.3 Tone & Voice Rules

- **Professional & Calm**: No hype, no "10x", no guru talk
- **Systems-Focused**: "From heroic effort to engineered outcomes"
- **Operator Mindset**: Written by practitioners for practitioners
- **Impersonal**: Never mention founders/owners by name
- **Credible**: Use real metrics, specific outcomes

### 6.4 Key Messaging

Core differentiator: **"Your business deserves infrastructure that works as hard as you do."**

Secondary differentiator: **"We don't just advise. We build."**

Value propositions:
- Replace duct-tape software with custom-built business OS
- Entirely bespoke modules engineered for your exact workflow
- AI-powered tools and workflows built into the core
- Not templates, not CRMs, but Hamsa Wolf architecture
- From scattered tools to unified custom system
- Measurable outcomes from day one

---

## 7. Service Definitions

### 7.1 Three Core Packages

1. **System Blueprint** - $3,500 (One-Time)
   - Business process mapping
   - Workflow diagrams
   - Data model outline
   - System architecture draft
   - Opportunity analysis
   - Full PDF blueprint (10-15 pages)
   - Prioritized roadmap for custom tools
   - Timeline: 7-10 business days

2. **Custom System Build** - Starting at $12,500 (One-Time)
   - Custom CRM layer (Hamsa Wolf architecture)
   - Custom intake and scheduling modules
   - AI-powered communication tools
   - Internal management tools (leads, operations, dashboards)
   - Automated workflows
   - AI summaries, routing logic, triggers
   - Fully branded UI components
   - Implementation and team training
   - Timeline: 21-45 days depending on complexity

3. **System Command** - $4,500/month (90-Day Term)
   - Weekly system optimization
   - Monthly module expansions
   - Pipeline intelligence reports
   - Workflow improvements
   - AI agent updates and refinements
   - Leadership briefings
   - Operational support
   - Data insights and recommendations

### 7.2 Add-On Modules (Optional)

- Custom Dashboard Suite — $2,000
- Advanced AI Agent Package (3 agents) — $3,500
- Automated Client Portal — $4,000
- Multi-location routing logic — $2,500
- Analytics & KPI Intelligence Layer — $2,000
- Custom Payment Flow Integration — $1,500

### 7.3 Case Study Metrics

Premium Venue Brand Results:
- **63+** booked events in first year
- **6** bookings in single open-house sprint
- **1-call close** framework implemented
- Used as core example for practice

---

## 8. File Generation Instructions

### 8.1 Generation Order

1. Create `src/` directory structure
2. Generate `styles.css` from tokens
3. Read all `copy-*.md` files into memory
4. Assemble `index.html` with content
5. Generate `privacy.html` from copy-privacy.md
6. Generate `terms.html` from copy-terms.md
7. Create minimal `main.js` if needed
8. Generate `README.md` with project overview
9. Update `CHANGELOG.md` with build timestamp

### 8.2 Error Handling

- If Raw folder missing: Use default design tokens
- If Raw/styles.css missing: Create minimal default styles
- If copy files missing: STOP and report error (content is required)
- If fonts missing: Fall back to system fonts
- Log all assumptions to CHANGELOG

### 8.3 Validation Checks

After generation:
1. Verify all sections have content
2. Check all internal links resolve
3. Ensure CSS variables defined
4. Validate HTML structure
5. Confirm responsive meta tags

---

## 9. Future Automation

### 9.1 Watch Mode

Future implementation could:
- Monitor `OPERATIONS/copy-*.md` for changes
- Auto-regenerate affected HTML sections
- Hot-reload development server

### 9.2 Multi-Page Support

To add new pages:
1. Create `copy-{pagename}.md` in OPERATIONS
2. Add routing rules to this document
3. Generate `src/{pagename}.html`

### 9.3 Component Library

Future enhancement:
- Extract components to `src/components/`
- Create component manifest
- Enable component composition

---

## 10. Implementation Checklist

When Claude Code builds this site:

- [ ] Read ASSET-MIGRATION.md for asset organization instructions
- [ ] Analyze Raw/styles.css for design tokens
- [ ] Study Raw/pages/*.html for layout patterns (ignore content)
- [ ] Extract colors, fonts, spacing from Raw
- [ ] Create src/ directory structure with proper asset folders
- [ ] Migrate assets following ASSET-MIGRATION.md guidelines
- [ ] Copy selected icons from Raw/assets/icons/
- [ ] Copy appropriate images from Raw/assets/images/ 
- [ ] Copy fonts from Raw/assets/fonts to assets/fonts/
- [ ] Integrate HWLOGO.png in navigation and footer
- [ ] Add favicon links to HTML head
- [ ] Generate styles.css with extracted tokens and asset references
- [ ] Parse all copy-*.md files for content
- [ ] Build fresh HTML using patterns + content
- [ ] Assemble index.html with HamsaWolf content and branding
- [ ] Generate privacy.html from copy-privacy.md
- [ ] Generate terms.html from copy-terms.md
- [ ] Add footer with legal links to all pages
- [ ] Validate output structure
- [ ] Create README.md
- [ ] Update CHANGELOG.md
- [ ] Confirm all links work
- [ ] Test responsive behavior

---

## Version

**Document Version**: 1.0.0  
**Last Updated**: 2024-12-27  
**Specification Status**: Active

---

## Notes for Claude Code

⚠️ **CRITICAL UNDERSTANDING** ⚠️

**The Raw folder is for VISUAL REFERENCE ONLY:**
- Extract design tokens (colors, fonts, spacing) from Raw/styles.css
- Study layout patterns from Raw/pages/*.html
- BUT DO NOT COPY ANY CONTENT OR TEXT
- Build everything fresh using HamsaWolf content from OPERATIONS/copy-*.md

**Think of it this way:**
- Raw = "Make it LOOK like this"
- OPERATIONS = "Make it SAY this"

**General Rules:**
1. **This document is the law**: Follow these instructions exactly
2. **Content is king**: All content comes from OPERATIONS/copy-*.md files ONLY
3. **Tokens over hardcoding**: Extract and use design tokens from Raw
4. **Component thinking**: Learn patterns from Raw, build fresh components
5. **Document everything**: Update CHANGELOG with every build

Remember: You are building a professional consulting firm website for HamsaWolf Sales Engineering, not copying the reference site. Keep it credible, calm, and focused on custom business operating systems.

END OF OPERATIONS MANUAL

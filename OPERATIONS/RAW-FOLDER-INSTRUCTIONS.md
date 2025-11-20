# RAW FOLDER USAGE - CRITICAL INSTRUCTIONS

## ⚠️ ABSOLUTE CLARITY FOR CLAUDE CODE ⚠️

The **Raw folder** contains an EXTRACTED WEBSITE that serves as a **VISUAL STYLE GUIDE ONLY**.

---

## What the Raw Folder IS:

✅ **A DESIGN REFERENCE**
- Color palette source
- Typography examples
- Spacing patterns
- Layout structures
- Component patterns

✅ **A STYLE GUIDE**
- Professional design standards
- CSS organization patterns
- HTML structure examples
- Responsive approaches

✅ **A QUALITY BAR**
- "Make our site look THIS professional"
- "Use THIS level of polish"
- "Match THIS attention to detail"

---

## What the Raw Folder IS NOT:

❌ **NOT A TEMPLATE**
- Do not modify Raw HTML files
- Do not use as base for new pages
- Do not copy and paste sections

❌ **NOT A CONTENT SOURCE**
- Ignore ALL text content
- Ignore company names
- Ignore navigation labels
- Ignore meta descriptions

❌ **NOT OUR BRAND**
- This is someone else's site
- We're building for HamsaWolf
- Different company, different message

---

## The BUILD PROCESS:

### Step 1: EXTRACT Design Tokens
From `Raw/styles.css`, extract:
- Colors: `#hex`, `rgb()`, `hsl()` values
- Fonts: `font-family: 'Open Sans'` etc.
- Sizes: `font-size`, `padding`, `margin` patterns
- Effects: `box-shadow`, `border-radius` values

### Step 2: STUDY Layout Patterns
From `Raw/pages/*.html`, learn:
- How sections are structured
- How grids are built
- How components nest
- How responsive works

### Step 3: IGNORE All Content
Skip completely:
- Headlines and body text
- Company descriptions
- Service offerings
- Case studies
- All written content

### Step 4: BUILD Fresh
Create new using:
- Design tokens from Step 1
- Layout patterns from Step 2
- **CONTENT FROM OPERATIONS/copy-*.md**
- Fresh semantic HTML
- Clean, organized CSS

---

## Example:

### What you SEE in Raw:
```html
<section class="hero">
  <h1>Transform Your Revenue</h1>
  <p>We help B2B companies scale...</p>
</section>
```

### What you EXTRACT:
- There's a hero section pattern
- It has an h1 and a p tag
- The class is "hero"

### What you BUILD:
```html
<section class="hero">
  <h1>Your Business Deserves Infrastructure That Works As Hard As You Do</h1>
  <p>We build fully custom business operating systems...</p>
</section>
```
(Content from OPERATIONS/copy-home.md)

---

## The Golden Rule:

**Raw folder = HOW it looks**
**OPERATIONS folder = WHAT it says**

Build a site that LOOKS like Raw but SAYS HamsaWolf.

---

*This is version 2.2.0 of the build specification.*
*Last updated: January 1, 2025*

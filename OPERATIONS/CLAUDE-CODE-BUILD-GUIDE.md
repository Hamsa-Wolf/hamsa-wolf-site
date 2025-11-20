# Claude Code Build Instructions - HamsaWolf Sales Engineering Website

## Quick Start for Claude Code

You are building the HamsaWolf Sales Engineering website. This document provides the essential instructions to execute the build.

---

## 🎯 Primary Objective

Build a professional consulting website for **HamsaWolf Sales Engineering** - a boutique agency that builds fully custom business operating systems (not templates or CRMs, but bespoke infrastructure).

---

## 📂 Key Documents to Read (In Order)

1. **OPERATIONS/OPERATIONS.md** - The master build specification (this is the law)
2. **OPERATIONS/ASSET-MIGRATION.md** - How to organize and migrate assets
3. **OPERATIONS/copy-*.md files** - All the content for the website
4. **OPERATIONS/RAW-FOLDER-INSTRUCTIONS.md** - Critical understanding about Raw folder usage

---

## ⚠️ Critical Understanding

### The Raw Folder Rule
- **Raw folder = HOW it looks** (colors, fonts, spacing, layout patterns)
- **OPERATIONS folder = WHAT it says** (all content, text, messaging)
- **NEVER copy content from Raw** - only extract design tokens and patterns
- **Build everything fresh** using HamsaWolf content

### HamsaWolf's Assets
- **Logo**: `/assets/HWLOGO.png` - Use in navigation (45px height)
- **Favicon**: Complete set in `/assets/favicon/` - Already prepared
- **DO NOT** overwrite these with anything from Raw

---

## 🏗️ Build Steps

### 1. Asset Organization
- Create proper folder structure in `src/assets/`
- Copy selected professional icons from `Raw/assets/icons/`
- Copy appropriate abstract images from `Raw/assets/images/`
- Copy all font files from `Raw/assets/fonts/`
- **Skip**: Any branded content, logos, or specific company materials from Raw

### 2. Design Token Extraction
From `Raw/styles.css`, extract:
- Color palette (use for HamsaWolf's color scheme)
- Font families and sizes
- Spacing units and patterns
- Component styles (buttons, cards, etc.)

### 3. HTML Generation
- Use structure patterns from Raw as inspiration
- Fill with content from `OPERATIONS/copy-*.md` files
- Integrate HWLOGO.png in navigation
- Add complete favicon setup in `<head>`
- Build three pages: index.html, privacy.html, terms.html

### 4. CSS Creation
Professional color scheme:
```css
--color-primary: #0066CC;        /* Professional blue */
--color-teal: #00A19C;           /* Accent teal */
--color-dark: #1A1A1A;           /* Text */
--color-white: #FFFFFF;          /* White */
```

### 5. Content Integration
The site has three service packages:
- **System Blueprint** - $3,500 (diagnostic)
- **Custom System Build** - From $12,500 (implementation)
- **System Command** - $4,500/month (partnership)

Core value prop: **"Your business deserves infrastructure that works as hard as you do."**

---

## ✅ Final Checklist

- [ ] Assets organized per ASSET-MIGRATION.md
- [ ] HWLOGO.png in navigation
- [ ] Favicon properly linked
- [ ] All content from copy-*.md files integrated
- [ ] index.html complete with all sections
- [ ] privacy.html generated
- [ ] terms.html generated
- [ ] Footer with legal links on all pages
- [ ] Professional blue/teal color scheme
- [ ] No content copied from Raw (only design tokens)
- [ ] All internal links working

---

## 📝 Notes

- **Target Market**: B2B SaaS, Service Brands, Founders acting as Head of Sales
- **Tone**: Professional, calm, systems-focused (no hype)
- **Philosophy**: "From heroic effort to engineered outcomes"
- **Key Differentiator**: They BUILD custom systems, not just advise

---

**Remember**: You're building for HamsaWolf Sales Engineering, not copying the reference site. Make it look professional like the reference, but with HamsaWolf's content and branding.

---

*Document Version: 1.0*  
*Last Updated: 2025-01-01*  
*Status: Ready for execution*

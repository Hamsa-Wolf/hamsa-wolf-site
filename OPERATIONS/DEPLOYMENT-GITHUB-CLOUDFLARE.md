# GitHub & Cloudflare Pages Deployment Instructions

## For Claude Code: Deploy HamsaWolf to Production

This document provides instructions to prepare and deploy the HamsaWolf website to GitHub for Cloudflare Pages hosting.

---

## 🚀 Deployment Overview

**GitHub Organization**: https://github.com/Hamsa-Wolf  
**Deployment Method**: Cloudflare Pages (static site hosting)  
**Build Output**: The `src/` directory contains the production-ready static files

---

## 📁 Repository Structure for Cloudflare Pages

Cloudflare Pages expects this structure:
```
hamsa-wolf-site/           (repository root)
├── src/                   (build output - this is what Cloudflare serves)
│   ├── index.html
│   ├── privacy.html
│   ├── terms.html
│   └── assets/
│       ├── css/
│       ├── js/
│       ├── fonts/
│       ├── images/
│       ├── favicon/
│       └── HWLOGO.png
├── OPERATIONS/            (documentation - not served)
├── Raw/                   (reference files - not served)
├── README.md
├── .gitignore
└── CHANGELOG.md
```

---

## 🔧 Step-by-Step Deployment Instructions

### 1. Create .gitignore file
```gitignore
# Dependencies
node_modules/
.env

# OS files
.DS_Store
Thumbs.db

# Editor directories
.vscode/
.idea/

# Raw extraction files (optional - keep if you want version control)
# Raw/

# Temporary files
*.tmp
*.log

# Keep the built files - Cloudflare needs these
# Do NOT ignore src/
```

### 2. Initialize Git Repository
```bash
# Navigate to project root
cd "C:\Users\matth\Documents\Template_Pipeline\XTRACTORV1.2\output\Hamsa Wolf"

# Initialize git
git init

# Add all files
git add .

# Initial commit
git commit -m "Initial commit: HamsaWolf Sales Engineering website"
```

### 3. Create GitHub Repository
```bash
# Create a new repo on GitHub (using GitHub CLI if available)
gh repo create Hamsa-Wolf/hamsa-wolf-site --public --source=. --remote=origin --push

# OR manually add remote if repo already exists
git remote add origin https://github.com/Hamsa-Wolf/hamsa-wolf-site.git
git branch -M main
git push -u origin main
```

### 4. Cloudflare Pages Configuration

When connecting to Cloudflare Pages, use these settings:

**Build configuration:**
- **Production branch**: main
- **Build command**: (leave empty - we're serving pre-built files)
- **Build output directory**: /src
- **Root directory**: / (repository root)

**Environment variables:** None needed (static site)

---

## 📝 README.md for GitHub Repository

Create/update README.md with:

```markdown
# HamsaWolf Sales Engineering

Professional website for HamsaWolf Sales Engineering - a boutique agency that builds fully custom business operating systems.

## 🌐 Live Site
[https://hamsawolf.com](https://hamsawolf.com) (or your domain)

## 🚀 Deployment
This site is deployed via Cloudflare Pages from the `src/` directory.

## 🏗️ Structure
- `/src` - Production-ready static website files
- `/OPERATIONS` - Documentation and content source files
- `/assets` - Original assets (logo, favicon)

## 📄 Pages
- Homepage (`index.html`)
- Privacy Policy (`privacy.html`)
- Terms of Service (`terms.html`)

## 🛠️ Tech Stack
- Pure HTML/CSS/JavaScript (no framework)
- Token-based CSS design system
- Cloudflare Pages hosting

## 📦 Services
- **System Blueprint** - $3,500
- **Custom System Build** - From $12,500
- **System Command** - $4,500/month

## 📧 Contact
- Sales: build@hamsawolf.com
- Support: support@hamsawolf.com

---
*Built with documentation-driven development*
```

---

## 🎯 Cloudflare Pages Benefits

1. **Global CDN**: Automatic edge deployment
2. **SSL**: Free HTTPS certificates
3. **Custom Domain**: Easy domain connection
4. **Preview Deployments**: Automatic preview URLs for branches
5. **Fast**: Static files served from edge locations

---

## ✅ Pre-Deployment Checklist

Before pushing to GitHub:

- [ ] All HTML files generated in `src/`
- [ ] Assets properly organized in `src/assets/`
- [ ] HWLOGO.png in correct location
- [ ] Favicon files in `src/assets/favicon/`
- [ ] All internal links use relative paths
- [ ] CSS and JS files linked correctly
- [ ] No absolute local paths (C:\...)
- [ ] .gitignore file created
- [ ] README.md updated

---

## 🔄 Continuous Deployment

Once set up, the workflow is:
1. Make changes locally
2. Rebuild site in `src/`
3. Commit and push to GitHub
4. Cloudflare Pages automatically deploys

---

## 📌 Important Notes

1. **Build Directory**: Cloudflare will serve everything in `/src` as the website root
2. **Asset Paths**: Ensure all paths in HTML are relative (e.g., `assets/css/styles.css` not `/assets/css/styles.css`)
3. **404 Page**: Consider adding a `404.html` in src/ for better error handling
4. **Redirects**: Can be configured via `_redirects` file in src/ if needed

---

**Document Version**: 1.0.0  
**Created**: 2025-01-01  
**Purpose**: GitHub repository setup and Cloudflare Pages deployment

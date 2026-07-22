# 🚀 GitHub Setup Guide

Hướng dẫn push skill lên GitHub repository riêng của bạn.

---

## 📋 Prerequisites

- GitHub account
- Git installed locally (`git --version`)
- Terminal/Command line access

---

## ✅ Step-by-Step Setup

### Step 1: Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Enter repository name: `ux-ui-design-skill`
3. Add description:
   ```
   A comprehensive UX/UI Design Skill for Claude — Senior Product Designer capabilities
   ```
4. Choose visibility: **Public** (recommended for sharing)
5. Click **Create repository**

---

### Step 2: Initialize Local Repository

```bash
# Navigate to skill directory
cd ux-ui-design-skill

# Initialize git (if not already initialized)
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: UX/UI Design Skill v1.0.0"
```

---

### Step 3: Connect to GitHub

```bash
# Replace YOUR_USERNAME and YOUR_REPO with your details
git remote add origin https://github.com/YOUR_USERNAME/ux-ui-design-skill.git

# Verify connection
git remote -v
# Output should show:
# origin  https://github.com/YOUR_USERNAME/ux-ui-design-skill.git (fetch)
# origin  https://github.com/YOUR_USERNAME/ux-ui-design-skill.git (push)
```

---

### Step 4: Push to GitHub

```bash
# For first push, set upstream branch
git branch -M main

# Push to GitHub
git push -u origin main

# For future pushes, just use:
# git push
```

---

### Step 5: Verify on GitHub

1. Go to [github.com/YOUR_USERNAME/ux-ui-design-skill](https://github.com/YOUR_USERNAME/ux-ui-design-skill)
2. Verify files appear:
   - ✅ SKILL.md
   - ✅ README.md
   - ✅ INSTALLATION.md
   - ✅ references/ folder
   - ✅ .gitignore
   - ✅ LICENSE

---

## 📝 Post-Setup Configuration

### Add GitHub Topics

Go to repository Settings → Topics, add:
- `claude`
- `ai-skill`
- `design`
- `ux-ui`
- `figma`
- `product-design`
- `design-system`

This helps discoverability!

---

### Add Repository Description

Go to repository Settings → About:
- **Description**: "Senior Product Designer Skill for Claude — Design screens, components, audits, and more"
- **Website**: (leave blank or add your site)
- **Use as template**: Enable (so others can fork easily)

---

### Configure GitHub Pages (Optional)

If you want documentation site:

1. Go to Settings → Pages
2. Select Source: `main` branch, `/ (root)` folder
3. GitHub generates site at: `username.github.io/ux-ui-design-skill`

---

### Create GitHub Release

```bash
# Tag the release
git tag -a v1.0.0 -m "Release v1.0.0: Initial Release"

# Push tags
git push origin v1.0.0
```

Or via GitHub UI:
1. Click **Releases** (right side)
2. Click **Create a new release**
3. Tag version: `v1.0.0`
4. Title: `v1.0.0 - Initial Release`
5. Description:
   ```
   ## 🎉 First Release - UX/UI Design Skill v1.0.0

   ### What's New
   - 5 operating modes (Design Screen, Build Component, Audit, Edit, PRD to UI)
   - 500+ lines comprehensive guidelines
   - Design System foundation template
   - PRD reading checklist
   - Figma MCP integration support

   ### Files
   - SKILL.md: Main skill instructions
   - README.md: Overview
   - INSTALLATION.md: Setup guide
   - references/: Design system templates

   ### How to Use
   See [INSTALLATION.md](INSTALLATION.md) for detailed setup.
   ```
6. Upload files:
   - ux-ui-design-skill-1.0.0.tar.gz
   - ux-ui-design-skill-1.0.0.zip
7. Click **Publish release**

---

## 📚 Repository Documentation Structure

```
ux-ui-design-skill/
├── README.md              ← Main entry point (GitHub front page)
├── GITHUB_README.md       ← Alternative markdown format
├── GITHUB_SETUP.md        ← This file
├── INSTALLATION.md        ← Setup instructions
├── SKILL.md               ← Actual skill content
├── CHANGELOG.md           ← Version history
├── LICENSE                ← MIT License
├── .gitignore             
└── references/
    ├── design-system-foundation.md
    └── prd-reading-checklist.md
```

---

## 🔄 Regular Maintenance

### Update Skill

When you improve the skill:

```bash
# Make changes
# Edit SKILL.md, references, etc.

# Stage changes
git add .

# Commit
git commit -m "Update: improve X description"

# Push
git push origin main
```

### Create New Release

```bash
# Tag new version
git tag -a v1.1.0 -m "Release v1.1.0"

# Push
git push origin v1.1.0

# Create GitHub Release (via web)
# - Upload updated .tar.gz and .zip
# - Write release notes
```

---

## 🎯 Best Practices

### Commit Messages

Use clear, descriptive messages:
```bash
# Good ✅
git commit -m "Add: animation guidelines to component section"
git commit -m "Fix: typo in accessibility checklist"
git commit -m "Update: improve PRD reading checklist"

# Bad ❌
git commit -m "Update files"
git commit -m "Fix"
git commit -m "Changes"
```

### Branch Strategy

For larger teams:
```bash
# Feature branches
git checkout -b feature/animation-guidelines
# ... make changes ...
git commit -m "Add: animation guidelines"
git push origin feature/animation-guidelines
# Create Pull Request on GitHub

# Main branch = production ready
# Merge PRs after review
```

### Version Numbers

Follow [Semantic Versioning](https://semver.org/):
- **v1.0.0**: Major release (breaking changes)
- **v1.1.0**: Minor release (new features)
- **v1.0.1**: Patch release (bug fixes)

---

## 📊 GitHub Profile Enhancement

### Add to Your Profile

Edit your GitHub profile README to mention the skill:

```markdown
## 🎨 Open Source Contributions

- **UX/UI Design Skill**: Senior Product Designer capabilities for Claude
  - 5 operating modes
  - 1,800+ lines of comprehensive guidelines
  - Figma MCP integration
  - [View Repository](https://github.com/username/ux-ui-design-skill)
```

---

## 🤝 Encourage Contributions

Add this to README.md:

```markdown
## 🤝 Contributing

I welcome contributions! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-improvement`)
3. Make changes
4. Commit (`git commit -m 'Add: description'`)
5. Push (`git push origin feature/your-improvement`)
6. Open a Pull Request

Please ensure:
- Changes align with skill purpose
- Documentation is updated
- Test prompts reflect new features
```

---

## 📞 GitHub Issues & Discussions

### Enable Issues

1. Go to Settings → Features
2. Enable ✅ Issues
3. Optionally configure:
   - Issue templates
   - Bug report template
   - Feature request template

### Enable Discussions

1. Go to Settings → Features
2. Enable ✅ Discussions
3. Setup categories:
   - Announcements
   - Ideas
   - Q&A
   - Show & tell

---

## 🔒 Security

### Add SECURITY.md

Create file:
```
# Security Policy

## Reporting Security Issues

If you discover security issues, please email security@example.com
instead of opening a public issue.

## Security Considerations

This skill provides design guidance. It does not:
- Access or store personal data
- Connect to external services (except Figma via MCP)
- Execute code
- Modify local files
```

---

## 📈 Share & Promote

### Share Links

- Direct: `github.com/username/ux-ui-design-skill`
- Release: `github.com/username/ux-ui-design-skill/releases`
- Clone: `git clone https://github.com/username/ux-ui-design-skill.git`

### Social Media

```
Just released my UX/UI Design Skill for Claude! 🎨

A comprehensive Senior Product Designer with:
- 5 operating modes
- Design system guidelines
- PRD analysis templates
- Figma integration

🔗 https://github.com/username/ux-ui-design-skill

#Claude #DesignSystem #UX #OpenSource
```

---

## ✅ Checklist

Before marking "Production Ready":

- [ ] Repository created on GitHub
- [ ] All files pushed
- [ ] README.md visible and clear
- [ ] LICENSE file present
- [ ] .gitignore configured
- [ ] Repository topics added
- [ ] Initial release created (v1.0.0)
- [ ] Release notes written
- [ ] INSTALLATION.md complete
- [ ] CHANGELOG.md updated
- [ ] Contributing guidelines added
- [ ] Issues template added

---

## 🎉 You're Ready!

Your skill is now on GitHub and ready to share! 

Next steps:
1. Share link with team/community
2. Collect feedback via Issues
3. Track improvements in Releases
4. Build community around it

---

## 📖 GitHub Resources

- [GitHub Guides](https://guides.github.com/)
- [GitHub Docs](https://docs.github.com/)
- [Getting Started with Git](https://git-scm.com/doc)
- [Semantic Versioning](https://semver.org/)

---

**Version**: 1.0  
**Last Updated**: 2026-07-22  
**Status**: Ready to Push! 🚀

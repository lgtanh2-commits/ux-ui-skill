# UX/UI Design Skill for Claude

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Language](https://img.shields.io/badge/language-Vietnamese-orange)
![Status](https://img.shields.io/badge/status-Active-brightgreen)

**A comprehensive UX/UI Design Skill for Claude** — Hoạt động như Senior Product Designer với khả năng thiết kế screen, build component, audit design system, và tích hợp Figma.

---

## 🎨 Features

- ✨ **5 Operating Modes**:
  - Design Screen Mode (from PRD to high-fidelity UI)
  - Build Component Mode (create/improve design system components)
  - Audit Mode (review + recommend improvements)
  - Edit Mode (targeted modifications)
  - PRD to UI Mode (full end-to-end process)

- 🎯 **Interview-First Approach**: Hỏi kỹ trước khi thiết kế
- 🌐 **Design System Focused**: Prioritize reuse > create new
- ✅ **Quality Built-In**: Responsive, accessibility, consistency checklist
- 🔧 **Figma Integration**: Optional MCP support for direct file editing
- 📚 **Comprehensive Docs**: 500+ lines guidelines + reference templates
- 🇻🇳 **Vietnamese Native**: Hướng dẫn + terminology tiếng Việt

---

## 📦 What's Included

```
ux-ui-design-skill/
├── SKILL.md                    (490 lines) ← Main file
├── README.md                   Overview & quick start
├── INSTALLATION.md             Setup instructions  
├── CHANGELOG.md                Version history
├── LICENSE                     MIT License
├── .gitignore                  
└── references/
    ├── design-system-foundation.md   (300+ lines)
    └── prd-reading-checklist.md      (350+ lines)
```

---

## 🚀 Quick Start

### 1️⃣ Installation (5 minutes)

**For Claude.ai Users:**
1. Go to Settings → Skills
2. Create new skill
3. Copy `SKILL.md` content
4. Name it `ux-ui-design`
5. Save!

**For Claude Code:**
```bash
git clone https://github.com/yourusername/ux-ui-design-skill.git
cp SKILL.md ~/.claude/skills/
claude skill register ./SKILL.md
```

See **[INSTALLATION.md](INSTALLATION.md)** for detailed steps.

---

### 2️⃣ First Use

```
You: "Design a mobile checkout screen for e-commerce app"

Claude: 
→ Skill triggers automatically
→ Asks clarifying questions (target user? existing design system?)
→ Builds requirement summary
→ Creates high-fidelity UI design
→ Quality checklist + assumptions
```

---

### 3️⃣ Try All Modes

Test cases in **[TEST_PROMPTS.md](TEST_PROMPTS.md)**:
- Mode 1: Design screen from PRD
- Mode 2: Build component
- Mode 3: Audit existing design
- Mode 4: Edit specific elements
- Mode 5: Full end-to-end design

---

## 📖 Documentation

| File | Purpose | Lines |
|------|---------|-------|
| **SKILL.md** | Main instructions (all modes) | 490 |
| **README.md** | Overview & features | 200 |
| **INSTALLATION.md** | Setup guide | 350 |
| **design-system-foundation.md** | DS template | 300+ |
| **prd-reading-checklist.md** | PRD analysis guide | 350+ |
| **TEST_PROMPTS.md** | Test cases | 150 |

**Total**: 1,800+ lines of comprehensive design guidance

---

## 🎓 Core Concepts

### 5 Operating Modes

```
Mode 1: Design Screen
├─ PRD input
├─ Clarifying questions
├─ User flow building
├─ High-fidelity UI
└─ Output: Figma file + summary

Mode 2: Build Component
├─ Requirement analysis
├─ Component anatomy
├─ Properties + variants
├─ Auto Layout setup
└─ Output: Reusable component

Mode 3: Audit
├─ Design analysis
├─ Issue identification
├─ Best practices check
├─ A11y verification
└─ Output: Report + recommendations

Mode 4: Edit
├─ Targeted changes
├─ Impact analysis
├─ Consistency check
└─ Output: Updated design

Mode 5: PRD to UI
├─ Full interview
├─ Complete analysis
├─ All screens + states
├─ Prototype creation
└─ Output: Production-ready design
```

---

### Design System Priority

```
1. Reuse existing component (BEST)
   ↓
2. Extend with variant/property
   ↓
3. Create new from existing tokens
   ↓
4. Create new token (only if necessary)
```

---

### Quality Checklist

Before completion, verify:
- ✅ Solves PRD requirements
- ✅ UX is simple + clear
- ✅ UI is consistent
- ✅ Components are reusable
- ✅ Responsive (desktop/tablet/mobile)
- ✅ Accessible (WCAG AA)
- ✅ Developer handoff ready

---

## 🔌 Figma Integration

Optional Figma MCP support for:
- Reading design files
- Analyzing design system
- Suggesting improvements
- Direct file editing (if authorized)

Enable via Claude Settings → Integrations → Figma

---

## 🌟 Highlights

| Aspect | Benefit |
|--------|---------|
| **Interview-First** | Requirements fully understood before design |
| **System Thinking** | Holistic approach, not piecemeal design |
| **Best Practices** | UX principles, accessibility, responsiveness built-in |
| **Reusable Assets** | Component-based, not throwaway designs |
| **Clear Reasoning** | Every decision explained |
| **Developer-Ready** | Organized, named, documented for handoff |
| **Vietnamese** | Instructions in your language |

---

## 📋 Requirements

- Claude account (claude.ai or API)
- Basic UX/design knowledge helpful (but not required)
- (Optional) Figma account + MCP integration

---

## 💻 System Requirements

- No special dependencies
- Works on any device with Claude access
- Browser: Modern browsers (Chrome, Firefox, Safari)
- Optional: Figma for actual design work

---

## 🤝 Contributing

Contributions welcome! 

```bash
# Fork repository
# Create feature branch
git checkout -b feature/your-improvement

# Make changes
# Commit with clear messages
git commit -m "Add: new component template"

# Push and open PR
git push origin feature/your-improvement
```

---

## 📝 License

This project is licensed under the **MIT License** - see [LICENSE](LICENSE) for details.

---

## 👤 Author

**Tâm Anh (Lương Tâm Anh)**
- Product Manager / Business Analyst at QTS (Quang Truong Solutions)
- CCBA Certified
- Specializes in: Product Design, Design Systems, Figma, nexWallet Platform

---

## 🎯 Skill Trigger Keywords

Skill triggers automatically when you mention:
- `design`, `UX`, `UI`, `Figma`
- `screen`, `wireframe`, `prototype`
- `component`, `design system`
- `layout`, `responsive`, `accessibility`
- `interaction`, `animation`, `state`
- Any product design request

---

## 🔍 Examples

### Example 1: Design Screen Mode
```
Input: "Design payment confirmation screen from this PRD"
Output: 
- Clarifying questions
- User flow diagram
- High-fidelity screens
- Component specs
- Responsive variations
```

### Example 2: Build Component
```
Input: "Create reusable Button component with sizes + variants"
Output:
- Component anatomy
- Auto Layout structure
- Properties definition
- State variations (hover, active, disabled)
- Accessibility notes
```

### Example 3: Audit
```
Input: "Audit this Figma design for accessibility"
Output:
- Issues by severity (Critical, High, Medium, Low)
- Specific recommendations
- WCAG violations
- Improvement suggestions
```

---

## 📚 Learning Path

1. **Read README.md** (5 min) — Understand what skill does
2. **Review SKILL.md** (20 min) — Learn 5 modes
3. **Check TEST_PROMPTS.md** (10 min) — See example usage
4. **Try first prompt** (15 min) — Design something simple
5. **Reference docs as needed** — Design System, PRD templates

Total: ~1 hour to productive use

---

## 🐛 Troubleshooting

**Skill not triggering?**
- Verify enabled in Claude settings
- Check description is complete
- Restart Claude session
- Try more complex request (not simple queries)

**Can't access reference files?**
- Copy files to same directory as SKILL.md
- Add explicitly in Claude settings
- Or mention filename in your request

**Figma integration issues?**
- Enable Figma MCP in integrations
- Authorize access to Figma
- Share file publicly (if private)
- Skill works without Figma too!

See **[INSTALLATION.md](INSTALLATION.md)** for more troubleshooting.

---

## 📊 Stats

- **Lines of Code**: 1,800+
- **Operating Modes**: 5
- **Reference Templates**: 2
- **Quality Checklist Items**: 25+
- **Test Prompts**: 7+
- **Language**: Vietnamese (Tiếng Việt)
- **License**: MIT
- **Status**: Production Ready ✅

---

## 🚀 Roadmap

### v1.1 (Coming Soon)
- Animation guidelines
- Micro-interaction patterns
- Dark mode design guide

### v1.2 (Planned)
- Component library examples
- Design tokens export
- Accessibility audit advanced

### v2.0 (Future)
- Interactive decision trees
- Video tutorials
- Live design system examples

---

## ❓ FAQ

**Q: Is this a Figma plugin?**  
A: No, it's a Claude skill. Uses Figma MCP optionally for enhanced capabilities.

**Q: Can I modify it?**  
A: Yes! Edit SKILL.md to customize for your brand/team.

**Q: Do I need design experience?**  
A: Helpful but not required. Skill teaches best practices.

**Q: Can teams use this?**  
A: Absolutely. Share or create team version.

**Q: Supported languages?**  
A: Vietnamese natively. Can adapt to other languages.

**Q: Does it replace designers?**  
A: No. It's guidance tool for designers to work faster + smarter.

---

## 📞 Support

- 📖 Read documentation files
- 🐛 Open GitHub issues
- 💬 Check discussions
- 📧 Contact author

---

## 🎁 Credits

Built using:
- [Claude AI](https://claude.ai) by Anthropic
- [Figma MCP](https://www.figma.com/) integration
- [Material Design](https://m3.material.io/) principles
- [WCAG Accessibility](https://www.w3.org/WAI/WCAG21/quickref/) guidelines
- [Nielsen Norman UX](https://www.nngroup.com/) research

---

## 📜 Changelog

See [CHANGELOG.md](CHANGELOG.md) for version history and updates.

---

<div align="center">

**Made with 🎨 for Product Designers**

[⭐ Star us on GitHub](https://github.com/yourusername/ux-ui-design-skill) if you find it useful!

</div>

---

**Version**: 1.0.0  
**Last Updated**: 2026-07-22  
**Language**: Vietnamese (Tiếng Việt) + English  
**Status**: Active & Maintained ✅

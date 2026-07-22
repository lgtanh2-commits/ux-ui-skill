# 🚀 Installation Guide - UX/UI Design Skill

Hướng dẫn cài đặt và cấu hình UX/UI Design Skill cho Claude.

---

## 📋 Prerequisites

- Claude account (claude.ai hoặc Claude API)
- Basic understanding of design/UX concepts
- (Optional) Figma account + Figma MCP enabled

---

## 🔧 Installation Methods

### Method 1: Claude.ai Web (Recommended for beginners)

#### Step 1: Download Skill Files
```bash
# Clone repository
git clone https://github.com/yourusername/ux-ui-design-skill.git
cd ux-ui-design-skill

# Or download ZIP
# https://github.com/yourusername/ux-ui-design-skill/archive/refs/heads/main.zip
```

#### Step 2: Prepare Files
Copy files từ repository:
- `SKILL.md` (required)
- `references/design-system-foundation.md`
- `references/prd-reading-checklist.md`

#### Step 3: Upload to Claude Profile
1. Go to **claude.ai**
2. Click **⚙️ Settings** (bottom left)
3. Go to **Skills** section
4. Click **Create Skill** button
5. Copy nội dung từ `SKILL.md` vào editor
6. Set name: `ux-ui-design`
7. Click **Save Skill**

#### Step 4: Enable References (Optional)
Nếu muốn reference files có sẵn:
1. Go to **Skill Settings**
2. Add reference files:
   - `design-system-foundation.md`
   - `prd-reading-checklist.md`
3. Save

---

### Method 2: Claude Code / VS Code Extension

#### Step 1: Setup Environment
```bash
# Install Claude CLI (if using Claude Code)
npm install -g @anthropic-ai/claude

# Or use Claude Code extension in VS Code
```

#### Step 2: Create Skill Directory
```bash
mkdir -p ~/.claude/skills/ux-ui-design
cd ~/.claude/skills/ux-ui-design

# Copy files
cp SKILL.md .
mkdir -p references
cp references/* references/
```

#### Step 3: Register Skill
```bash
# Using Claude CLI
claude skill register ./SKILL.md

# Or manually add to Claude configuration
```

#### Step 4: Verify Installation
```bash
claude skill list
# Nên thấy "ux-ui-design" trong danh sách
```

---

### Method 3: GitHub Codespaces (For Development)

#### Step 1: Open in Codespaces
```bash
# Fork repository
# Click "Codespaces" tab
# Click "Create codespace on main"
```

#### Step 2: Review Files
```bash
# Files sẵn có:
ls -la
# SKILL.md, README.md, references/...
```

#### Step 3: Make Modifications
```bash
# Edit SKILL.md nếu cần customize
code SKILL.md

# Test changes
git diff SKILL.md
```

#### Step 4: Push Updates
```bash
git add .
git commit -m "Update: improve skill description"
git push origin main
```

---

## ✅ Verification

### Check if Skill Triggered

Cách kiểm tra skill hoạt động:

#### Test 1: Simple Trigger
```
Input: "Design a user profile screen"
Expected: Skill triggers automatically
```

#### Test 2: Interview Mode
```
Input: "Tôi có PRD cho feature checkout payment"
Expected: 
- Skill triggers
- Claude asks clarifying questions
- Starts interview process
```

#### Test 3: All Modes
Refer to **TEST_PROMPTS.md** untuk 7 test cases.

---

## 🔌 Figma MCP Integration

### Enable Figma MCP (Optional)

#### Step 1: Connect Figma Account
1. Go to Claude settings
2. Go to **Integrations**
3. Find **Figma** integration
4. Click **Connect**
5. Authorize Figma access

#### Step 2: Verify Connection
```
Input: "Audit my Figma file for accessibility"
Expected: Skill reads Figma file directly
```

#### Step 3: Use Features
Setelah Figma MCP enabled, skill mendapat akses:
- Read Figma files
- Analyze design system
- Suggest improvements
- (Optional) Direct file editing

---

## 📁 File Structure

```
ux-ui-design-skill/
├── SKILL.md                          # Main skill file (REQUIRED)
├── README.md                         # Overview & quick start
├── INSTALLATION.md                   # This file
├── CHANGELOG.md                      # Version history
├── LICENSE                           # MIT License
├── .gitignore                        # Git ignore rules
└── references/                       # Reference files (optional)
    ├── design-system-foundation.md   # DS template
    └── prd-reading-checklist.md      # PRD analysis guide
```

---

## 🎯 Quick Start After Installation

### 1. First Use
```
Prompt: "Design a login form untuk mobile app"

Expected Flow:
1. Skill triggers
2. Asks: Target user? Existing design system? Requirements?
3. Builds requirement summary
4. Creates design wireframes
5. High-fidelity UI
6. Quality checklist
```

### 2. Customize for Your Needs
Edit `SKILL.md`:
```markdown
# Personalization Options:

1. Color scheme (example: primary color #0066FF)
2. Typography preferences (font family)
3. Spacing baseline (8px or 4px)
4. Component library reference
5. Design system naming convention
```

### 3. Reference Files as Needed
```
When you need Design System foundation:
→ See: references/design-system-foundation.md

When analyzing PRD:
→ See: references/prd-reading-checklist.md
```

---

## 🐛 Troubleshooting

### Issue 1: Skill Not Triggering

**Symptom**: Mention "design" pero skill tidak trigger

**Solution**:
1. Verify skill enabled dalam profile
2. Check skill description dalam settings
3. Restart Claude session
4. Try explicit request: "Use UX/UI Design Skill: Design a screen"

**Hint**: Skill triggers best pada complex requests, bukan simple queries

---

### Issue 2: Can't Access Reference Files

**Symptom**: Claude says "tidak tìm thấy design-system-foundation.md"

**Solution**:
1. Copy reference files ke same folder as SKILL.md
2. In Claude settings, add references explicitly
3. Or paste content into conversation when needed

---

### Issue 3: Figma MCP Not Connected

**Symptom**: "Cannot read Figma file" error

**Solution**:
1. Enable Figma MCP dalam integrations
2. Authorize Figma account access
3. Share Figma file publicly (nếu private)
4. Or paste Figma link in request

**Note**: Skill works without Figma MCP, tapi dengan limited capabilities

---

### Issue 4: Different Output Than Expected

**Symptom**: Claude doesn't ask questions, goes straight to design

**Solution**:
1. Verify SKILL.md content is correct
2. Check if request has full context
3. Explicitly request: "Interview mode: hỏi kỹ trước thiết kế"
4. Make sure references file loaded

---

## 📚 Learning Resources

### Within the Skill
- **SKILL.md**: Comprehensive guidelines
- **README.md**: Quick overview
- **TEST_PROMPTS.md**: Example use cases
- **design-system-foundation.md**: DS best practices
- **prd-reading-checklist.md**: Requirements analysis

### External Resources
- [Figma Design System Best Practices](https://www.figma.com/)
- [Nielsen Norman UX Principles](https://www.nngroup.com/)
- [WCAG Accessibility Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [Material Design System](https://m3.material.io/)

---

## 🔄 Updating the Skill

### Check for Updates
```bash
# Navigate to skill directory
cd ux-ui-design-skill

# Check for new releases
git fetch origin
git log origin/main --oneline | head -5

# Pull latest version
git pull origin main
```

### Update Your Installation
```bash
# Copy updated SKILL.md to Claude
# (Repeat installation Method 1, Step 3-7)

# Or update via CLI
claude skill update ./SKILL.md
```

### Keep Track of Changes
- See **CHANGELOG.md** untuk history
- Watch repository untuk notifications
- Join discussions untuk feature requests

---

## 💡 Pro Tips

1. **Copy SKILL.md content completely** - Ensure all 490 lines are in Claude
2. **Bookmark reference files** - Have them available quando needed
3. **Test with TEST_PROMPTS.md** - Validate all 5 modes work
4. **Customize color/typography** - Edit base values in SKILL.md untuk match your brand
5. **Enable Figma MCP** - Dùng skill at full capacity
6. **Create team version** - Share customized skill dengan team

---

## 🤝 Contributing

Tìm bug atau improvement ideas?

```bash
# Create issue
# https://github.com/yourusername/ux-ui-design-skill/issues

# Or submit PR
git checkout -b feature/your-improvement
git commit -m "Add: description"
git push origin feature/your-improvement
# Then open PR on GitHub
```

---

## ❓ FAQ

**Q: Do I need Figma?**  
A: No, skill works standalone. Figma MCP enhances capabilities (optional).

**Q: Can I modify SKILL.md?**  
A: Yes! Customize colors, terminology, components per your needs.

**Q: What's the learning curve?**  
A: If you know UX/design, ~15 mins. Otherwise, read SKILL.md first.

**Q: Can I use for team?**  
A: Yes, share skill link or customize per team requirements.

**Q: Does it replace Figma?**  
A: No, it's a design guidance system. Still need Figma untuk actual design work.

**Q: Supported languages?**  
A: Vietnamese (Tiếng Việt). Can be adapted to other languages.

---

## 📞 Support

- 📖 Read README.md, SKILL.md, references/
- 🐛 Check Troubleshooting section above
- 💬 Open GitHub issue
- 📧 Contact author

---

**Installation Complete! 🎉**

Now try: *"Design a mobile checkout screen"*

Claude sẽ trigger UX/UI Design Skill automatically! 🚀

---

**Version**: 1.0  
**Last Updated**: 2026-07-22  
**Language**: Tiếng Việt + English

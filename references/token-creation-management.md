# Token Creation & Management Guide

## Hướng dẫn chi tiết tạo, quản lý, và áp dụng design tokens trong Figma

---

## 1. Token Creation Workflow

### Phase 1: Define (Định nghĩa)

**Output**: List các token cần tạo (từ `design-system-foundation.md`)

```
Color Tokens:
✓ Background/Primary, Background/Secondary, Background/Hover
✓ Text/Primary, Text/Secondary, Text/Disabled
✓ Border/Default, Border/Strong
✓ Action/Primary, Action/Hover, Action/Secondary
✓ Status/Success, Status/Warning, Status/Error, Status/Info

Typography Tokens:
✓ Display (48px, 700)
✓ Heading 1 (36px, 700)
✓ Heading 2 (28px, 700)
✓ Body (16px, 400)
✓ Label (12px, 500)

Spacing Tokens:
✓ 8, 16, 24, 32, 40, 48, 64

Size Tokens:
✓ Button/Small (32px)
✓ Button/Medium (40px)
✓ Input/Standard (40px)

Shadow Tokens:
✓ Shadow/Small
✓ Shadow/Medium
✓ Shadow/Large
```

---

### Phase 2: Create (Tạo trong Figma)

#### Step 2.1: Tạo Color Styles

```
Figma Workflow:
1. Open Assets panel (Shift + A)
2. Click "Colors" tab
3. Click + icon → "Create new color style"
4. Set color value (hex code)
5. Name: Background/Primary
6. Figma auto-creates "Background" folder
7. Repeat cho tất cả semantic colors
```

**Checklist**:
- [ ] All semantic colors created
- [ ] Naming follow `Category/Type/State` pattern
- [ ] Colors organized in folders (Background, Text, Action, Status)
- [ ] Example: 50+ color styles → 4-5 folders

---

#### Step 2.2: Tạo Typography Styles

```
Figma Workflow:
1. Create text element
2. Set properties:
   - Font family: Inter (or your brand font)
   - Size: 48px (for Display)
   - Weight: 700 (Bold)
   - Line height: 1.2
   - Letter spacing: -0.5px
3. Assets panel → Typography tab → + → "Create text style"
4. Name: Display
5. Repeat cho Display, Heading 1-3, Body, Label, etc.
```

**Important**: Typography style should include:
- ✅ Font family
- ✅ Size
- ✅ Weight
- ✅ Line height
- ✅ Letter spacing
- ❌ NOT color (use Color Style separately)

**Checklist**:
- [ ] All typography scales created
- [ ] Font properties match foundation doc
- [ ] Naming: Display, Heading 1, Body, Label (functional, not size-based)
- [ ] ~10 typography styles

---

#### Step 2.3: Set Up Spacing Variables (Figma 2024+)

```
Figma Workflow (if Variables supported):
1. Prototypes panel → Variables tab
2. Click + → "Create new variable collection"
3. Name: "Spacing"
4. Type: Number, Resolution: Absolute
5. Create variables:
   spacing/8 = 8
   spacing/16 = 16
   spacing/24 = 24
   spacing/32 = 32
   spacing/40 = 40
   spacing/48 = 48
   spacing/64 = 64
6. Save
```

**Fallback** (if Variables not available):
- Document spacing scale in Figma
- Manual maintain consistency when designing
- Update checklist: "All paddings/gaps use 8px scale"

---

#### Step 2.4: Set Up Shadow Styles (if tool supports)

```
Figma Workflow:
1. Create shape element
2. Design panel → Effects → + icon → Add shadow
3. Configure shadow:
   Shadow/Small:
   - X: 0, Y: 1px, Blur: 2px, Spread: 0
   - Color: rgba(0,0,0,0.05)
4. Effects dropdown → + → "Create effect style"
5. Name: Shadow/Small
6. Repeat for Shadow/Medium, Shadow/Large, Shadow/Elevated
```

---

### Phase 3: Verify (Kiểm tra)

**Checklist trước khi publish**:

```
Color Styles:
- [ ] All 50+ color tokens created
- [ ] Organized in folders (Background, Text, Border, Action, Status)
- [ ] Test: Select element → Change fill → Can see all styles?
- [ ] Contrast check: Text colors pass WCAG AA (4.5:1)?

Typography Styles:
- [ ] All ~10 styles created
- [ ] Test: Apply to text → Font/size/weight correct?
- [ ] Font family consistent (Inter, system fonts)
- [ ] Line height >= 1.4 for readability

Spacing (Variables or manual):
- [ ] All 8px-scale values documented
- [ ] Test: Set component padding to variable → works?
- [ ] Consistency check: No custom spacing outside scale

Effects/Shadows:
- [ ] All shadow styles created (if supported)
- [ ] Test: Apply shadow → renders correct?
- [ ] Elevation hierarchy: Small < Medium < Large

Organization:
- [ ] Styles grouped by category (Colors, Typography, Effects)
- [ ] Naming consistent (/, PascalCase)
- [ ] Ready to publish to team library
```

---

## 2. Token Naming Strategy

### Why Semantic Naming?

❌ **Bad naming** (Literal, not maintainable):
```
Blue1, Blue2, Blue3          ← What if brand changes to purple?
Font14px, Font16px, Font20px ← What if size scale changes?
Small, Medium, Large         ← What does "Small" mean? Small what?
```

✅ **Good naming** (Semantic, maintainable):
```
Background/Primary, Background/Secondary  ← Clear purpose
Text/Primary, Text/Secondary              ← Purpose + hierarchy
Action/Primary, Action/Hover              ← What action + state
Status/Success, Status/Warning            ← Intent-based
```

---

### Naming Patterns

#### Color Tokens

```
Background/[Type]:
  Background/Primary    ← Main background color
  Background/Secondary  ← Secondary/alt background
  Background/Hover      ← Hover state background
  Background/Selected   ← Selected/active background
  Background/Disabled   ← Disabled state background

Text/[Type]:
  Text/Primary          ← Main text color
  Text/Secondary        ← Secondary text (less important)
  Text/Tertiary         ← Tertiary text (even less important)
  Text/Disabled         ← Disabled text color

Border/[Strength]:
  Border/Default        ← Standard border
  Border/Strong         ← Strong/emphasized border
  Border/Subtle         ← Subtle/light border

Action/[Type]/[State]:
  Action/Primary        ← Primary action (main button, link)
  Action/Primary/Hover  ← Primary action hover
  Action/Primary/Active ← Primary action pressed/active
  Action/Secondary      ← Secondary action

Status/[Semantic]/[Intensity]:
  Status/Success        ← Success color (darker/standard)
  Status/Success/Light  ← Success background (lighter)
  Status/Warning        ← Warning color
  Status/Warning/Light  ← Warning background
  Status/Error          ← Error color
  Status/Info           ← Info color
```

#### Typography Tokens

```
Display          ← Largest, most prominent
Heading 1        ← Page title, major sections
Heading 2        ← Section titles
Heading 3        ← Subsection titles
Title            ← Component title (card title, modal title)
Body             ← Main body text (16px standard)
Body Small       ← Smaller body text (14px)
Label            ← Form labels, small labels (12px)
Caption          ← Caption/helper text (12px)
Helper Text      ← Additional help text
```

#### Spacing Tokens

```
Spacing/2   = 2px    (micro-spacing, borders)
Spacing/4   = 4px    (very small gaps
Spacing/8   = 8px    (base unit, most common)
Spacing/16  = 16px   (common padding)
Spacing/24  = 24px   (section spacing)
Spacing/32  = 32px   (large spacing)
Spacing/40  = 40px   (very large spacing)
Spacing/48  = 48px   (huge spacing)
Spacing/64  = 64px   (max spacing)
```

---

## 3. Token Organization in Figma File

### File Structure

```
Design System File
├─ 📄 Tokens page (documentation)
│  ├─ Color tokens table
│  ├─ Typography tokens table
│  ├─ Spacing scale reference
│  └─ Size tokens reference
│
├─ 📦 Components page
│  ├─ Button component (uses color + typo styles)
│  ├─ Input component (uses typo + spacing)
│  ├─ Card component (uses color + shadow + spacing)
│  └─ ... (other components)
│
└─ 🎨 Assets Panel (Figma)
   ├─ Colors (Color Styles)
   │  ├─ Background/
   │  ├─ Text/
   │  ├─ Border/
   │  ├─ Action/
   │  └─ Status/
   ├─ Typography (Text Styles)
   │  ├─ Display
   │  ├─ Heading 1-3
   │  ├─ Body
   │  └─ Label
   ├─ Effects (Effect Styles)
   │  ├─ Shadow/Small
   │  ├─ Shadow/Medium
   │  └─ Shadow/Large
   └─ Variables (if available)
      ├─ spacing/8
      ├─ spacing/16
      └─ spacing/24
```

---

### Library Setup (for team sharing)

**Option 1: Figma Team Library**
```
1. Create "Design System" file in Figma
2. Assets Panel → Colors/Typography tabs → Publish styles
   → "Setup library file"
3. Team → Share library
4. Other files → Assets → Enable "Design System" library
5. Use styles from library → auto-link
```

**Option 2: Figma Tokens Plugin** (3rd party)
```
1. Install "Figma Tokens" plugin
2. Export tokens as JSON
3. Commit to version control
4. Auto-generate CSS, tailwind config, etc.
5. Sync back to Figma
```

---

## 4. Token Management & Updates

### When to Update Tokens

✅ **Update existing token**:
- Color brand changes (primary blue → primary purple)
- Font size adjustment (Body 16px → Body 14px for mobile)
- Spacing scale refinement (add 28px between 24px and 32px)

❌ **Create new token** (instead of updating):
- New color for new feature (use Status/New instead)
- Additional typography level (add "Title Small" if needed)
- Different spacing for specific context (use semantic naming)

---

### How to Update Tokens Safely

**Step 1**: Identify impact
- How many components use this token?
- Which screens will be affected?
- Is it a breaking change?

**Step 2**: Update in Figma
- Select Color/Typography style
- Right-click → Edit style
- Change value
- All components using this style auto-update

**Step 3**: Review changes
- Check all affected screens
- Verify visual consistency
- Test accessibility (contrast, readability)

**Step 4**: Communicate (if team library)
- Document what changed
- Explain why (e.g., "Refined spacing scale for better visual rhythm")
- Version: v1.0 → v1.1

---

### Token Versioning (for published libraries)

**Semantic Versioning**:
```
MAJOR.MINOR.PATCH

v1.0.0 (Initial release)
v1.1.0 (Add new tokens - backward compatible)
v1.1.1 (Bug fix - no changes to appearance)
v2.0.0 (Breaking change - update color values)
```

**Example changelog**:
```
v1.0.0 - Initial Design System Release
  - 50 color tokens
  - 10 typography styles
  - Spacing scale (8px base)

v1.1.0 - Add Light/Dark Mode Support
  - New color tokens for dark theme
  - No breaking changes

v2.0.0 - Brand Refresh
  - Updated primary colors (breaking change)
  - Refined typography scale
  - All files must update

v2.1.0 - Spacing Refinement
  - Added spacing/28px variant
  - Backward compatible
```

---

## 5. Token Export for Developers

### Why Export Tokens?

Designers create tokens in Figma, developers need tokens in code:
- CSS variables
- Tailwind config
- Design token JSON
- Theme objects (React, Vue)

---

### Export Methods

#### Option 1: Manual (Simple cases)
```
Export from Figma (copy hex values):
Color/Primary = #0066FF → add to CSS:
  :root {
    --color-primary: #0066FF;
  }
```

#### Option 2: Figma Tokens Plugin
```
1. Install "Figma Tokens" plugin
2. Generate JSON from Figma styles
3. Export to GitHub
4. CI/CD generates CSS/Tailwind from JSON
5. Auto-sync back to Figma
```

#### Option 3: Programmatic (Design APIs)
```
Use Figma REST API:
- Get all color styles
- Extract values
- Generate CSS/JSON
- Commit to repo
```

---

### Export Format Examples

**CSS Variables**:
```css
:root {
  --color-background-primary: #FFFFFF;
  --color-text-primary: #1A1A1A;
  --color-action-primary: #0066FF;
  
  --spacing-8: 8px;
  --spacing-16: 16px;
  
  --shadow-small: 0 1px 2px rgba(0,0,0,0.05);
}
```

**Tailwind Config**:
```js
module.exports = {
  theme: {
    colors: {
      background: {
        primary: '#FFFFFF',
        secondary: '#F5F5F5',
      },
      text: {
        primary: '#1A1A1A',
        secondary: '#666666',
      },
    },
    spacing: {
      8: '8px',
      16: '16px',
      24: '24px',
    },
  },
}
```

**JSON**:
```json
{
  "color": {
    "background": {
      "primary": { "value": "#FFFFFF" },
      "secondary": { "value": "#F5F5F5" }
    },
    "text": {
      "primary": { "value": "#1A1A1A" }
    }
  },
  "spacing": {
    "8": { "value": "8px" },
    "16": { "value": "16px" }
  }
}
```

---

## 6. Token Application Checklist

**Before publishing component**:

```
Color Application:
- [ ] All fills use Color Styles (not literal colors)
- [ ] All strokes use Border/Default or Border/Strong
- [ ] Text color uses Text/Primary, Text/Secondary, Text/Disabled
- [ ] Hover state uses Action/Hover
- [ ] Error state uses Status/Error

Typography Application:
- [ ] Text element uses Typography Style
- [ ] No manual font size override
- [ ] Font size matches foundation (Body=16px, Label=12px)
- [ ] Line height >= 1.4 for readability

Spacing Application:
- [ ] Padding values from spacing scale (8, 16, 24, 32...)
- [ ] Gaps between items use spacing scale
- [ ] No custom padding like 17px, 33px (not in scale)
- [ ] Consistency: Same component type has same spacing

Shadow Application:
- [ ] Elevated elements use Shadow styles
- [ ] Shadow hierarchy: Small < Medium < Large
- [ ] No custom shadow values

Consistency:
- [ ] Component looks consistent with other similar components
- [ ] Spacing aligns with others in same container
- [ ] Colors match semantic meaning (primary button = Action/Primary)
```

---

## 7. Common Token Mistakes to Avoid

❌ **Mistake 1: Mixed token approaches**
```
Component A: padding 32px (literal value)
Component B: padding $spacing-32 (variable)
Component C: padding using Auto Layout + Token

→ Inconsistent, hard to update
```

✅ **Fix**: Use same approach for all components (prefer tokens)

---

❌ **Mistake 2: Too many token variations**
```
Color/Primary, Color/PrimaryHover, Color/PrimaryActive,
Color/Primary/Hover, Color/Primary/Active, Primary, Blue, Blue500...

→ Confusing, unclear which to use
```

✅ **Fix**: One naming convention, clear hierarchy
```
Action/Primary (default state)
Action/Primary/Hover (hover state)
Action/Primary/Active (pressed state)
```

---

❌ **Mistake 3: Non-semantic naming**
```
Blue, Red, Green, Font12px, Font16px, Small, Medium, Large
```

✅ **Fix**: Semantic naming
```
Action/Primary, Status/Success, Body, Heading 1, Spacing/24
```

---

❌ **Mistake 4: Using literal colors despite having Color Styles**
```
Designer creates 50 Color Styles, but still sets colors manually in components
→ When brand changes, need to update 500+ instances by hand
```

✅ **Fix**: ALWAYS use Color Styles for any color, never set literal colors in component

---

❌ **Mistake 5: Inconsistent spacing scale**
```
Padding: 16px, 20px, 28px, 36px (random values, not from scale)
Scale defined: 8, 16, 24, 32, 40
```

✅ **Fix**: ALWAYS use spacing scale (8, 16, 24, 32, 40, 48...)

---

❌ **Mistake 6: Token for edge case**
```
Create "Background/SpecialFeatureX" token just for one screen

→ Bloats design system, maintenance nightmare
```

✅ **Fix**: Reuse existing tokens, create new only if pattern repeats 3+ times

---

## 8. Quick Reference: Token Creation Checklist

```
☐ Phase 1: Define Tokens
  ☐ Color palette → semantic names
  ☐ Typography scale → sizes + weights
  ☐ Spacing scale → 8px base
  ☐ Size tokens → button, input, icon
  ☐ Shadow scale → elevation levels

☐ Phase 2: Create in Figma
  ☐ Color Styles (50+) organized by category
  ☐ Typography Styles (10+) with complete properties
  ☐ Spacing Variables (if supported)
  ☐ Shadow/Effect Styles
  ☐ Update checklist

☐ Phase 3: Verify
  ☐ All tokens created and organized
  ☐ Naming consistent across all tokens
  ☐ Styles appear in Figma Assets panel
  ☐ Can apply to elements without error

☐ Phase 4: Apply to Components
  ☐ All colors use Color Styles
  ☐ All text uses Typography Styles
  ☐ Padding/gaps use spacing scale
  ☐ Shadows use Effect Styles
  ☐ No literal values in components

☐ Phase 5: Export & Publish
  ☐ Export tokens for developers
  ☐ Setup library (if team file)
  ☐ Document in team wiki
  ☐ Version (v1.0.0)
  ☐ Share with team
```

---

**Version**: 1.0  
**Created**: 2026-07-24  
**Language**: Tiếng Việt + English (technical)

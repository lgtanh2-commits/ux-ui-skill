# Token Application Guide for Designers

## Khi thiết kế screen: Cách áp dụng tokens vào các component

---

## 1. Token Application Workflow

### Step 1: Check Available Tokens

Trước khi thiết kế, **kiểm tra token nào có sẵn**:

```
Figma Workflow:
1. Open Assets panel (Shift + A)
2. Colors tab → browse available Color Styles
3. Typography tab → browse available Text Styles
4. Prototypes → Variables → browse Spacing variables
```

### Step 2: Select Correct Token for Use Case

**Decision Tree**:

```
Need a color?
├─ Background color → use Background/Primary, Secondary, Hover
├─ Text color → use Text/Primary, Secondary, Disabled
├─ Border color → use Border/Default, Strong, Subtle
├─ Button color → use Action/Primary, Secondary
└─ Status color → use Status/Success, Warning, Error, Info

Need typography?
├─ Page title → Heading 1
├─ Section title → Heading 2
├─ Component title → Title
├─ Main text → Body
├─ Small text → Body Small
└─ Label text → Label

Need spacing?
├─ Between components → Spacing/24, Spacing/32
├─ Inside component → Spacing/8, Spacing/16
├─ Section gap → Spacing/32, Spacing/48
└─ Never use → 7px, 15px, 25px (not in scale)
```

### Step 3: Apply Token to Element

```
Figma Workflow:
1. Select element (shape, text, etc.)
2. Design panel → [property] → Click color/style dropdown
3. Select from list (organized by folder)
4. Applied!
```

### Step 4: Verify Application

```
Checklist:
- ☐ Using Color Style (not literal hex)
- ☐ Using Typography Style (not manual font setup)
- ☐ Using Spacing from scale (not random value)
- ☐ No overrides unless necessary
```

---

## 2. Color Token Application

### When to Use Each Color Category

#### Background Colors

**Use Case**: Container backgrounds, page background, card background

```
Background/Primary
├─ Default background color
├─ Page/section background
├─ Card/container fill
└─ Example: White (#FFFFFF) for light mode

Background/Secondary
├─ Alternative background (less prominent)
├─ Grouped section background
├─ Sidebar background
└─ Example: Light gray (#F5F5F5)

Background/Hover
├─ Hover state for list items
├─ Highlight on interaction
├─ When user hovers over row
└─ Example: Very light gray/blue

Background/Selected
├─ Selected/active state
├─ Current item highlighting
├─ Active tab background
└─ Example: Light blue tint

Background/Disabled
├─ Disabled state background
├─ Unavailable areas
└─ Example: Grayed out (#EFEFEF)
```

**Application Example**:
```
List item hover state:
1. Create rectangle for list item
2. Fill → select Color Style → Background/Hover
3. Copy to all list items
4. Brand changes → update Background/Hover once → all items auto-update
```

---

#### Text Colors

**Use Case**: Typography colors for different text hierarchy

```
Text/Primary
├─ Main body text
├─ Primary information
├─ Highest readability needed
├─ Example: Very dark gray (#1A1A1A)

Text/Secondary
├─ Secondary information
├─ Descriptions, metadata
├─ Less emphasis than primary
├─ Example: Medium gray (#666666)

Text/Tertiary
├─ Least important text
├─ Hints, helper text
├─ Example: Light gray (#999999)

Text/Disabled
├─ Disabled text (form inputs)
├─ Unavailable content
├─ Example: Very light gray (#CCCCCC)
```

**Application Example**:
```
Card with title + description:

Title:
1. Select text element
2. Design → Text color → Text/Primary (main text)

Description:
1. Select text element
2. Design → Text color → Text/Secondary (less important)

3. Both auto-linked to Color Style
4. If text needs to dim, use Text/Tertiary
```

---

#### Border Colors

**Use Case**: Borders, dividers, outlines

```
Border/Default
├─ Standard border (most common)
├─ Input field border
├─ Card border
├─ Divider between sections
└─ Example: Light gray (#E0E0E0)

Border/Strong
├─ Emphasized border
├─ Focus state border
├─ Important divider
└─ Example: Dark gray (#CCCCCC)

Border/Subtle
├─ Very light border
├─ Barely visible divider
├─ Minimal visual weight
└─ Example: Extra light gray (#F0F0F0)
```

**Application Example**:
```
Input field:
1. Create input rectangle
2. Stroke → Color Style → Border/Default
3. Focus state variant:
   - Stroke → Color Style → Border/Strong
   - Stroke width: 2px (more prominent)
```

---

#### Action Colors

**Use Case**: Interactive elements (buttons, links)

```
Action/Primary (default)
├─ Primary button color
├─ Main action (most important)
├─ Call-to-action
└─ Example: Blue (#0066FF)

Action/Primary/Hover
├─ Hover state of primary button
├─ Darken or emphasize primary color
└─ Example: Darker blue (#0052CC)

Action/Primary/Active
├─ Pressed/active state
├─ When button is clicked
├─ Strongest emphasis
└─ Example: Even darker blue (#003D99)

Action/Secondary
├─ Secondary button color
├─ Less important action
├─ Alternative action (not main)
└─ Example: Light blue or outline style

Action/Secondary/Hover
├─ Hover state for secondary action
└─ Subtly different from default
```

**Application Example**:
```
Button component with states:

Default state:
1. Select button shape
2. Fill → Action/Primary

Hover state (variant):
1. Create hover variant
2. Fill → Action/Primary/Hover

Active state:
1. Create active variant
2. Fill → Action/Primary/Active

→ All button instances auto-update color if Action/Primary changes
```

---

#### Status Colors

**Use Case**: Status indicators, success/error/warning messages

```
Status/Success
├─ Success state (darker, for text)
├─ Checkmark color
├─ Confirmation message
└─ Example: Green (#00AA44)

Status/Success/Light
├─ Success background (lighter tint)
├─ Success alert/toast background
├─ Less important success indication
└─ Example: Light green (#E6F9F0)

Status/Warning
├─ Warning state (text, icon)
├─ Caution indicator
├─ Action needed
└─ Example: Orange (#FFAA00)

Status/Warning/Light
├─ Warning background
├─ Warning message container
└─ Example: Light orange (#FFF4E6)

Status/Error
├─ Error state (text, icon, border)
├─ Alert/error message text
├─ Failed action
└─ Example: Red (#EE3333)

Status/Error/Light
├─ Error background
├─ Error message container
└─ Example: Light red (#FFEBEB)

Status/Info
├─ Informational state
├─ Info icon color
├─ Neutral information
└─ Example: Blue (#0066FF)

Status/Info/Light
├─ Info background
├─ Info message container
└─ Example: Light blue (#E6F2FF)
```

**Application Example**:
```
Success toast/alert:

Background:
1. Select background shape
2. Fill → Status/Success/Light

Text:
1. Select text element
2. Text color → Status/Success

Icon:
1. Select icon
2. Fill → Status/Success

→ Entire success state grouped in semantic tokens
```

---

### Color Application Best Practices

✅ **ALWAYS use Color Styles**:
```
When you need a color:
1. Never set literal hex (#0066FF)
2. Always → Assets → Select Color Style
3. Pick from list (Background, Text, Action, Status)
```

✅ **Consistency check**:
```
Same component type = same token:
- Button 1 → Action/Primary
- Button 2 → Action/Primary (same!)
- Button 3 → Action/Primary (same!)

Never mix literal colors with tokens.
```

✅ **Override only when necessary**:
```
Good override:
- Default button is Action/Primary
- One special button needs Action/Secondary (override)

Bad override:
- Button using Color Style, then override fill to literal #0066FF
- Why? Defeats purpose of tokens
```

---

## 3. Typography Token Application

### When to Use Each Typography Style

#### Display

**Use**: Splash screen hero, extra-large titles
- Largest size (48px)
- Highest visual impact
- Use sparingly (usually 1 per screen)

```
Example: Landing page hero title
1. Select text
2. Apply "Display" typography style
3. Result: 48px, 700 weight, 1.2 line height
```

---

#### Heading 1

**Use**: Page title, section heading
- Large, prominent
- Main heading hierarchy level
- Use 1-2 per page

```
Example: "Dashboard" page title
1. Select text element
2. Apply "Heading 1" style → 36px, 700
```

---

#### Heading 2

**Use**: Section subheading, card title area
- Medium-large
- Secondary heading level
- Multiple per page OK

```
Example: "Recent Activities" card title
1. Select text
2. Apply "Heading 2" → 28px, 700
```

---

#### Heading 3

**Use**: Subsection titles, dialog titles
- Medium size
- Tertiary heading

```
Example: Modal dialog title
1. Select text
2. Apply "Heading 3" → 24px, 600
```

---

#### Title

**Use**: Component-level titles
- Medium
- Use within components (card title, section title)

```
Example: Card/modal title
1. Select text
2. Apply "Title" → 20px, 600
```

---

#### Body

**Use**: Main body text, descriptions, standard text
- Default reading text
- Most common style
- Base typography for content

```
Example: Article text, description text
1. Select text
2. Apply "Body" → 16px, 400, 1.5 line height
3. Readable, standard size
```

---

#### Body Small

**Use**: Secondary text, smaller body copy
- Slightly smaller than Body
- Still readable

```
Example: Metadata, timestamps, secondary description
1. Select text
2. Apply "Body Small" → 14px, 400
```

---

#### Label

**Use**: Form labels, small UI text
- Small but prominent
- Form field labels, button text

```
Example: Form input label "Email Address"
1. Select text
2. Apply "Label" → 12px, 500 (medium weight)
3. More prominent than Caption
```

---

#### Caption

**Use**: Helper text, hints, small supporting text
- Smallest readable size
- Less important information

```
Example: Form helper text "Enter valid email"
1. Select text
2. Apply "Caption" → 12px, 400
```

---

#### Helper Text

**Use**: Detailed instructions, tips
- Same size as Caption
- Contextual help

```
Example: Form field hint "Passwords must be 8+ characters"
1. Select text
2. Apply "Helper Text" → 12px, 400
```

---

### Typography Application Decision Tree

```
What text am I designing?

Is it a page/section title?
├─ YES, main page title → Heading 1
├─ YES, section title → Heading 2
├─ YES, subsection → Heading 3
└─ NO, continue below

Is it body/main content?
├─ YES, main article text → Body
├─ YES, main description → Body
├─ YES, smaller secondary text → Body Small
└─ NO, continue below

Is it form-related?
├─ YES, form label → Label
├─ YES, form help text → Helper Text
└─ NO, continue below

Is it small support text?
├─ YES, caption/metadata → Caption
├─ YES, helper/hint → Helper Text
└─ NO, check component title

Is it component title?
└─ YES → Title

Default if unsure? → Body
```

---

### Typography Application Best Practices

✅ **ALWAYS apply complete Typography Style**:
```
Good:
1. Select text element
2. Design → Typography → "Body"
3. Auto-applies: font, size, weight, line-height, letter-spacing

Bad:
1. Manually set font to Inter
2. Manually set size to 16px
3. Manually set weight to 400
→ If Body style size changes to 15px, this text stays 16px (outdated)
```

✅ **Use Typography Style + Color Style together**:
```
Text element needs:
1. Typography Style for font/size/weight/line-height → "Body"
2. Text Color for color → "Text/Primary"

Both applied = fully tokenized text element
```

✅ **No mixed sizes**:
```
Bad:
- One "Body" text is 16px
- Another "Body" text is 15px (manual override)
→ Inconsistent appearance

Good:
- All "Body" text is 16px (from style)
- If need smaller, use "Body Small" (14px)
```

---

## 4. Spacing Token Application

### Spacing Decision Framework

```
What am I spacing?

Tiny gaps (2-4px):
├─ Border between elements
├─ Icon + text gap inside button
└─ Use: Spacing/2, Spacing/4

Small spacing (8px):
├─ Gap between icon + text
├─ Small padding inside components
├─ Gap between inline items
└─ Use: Spacing/8

Medium spacing (16px):
├─ Padding inside card/container
├─ Gap between form fields
├─ Internal component spacing
└─ Use: Spacing/16

Large spacing (24px):
├─ Gap between sections
├─ Spacing between containers
├─ Block-level spacing
└─ Use: Spacing/24

Extra large (32px+):
├─ Page-level spacing
├─ Major section gaps
├─ Between different areas
└─ Use: Spacing/32, Spacing/40, Spacing/48
```

---

### Padding Application

**Example 1: Button component**

```
Button with text + icon:

┌─────────────────────────┐
│  ↓ (icon) Add New      │  ← Total height: 40px
└─────────────────────────┘

Padding: Spacing/16 (16px) horizontal, Spacing/12 (12px) vertical
Icon + Text gap: Spacing/8 (8px)

In Figma:
1. Create Auto Layout frame (40px height)
2. Padding: left/right = Spacing/16 variable
3. Padding: top/bottom = Spacing/12 variable
4. Gap between icon & text = Spacing/8 variable
```

**Example 2: Card component**

```
Card:
┌────────────────────────────┐
│  Card Title (Heading 2)    │  ← Padding top: Spacing/24
│                            │
│  Card content text...      │  ← Content area (gap: Spacing/16)
│  More content here         │
│                            │
│  [Button] [Button]         │  ← Buttons (gap: Spacing/16)
└────────────────────────────┘

Padding: all sides = Spacing/24 (24px)
Content gap = Spacing/16 (16px)
```

---

### Gap Application (Auto Layout)

**Example: List of items**

```
List:
┌──────────────────┐
│ Item 1           │  ← Gap: Spacing/16 (16px between items)
├──────────────────┤
│ Item 2           │
├──────────────────┤
│ Item 3           │
└──────────────────┘

In Figma Auto Layout:
1. Create list container (vertical layout)
2. Gap = Spacing/16 variable
3. Each item auto-spaced 16px apart
```

---

### Spacing Scale Reference

| Value | Use Case |
|-------|----------|
| Spacing/2 (2px) | Micro spacing, border width |
| Spacing/4 (4px) | Very small gap (icon + label inside tight button) |
| Spacing/8 (8px) | Small gap (icon to text, tight spacing) |
| Spacing/12 (12px) | Medium-small (button vertical padding) |
| Spacing/16 (16px) | Standard internal spacing (card padding, field gap) |
| Spacing/20 (20px) | Medium spacing (between form sections) |
| Spacing/24 (24px) | Large spacing (card padding, section gap) |
| Spacing/32 (32px) | Large section spacing (between major sections) |
| Spacing/40 (40px) | Very large (page-level spacing) |
| Spacing/48 (48px) | Huge spacing (header + content gap) |
| Spacing/64 (64px) | Maximum spacing (between distinct areas) |

---

### Spacing Application Best Practices

✅ **ALWAYS use spacing scale**:
```
Spacing values: 8, 16, 24, 32, 40, 48, 64

Good: padding 24px (in scale)
Bad: padding 22px (random)
Bad: padding 30px (not in scale)

Exception: Touch targets (min 48px) can be custom if needed
```

✅ **Use Auto Layout with spacing variables**:
```
Instead of:
- Manually positioning each item
- Each gap is different

Do:
- Auto Layout (vertical/horizontal)
- Gap = Spacing/16 variable
- Items auto-space consistently
```

✅ **Consistency check**:
```
Same component type = same spacing:
- Card 1: padding 24px
- Card 2: padding 24px (same!)
- Card 3: padding 24px (same!)

Never mix: Card A uses 24px, Card B uses 20px
```

---

## 5. Shadow/Effect Token Application

### When to Use Shadows

**Shadow hierarchy**:

```
No shadow: Flat elements (background, text-only)
├─ Plain cards without elevation
├─ Section backgrounds

Shadow/Small: Subtle elevation
├─ Hover state on cards (not resting)
├─ Subtle floating elements
└─ Minimal depth

Shadow/Medium: Standard elevation
├─ Resting cards
├─ Modal background
├─ Default component state
└─ Most common shadow

Shadow/Large: Prominent elevation
├─ Modals (above other content)
├─ Floating action buttons (FAB)
├─ Dropdown menus
└─ Draw attention

Shadow/Elevated: Maximum elevation
├─ Top-most elements
├─ Full-screen modals
├─ Tooltips
└─ Highest z-index elements
```

---

### Shadow Application Examples

**Example 1: Card with hover state**

```
Card (resting):
- Fill: Background/Primary
- Shadow: Shadow/Medium
- Border: none

Card (hover):
- Fill: Background/Hover
- Shadow: Shadow/Large ← Lift on hover
- Border: none

→ Shadow/Medium → Shadow/Large creates depth feedback
```

**Example 2: Modal**

```
Modal overlay:
- Fill: rgba(0, 0, 0, 0.5) ← Darkening overlay

Modal content:
- Fill: Background/Primary
- Shadow: Shadow/Elevated ← Highest elevation
- Border-radius: Radius/Large

→ Shadow/Elevated makes modal stand out
```

**Example 3: Dropdown menu**

```
Menu trigger: Button
Dropdown content:
- Fill: Background/Primary
- Shadow: Shadow/Large ← Float above content
- Border: Border/Default

→ Shadow/Large shows menu is floating
```

---

### Shadow Application Best Practices

✅ **Use shadow for elevation**:
```
Elevation hierarchy:
- No shadow: Base layer (background, text)
- Small shadow: Slightly elevated
- Medium shadow: Standard card
- Large shadow: Modal, dropdown
- Elevated shadow: Top elements

→ Creates visual hierarchy through depth
```

✅ **Consistent shadow application**:
```
All cards at same level = same shadow:
- Card 1: Shadow/Medium
- Card 2: Shadow/Medium (same!)
- Card 3: Shadow/Medium (same!)

→ Creates visual consistency
```

❌ **Avoid overusing shadows**:
```
Bad: Shadow on every element
└─ Too many shadows = visual noise

Good: Shadow only for elevation/depth
└─ Shadow means "this element is floating above"
```

---

## 6. Token Override Guide

### When to Override Tokens

**Rarely override**, but sometimes necessary:

```
✅ Good reason to override:
- Component needs special state (disabled button has different color)
- Context-specific requirement (error state needs Status/Error)
- Temporary design decision (awaiting token addition)

❌ Bad reason to override:
- "Just this button is different color"
- "I prefer this shade"
- "Don't want to use the token"
→ Defeats purpose of design system
```

---

### How to Override Safely

**Step 1: Check if token exists**
```
Need Status/Warning color?
→ Check Design System if Status/Warning already exists
→ If yes, don't override, use token
→ If no, create token first
```

**Step 2: Document reason for override**
```
If must override:
- Add comment in Figma (right-click → Add comment)
- Explain why: "Temporary design, awaiting new token"
- Tag designer/PM for review
```

**Step 3: Plan to replace override**
```
Don't leave overrides permanently:
- Create proper token
- Replace override
- Delete override

Timeline: Decide override policy
- Maybe: "Max 2 weeks of override before token review"
```

---

## 7. Token Application Checklist

**Before handing off component to developer**:

```
Color Tokens:
- [ ] All fills use Color Styles
- [ ] All text colors use Text/[type] styles
- [ ] No literal hex colors (#0066FF should be Action/Primary)
- [ ] Hover/active/disabled states use appropriate color tokens
- [ ] Status/Success/Warning/Error use semantic color tokens

Typography Tokens:
- [ ] Text elements use Typography Styles (Display, Heading, Body, Label)
- [ ] No manual font size/weight/line-height (all from style)
- [ ] Font family consistent (Inter for all)
- [ ] Headlines match hierarchy (H1 larger than H2)
- [ ] Body text readable (16px, line-height 1.5)
- [ ] Small text still readable (min 12px)

Spacing Tokens:
- [ ] All padding values from spacing scale (8, 16, 24, 32...)
- [ ] All gaps between items from spacing scale
- [ ] Auto Layout used where applicable
- [ ] No arbitrary spacing like 17px, 33px, 50px
- [ ] Component spacing consistent with similar components

Shadow/Effects:
- [ ] Elevation consistent (card = Shadow/Medium, modal = Shadow/Elevated)
- [ ] Shadow adds value (doesn't clutter)
- [ ] Shadow hierarchy makes sense

Overall:
- [ ] No literal colors, fonts, spacing
- [ ] 100% tokenized component
- [ ] Ready for design system
- [ ] Developer can extract all tokens automatically
```

---

## 8. Common Token Application Mistakes

❌ **Mistake 1: Mixing literal colors with Color Styles**
```
Button default: using Color Style (Action/Primary) ✓
Button hover: set literal color #0052CC (override) ✗

→ Inconsistent, hard to update
```

✅ **Fix**: Use token for all states
```
Button default: Color Style → Action/Primary ✓
Button hover: Color Style → Action/Primary/Hover ✓
```

---

❌ **Mistake 2: Wrong color token for use case**
```
Primary button using Text/Primary (wrong!)
Should use Action/Primary
```

✅ **Fix**: Use semantic color for context
```
Button → Action/Primary
Text → Text/Primary
Border → Border/Default
Status → Status/Success
```

---

❌ **Mistake 3: Inconsistent typography sizing**
```
Component A title: 24px (manual)
Component B title: 28px (manual)

→ Unclear which is correct
```

✅ **Fix**: Use Typography Styles
```
Component A title: Heading 2 style (28px)
Component B title: Heading 2 style (28px)
```

---

❌ **Mistake 4: Spacing outside scale**
```
Padding: 15px (not in scale)
Gap: 30px (should be 32px)
Margin: 22px (should be 24px)

→ Random spacing everywhere
```

✅ **Fix**: Strict spacing scale
```
Available: 8, 16, 24, 32, 40, 48
Use only these values (exceptions: touch targets 44px+)
```

---

❌ **Mistake 5: Overriding tokens "just this once"**
```
Component using Color Style...
Then override to literal color

→ Creates maintenance nightmare
```

✅ **Fix**: Use/create proper token
```
If color needed:
1. Check if token exists
2. If yes, use token
3. If no, create token (never literal color)
```

---

## 9. Quick Reference: Token Lookup

| Need | Token | Example |
|------|-------|---------|
| **Background** | Background/Primary | White card background |
| | Background/Secondary | Grouped section background |
| | Background/Hover | List item hover state |
| **Text** | Text/Primary | Main paragraph text |
| | Text/Secondary | Description text |
| | Text/Disabled | Disabled field text |
| **Action** | Action/Primary | Main button color |
| | Action/Primary/Hover | Button hover state |
| | Action/Primary/Active | Button pressed state |
| **Status** | Status/Success | Green success message |
| | Status/Error | Red error message |
| | Status/Warning | Orange warning message |
| **Border** | Border/Default | Input field border |
| | Border/Strong | Focus state border |
| **Typography** | Heading 1 | Page title |
| | Heading 2 | Section title |
| | Body | Main text content |
| | Label | Form field label |
| **Spacing** | Spacing/8 | Icon + text gap |
| | Spacing/16 | Card internal padding |
| | Spacing/24 | Section spacing |
| | Spacing/32 | Large section gap |
| **Shadow** | Shadow/Medium | Card shadow |
| | Shadow/Large | Modal shadow |
| | Shadow/Elevated | Tooltip/floating elements |

---

**Version**: 1.0  
**Created**: 2026-07-24  
**Language**: Tiếng Việt + English (technical)

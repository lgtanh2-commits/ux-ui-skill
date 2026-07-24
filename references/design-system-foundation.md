# Design System Foundation Template

## Khi bạn cần xây dựng Design System từ đầu

### 1. Color Tokens

#### Semantic Colors
```
Background/Primary
Background/Secondary
Background/Selected
Background/Hover

Text/Primary
Text/Secondary
Text/Tertiary
Text/Disabled

Border/Default
Border/Strong
Border/Subtle

Action/Primary
Action/Primary/Hover
Action/Primary/Active
Action/Secondary
Action/Secondary/Hover

Status/Success
Status/Success/Light
Status/Warning
Status/Warning/Light
Status/Error
Status/Error/Light
Status/Info
Status/Info/Light
```

#### Example Values (dễ điều chỉnh)
- Background/Primary: #FFFFFF
- Background/Secondary: #F5F5F5
- Text/Primary: #1A1A1A
- Text/Secondary: #666666
- Text/Disabled: #CCCCCC
- Border/Default: #E0E0E0
- Action/Primary: #0066FF
- Status/Success: #00AA44
- Status/Warning: #FFAA00
- Status/Error: #EE3333

### 2. Typography Scale

| Name | Size | Weight | Line Height | Letter Spacing |
|------|------|--------|-------------|----------------|
| Display | 48px | 700 | 1.2 | -0.5px |
| Heading 1 | 36px | 700 | 1.25 | -0.25px |
| Heading 2 | 28px | 700 | 1.3 | 0 |
| Heading 3 | 24px | 600 | 1.3 | 0 |
| Title | 20px | 600 | 1.4 | 0 |
| Body | 16px | 400 | 1.5 | 0 |
| Body Small | 14px | 400 | 1.5 | 0.25px |
| Label | 12px | 500 | 1.5 | 0.5px |
| Caption | 12px | 400 | 1.4 | 0.25px |
| Helper Text | 12px | 400 | 1.4 | 0 |

**Font Family**: Inter, -apple-system, Segoe UI, Roboto

### 3. Spacing Scale

```
Spacing/2 = 2px
Spacing/4 = 4px
Spacing/8 = 8px
Spacing/12 = 12px
Spacing/16 = 16px
Spacing/20 = 20px
Spacing/24 = 24px
Spacing/32 = 32px
Spacing/40 = 40px
Spacing/48 = 48px
Spacing/64 = 64px
```

**Quy tắc**: Margin/padding = tính từ 8px base (8, 16, 24, 32, 40, 48...)

### 4. Radius Tokens

```
Radius/None = 0px
Radius/Small = 4px (input, small button)
Radius/Medium = 8px (card, standard button)
Radius/Large = 12px (modal, large card)
Radius/Full = 9999px (avatar, pill button)
```

### 5. Shadow Tokens

```
Shadow/None = none

Shadow/Small = 0 1px 2px rgba(0,0,0,0.05)

Shadow/Medium = 0 4px 8px rgba(0,0,0,0.08),
                0 2px 4px rgba(0,0,0,0.04)

Shadow/Large = 0 12px 24px rgba(0,0,0,0.12),
               0 4px 8px rgba(0,0,0,0.06)

Shadow/Elevated = 0 20px 40px rgba(0,0,0,0.16),
                  0 8px 16px rgba(0,0,0,0.08)
```

### 6. Size Tokens

```
Size/Button/Small = 32px (height)
Size/Button/Medium = 40px (height)
Size/Button/Large = 48px (height)

Size/Input/Standard = 40px (height)
Size/Input/Small = 32px (height)

Size/Icon/Small = 16px
Size/Icon/Medium = 24px
Size/Icon/Large = 32px

Size/Avatar/Small = 32px
Size/Avatar/Medium = 40px
Size/Avatar/Large = 48px

Size/Navigation/Item = 44px (height, mobile)
Size/Navigation/ItemDesktop = 48px (height, desktop)
```

---

## 🎨 How to Create Tokens in Figma

### Step 1: Color Tokens (Color Styles)

#### Workflow:
1. **Tạo Color Style cho Semantic Colors**
   - Assets panel → Colors tab → `+` (Create new color style)
   - Chọn mã màu
   - Đặt tên theo semantic naming: `Background/Primary`, `Text/Primary`, `Action/Primary`
   - Figma tự tạo folder dựa trên `/` trong tên

2. **Naming Structure**
   ```
   Background/Primary      ← Figma tạo folder "Background", style "Primary"
   Background/Secondary
   Text/Primary
   Text/Secondary
   Border/Default
   Action/Primary
   Status/Success
   ```

3. **Apply Color Style trong Component**
   - Select element (shape, text, stroke)
   - Design panel → Fill → Click fill color → Select "Color style"
   - Lựa chọn từ danh sách (grouped by folder)
   - Nếu update color style → mọi instance tự động update

#### Best Practice:
- ✅ **Use Color Styles** cho tất cả semantic colors (không set màu literal)
- ✅ **Naming**: Semantic tên (không dùng "Blue1", "Red2")
- ❌ **Avoid**: Set màu trực tiếp trên element (nếu cần thay đổi sau sẽ lâu)

---

### Step 2: Typography Tokens (Text Styles)

#### Workflow:
1. **Tạo Typography Style**
   - Create text element
   - Set font family, size, weight, line height, letter spacing
   - Assets panel → Typography tab → `+` (Create new text style)
   - Đặt tên: `Display`, `Heading 1`, `Body`, `Label`, etc.

2. **Example Setup**
   ```
   Display
   ├─ Font: Inter
   ├─ Size: 48px
   ├─ Weight: 700 (Bold)
   ├─ Line Height: 1.2 (57.6px)
   └─ Letter Spacing: -0.5px
   ```

3. **Apply Typography Style**
   - Select text element
   - Design panel → Typography section → Click style name → Select from list
   - Update text properties → auto-apply to all instances

#### Best Practice:
- ✅ **Use Text Styles** cho tất cả typography tokens
- ✅ **Separate font size từ color** (typography chỉ style text properties, color dùng Color Style)
- ✅ **Naming**: Functional tên (`Body`, `Heading 1`, `Label`) không size-based
- ❌ **Avoid**: Set font/size trực tiếp, use override ở instance

---

### Step 3: Spacing Tokens (Variables hoặc Auto Layout)

#### Option A: Figma Variables (Figma 2024+)
1. **Create Spacing Variables**
   - Prototypes panel → Variables tab → `+` (Create new variable)
   - Type: Number, Resolution: Absolute
   - Naming: `spacing/8`, `spacing/16`, `spacing/24`, etc.
   - Value: 8, 16, 24, 32, 40, 48...

2. **Apply to Component**
   - Auto Layout: Gap = select variable
   - Padding: select variable
   - Mọi component use variable auto-update khi variable change

#### Option B: Documentation (nếu project chưa dùng Variables)
- Lập danh sách spacing scale trong file
- Khi design: manually set padding/gap theo scale (8, 16, 24, 32...)
- Later: migrate sang Variables

---

### Step 4: Border Radius Tokens

**Best Practice in Figma**:
- Set radius trực tiếp trên component (không có "Radius Style" official)
- Maintain consistency bằng documentation
- Convention:
  ```
  Small corner: 4px   (Input, small button)
  Medium corner: 8px  (Card, standard button)
  Large corner: 12px  (Modal, large card)
  Full circle: 9999px (Avatar, pill button)
  ```

**Workaround**: Tạo component dengan radius mặc định, dùng property `cornerRadius` nếu cần variant

---

### Step 5: Shadow Tokens

**Best Practice**:
- Tạo **Effect Styles** cho shadows (nếu Figma hỗ trợ)
- Design panel → Effects (shadow icon) → `+` (Create effect style)
- Naming: `Shadow/Small`, `Shadow/Medium`, `Shadow/Large`, `Shadow/Elevated`

**Setup Example**:
```
Shadow/Small
├─ X: 0
├─ Y: 1px
├─ Blur: 2px
├─ Spread: 0
└─ Color: rgba(0,0,0,0.05)
```

**Apply**:
- Select element → Design panel → Effects → Add effect style
- Select từ list → auto-apply

---

### Step 6: Size Tokens (Naming Convention)

Figma không có "Size Style" chính thức, nhưng maintain consistency bằng:

1. **Component Properties**
   ```
   Button size property:
   ├─ Small (height: 32px)
   ├─ Medium (height: 40px)
   └─ Large (height: 48px)
   ```

2. **Documentation in Figma**
   - Create "Tokens" page trong file
   - List tất cả size values
   - Designer reference khi thiết kế

3. **Naming Convention**
   ```
   Component properties dùng:
   Size: Small | Medium | Large
   
   Input heights:
   Size/Input/Small = 32px
   Size/Input/Standard = 40px
   ```

---

### Organization Structure in Figma

**Recommended Folder Organization**:
```
Figma Assets Panel:
├─ Colors (Color Styles)
│  ├─ Background/Primary
│  ├─ Background/Secondary
│  ├─ Text/Primary
│  ├─ Action/Primary
│  └─ Status/Success
│
├─ Typography (Text Styles)
│  ├─ Display
│  ├─ Heading 1
│  ├─ Body
│  └─ Label
│
├─ Effects (Effect Styles) - nếu dùng shadows
│  ├─ Shadow/Small
│  ├─ Shadow/Medium
│  └─ Shadow/Large
│
└─ Variables (nếu Figma 2024+)
   ├─ spacing/8
   ├─ spacing/16
   └─ spacing/24
```

**Key Points**:
- Figma auto-groups styles by `/` character
- Maintain consistent naming across colors, typography, effects
- Use variables cho dynamic tokens (spacing, sizing)

---

### Naming Convention Rules

**Format**: `Category/Type/State`

```
Colors:
  Background/Primary
  Background/Hover
  Text/Primary
  Text/Disabled
  Action/Primary
  Action/Hover
  Status/Success

Typography:
  Display
  Heading 1
  Body
  Label

Effects:
  Shadow/Small
  Shadow/Large
```

**Rules**:
- ✅ Use `/` untuk nesting (Figma tạo folder)
- ✅ Semantic naming (Background, Text, Action, Status)
- ✅ Consistent casing (PascalCase cho style names)
- ❌ Avoid: "Color1", "Font14px", "Blue" (non-semantic)

---

### 7. Grid & Layout

```
Desktop:
- Grid: 12 columns
- Column width: variable
- Gutter: 24px
- Max width: 1440px
- Padding: 32px

Tablet:
- Grid: 8 columns
- Column width: variable
- Gutter: 16px
- Max width: 768px
- Padding: 24px

Mobile:
- Grid: 4 columns
- Column width: variable
- Gutter: 12px
- Max width: 100%
- Padding: 16px
```

### 8. Core Components (Minimal Set)

**Buttons**
- Primary, Secondary, Tertiary
- Sizes: Small, Medium, Large
- States: Default, Hover, Active, Disabled, Loading

**Inputs**
- Text input, Email, Password, Number
- Sizes: Standard, Small
- States: Default, Focused, Error, Disabled, Loading

**Form Elements**
- Checkbox, Radio, Toggle
- Select, Dropdown
- Date Picker, Textarea

**Layout**
- Card (với padding + radius + shadow)
- Container (max-width container)
- Section (vertical spacing)
- Grid (layout grid)

**Feedback**
- Alert / Banner (success, warning, error, info)
- Toast notification
- Modal
- Tooltip
- Skeleton/Loading state

**Navigation**
- Tabs
- Breadcrumbs
- Pagination
- Sidebar / Navigation menu

**Data Display**
- Table
- Avatar
- Badge
- List
- Empty state
- Error state

### 9. Accessibility Baseline

```
Color Contrast:
- Text on background: 4.5:1 (normal), 3:1 (large text)
- UI components: 3:1 minimum
- Graphics: 3:1

Focus State:
- Outline: 2px solid Action/Primary
- Outline offset: 2px

Touch Target:
- Minimum: 44x44px
- Recommended: 48x48px

Text:
- Minimum font size: 12px
- Maximum line length: 80 characters
- Line height: ≥ 1.4

Icons:
- Minimum size: 24x24px untuk interactive
- Labeling: Semua icon button harus ada label atau tooltip
```

---

## Checklist Membuat Design System Baru

- [ ] Tentukan color palette (primary, secondary, status)
- [ ] Buat semantic color tokens
- [ ] Tentukan typography scale (font family, sizes, weights)
- [ ] Buat typography styles dalam Figma
- [ ] Tentukan spacing scale
- [ ] Buat spacing tokens/variables
- [ ] Tentukan radius scale
- [ ] Tentukan shadow styles
- [ ] Tentukan size tokens untuk components
- [ ] Tentukan grid system untuk desktop/tablet/mobile
- [ ] Buat minimal set core components
- [ ] Setup Auto Layout untuk semua components
- [ ] Buat component variants untuk states
- [ ] Test accessibility (contrast, focus state)
- [ ] Document naming convention
- [ ] Create component playground
- [ ] Setup Figma library untuk sharing

---

**Tips**: Jangan tạo Design System quá chi tiết ngay từ đầu. Mulai dengan foundation (colors, typography, spacing, grid), rồi expand dần khi cần components mới.

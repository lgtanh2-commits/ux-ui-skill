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

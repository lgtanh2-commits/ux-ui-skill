# Screen Size & Responsive Layout Requirements

## Khi bạn cần định nghĩa screen size & layout structure trước khi thiết kế

---

## 1. Platform & Device Type Definition

### Primary: Web Responsive
- **Focus chính** của skill
- Hỗ trợ Desktop, Tablet, Mobile trong cùng design system
- Flexible layout adapts theo viewport width
- Breakpoint-based design

### Secondary: Mobile App (iOS/Android)
- Fixed screen sizes (xem guidelines riêng của iOS/Android)
- Có thể áp dụng responsive principles nhưng constraints khác web
- Sidebar → Bottom Tab Navigation hoặc Drawer Menu
- Topbar → Fixed Header/Navigation Bar

### Tertiary: Progressive Web App (PWA)
- Kết hợp giữa web responsive + mobile app paradigm
- Tối ưu cho touch + keyboard
- Offline-first layout considerations

### Desktop App (Electron, etc.)
- Window resizable → responsive design cần thiết
- Window minimum/maximum size constraints
- Sidebar có thể fixed hoặc collapsible
- Topbar là title bar hoặc custom header

---

## 2. Responsive Breakpoints (Web Primary)

### Standard Breakpoints

```
Mobile:       320px - 479px   (small phone, large phone)
Tablet:       480px - 1023px  (tablet landscape, tablet portrait)
Desktop:      1024px+         (desktop, wide screens)

Refinement (Desktop):
- Small desktop:   1024px - 1199px
- Standard desktop: 1200px - 1919px
- Large desktop:    1920px+
```

### Why these breakpoints?
- **Mobile → Tablet (480px)**: Shift from single-column to multi-column layout
- **Tablet → Desktop (1024px)**: Sidebar becomes permanent (iPad landscape + desktop)
- **Desktop refinement (1200px)**: Common desktop width, content usually feels comfortable at this width

### Device Examples
| Breakpoint | Devices | Layout |
|-----------|---------|--------|
| 320-479px | iPhone SE, iPhone 12 mini, small phones | Single column, no sidebar |
| 480-1023px | iPhone XR/14, iPad (portrait), iPad Mini | 2-3 columns, sidebar hidden/drawer |
| 1024-1199px | iPad (landscape), small laptops | Sidebar visible, 2-3 content columns |
| 1200px+ | Desktop, laptop, monitor | Full sidebar + multi-column content |

---

## 3. Page Layout Structure

### Standard 3-Section Layout (Desktop)

```
┌─────────────────────────────────────┐
│         Topbar (Sticky)             │ ← Height: 56-64px, FILL width, FIXED height
├────────────┬───────────────────────┤
│            │                       │
│  Sidebar   │   Content Area        │ ← Sidebar: flex/shrink, Content: FILL
│            │   (scrollable)        │
│   (auto    │                       │
│   layout)  │                       │
│            │                       │
├────────────┴───────────────────────┤
│         Footer (optional)          │ ← FILL width, content-based height
└─────────────────────────────────────┘
```

### Auto Layout Structure (Desktop Web)

**Page Root**
```
Direction: VERTICAL
Sizing: FIXED width (1440px max on large screens) or FILL
Padding: 0 (let children handle padding)
Gap: 0
```

**Topbar**
```
Direction: HORIZONTAL (contains logo, nav, user menu)
Sizing: FILL width × FIXED 64px height
Padding: 16px 24px
Gap: 16px
Position: Sticky top
```

**Main Container** (contains sidebar + content)
```
Direction: HORIZONTAL
Sizing: FILL width × FILL height
Padding: 0
Gap: 0
```

**Sidebar**
```
Direction: VERTICAL
Sizing: HUG width (expands/shrinks based on content) × FILL height
Padding: 24px 16px
Gap: 8px
Min-width: 250px (recommended)
Max-width: 400px (optional constraint)
Overflow: auto (scrollable if content exceeds)
Background: separate color (semantic token)
```

**Content Area**
```
Direction: VERTICAL
Sizing: FILL width × FILL height
Padding: 32px (top/bottom/right main content area)
Gap: 24px (between sections)
Overflow: auto (scrollable independently)
```

---

## 4. Responsive Behavior per Breakpoint

### Desktop (1024px+)

**Layout**
- Topbar: Visible, sticky
- Sidebar: Visible, fixed width or flexible
- Content: Full width minus sidebar

**Behavior**
```
Topbar Height: 64px
Sidebar Width: Flex (no fixed, expands/shrinks with content)
Content Padding: 32px
Gap between sections: 24px
Grid columns (if applicable): 12 columns
```

**Sidebar Variants**
- **Expanded**: Full navigation visible
- **Collapsed (optional)**: Icon-only mode, hover shows labels
- **Hidden (if needed)**: User toggles visibility

---

### Tablet (480px - 1023px)

**Layout**
- Topbar: Visible, sticky
- Sidebar: Hidden by default (drawer/hamburger menu)
- Content: Full width

**Behavior**
```
Topbar Height: 56px (slightly smaller)
Sidebar: Drawer menu (overlay on content) or Bottom tab nav
Content Padding: 24px
Gap between sections: 16px
Grid columns (if applicable): 8 columns
```

**Sidebar Interaction**
- Hamburger menu icon in topbar
- Opens as overlay drawer from left/right
- Closes when user taps outside or selects item
- Can slide in from side (20-30% screen width)

---

### Mobile (320px - 479px)

**Layout**
- Topbar: Visible, sticky (may be minimized)
- Sidebar: Hidden, accessible via drawer or bottom nav
- Content: Full width, single column

**Behavior**
```
Topbar Height: 48px (minimal)
Sidebar: Bottom tab navigation OR drawer menu
Content Padding: 16px
Gap between sections: 12px
Grid columns (if applicable): 4 columns or single column
```

**Considerations**
- Touch targets: ≥ 48px height for nav items
- Drawer width: 60-80% of screen width
- Bottom nav: 48px height, 4-5 items max
- Typography: Might reduce font sizes (body: 14px instead of 16px)

---

## 5. Key Layout Principles

### Topbar (Header)

✅ **Sticky behavior**
- Always visible while scrolling (unless explicitly hidden)
- Stays at viewport top
- Z-index: highest to stay above content

**Content**: Logo, main nav, user actions (search, notifications, profile)

**Responsive**
```
Desktop: 64px, full logo + navigation visible
Tablet:  56px, compact logo, hamburger menu
Mobile:  48px, icon logo, hamburger menu
```

---

### Sidebar (Navigation)

✅ **Flexible Width (Desktop)**
- Expands/shrinks based on content
- No fixed width → allows navigation items with varying label lengths
- Min-width: ~250px (recommendation)
- Max-width: optional, can constrain to ~400px

✅ **Vertical Auto Layout**
- Items stack vertically with consistent gaps
- Each item can have icon + label
- Hover/active states

✅ **Responsive Behavior**
```
Desktop (1024px+): Sidebar VISIBLE
- Auto Layout: VERTICAL
- Sizing: HUG width, FILL height
- Overflow: auto

Tablet (480-1023px): Sidebar HIDDEN (drawer menu)
- Toggle via hamburger menu
- Drawer width: ~320px (adjustable)
- Overlay on content with backdrop

Mobile (<480px): Sidebar HIDDEN (drawer menu or bottom nav)
- If drawer: same as tablet
- If bottom nav: 5 items max, 48px height
```

---

### Content Area

✅ **Fills remaining space**
- FILL width (minus sidebar on desktop)
- FILL height (minus topbar)
- Vertical scroll when content exceeds viewport

✅ **Padding strategy**
```
Desktop: 32px horizontal, 24-32px vertical
Tablet:  24px horizontal, 20-24px vertical
Mobile:  16px horizontal, 16-20px vertical
```

✅ **Max-width container (optional)**
- Large screens may want max-width on content
- Prevents text lines from becoming too long (readability)
- Common: 1200px for main content, 1400px for wide layouts

---

## 6. Common Layout Patterns

### Pattern A: Full-Width Sidebar + Content
```
Desktop:
├─ Topbar (sticky)
├─ [Sidebar VISIBLE] [Content FILL]
└─ Footer (optional)

Tablet/Mobile:
├─ Topbar (sticky) + Hamburger
├─ [Drawer/Menu HIDDEN] [Content FILL]
└─ Footer (optional)
```

**When**: Admin dashboards, project management tools, SaaS apps

---

### Pattern B: Collapsible Sidebar (Icon-only mode)
```
Desktop:
├─ Topbar (sticky)
├─ [Sidebar COLLAPSED: 80px] [Content FILL]
  OR
  [Sidebar EXPANDED: 250px] [Content adjusted]
└─ Footer (optional)

Tablet/Mobile: Same as Pattern A
```

**When**: Apps with many sidebar items, desktop users prefer focus on content

---

### Pattern C: No Sidebar (Content-only)
```
All breakpoints:
├─ Topbar (sticky)
├─ [Content area (full width)]
└─ Footer (optional)
```

**When**: Landing pages, documentation, blogs, simple single-purpose pages

---

### Pattern D: Bottom Navigation (Mobile-first)
```
Desktop:
├─ Topbar (sticky)
├─ [Sidebar VISIBLE] [Content]
└─ [Bottom nav: HIDDEN]

Tablet:
├─ Topbar (sticky)
├─ [Sidebar: Drawer] [Content]
└─ [Bottom nav: VISIBLE, 48px]

Mobile:
├─ Topbar (sticky, minimal)
├─ [Content]
└─ [Bottom nav: 48px, 4-5 items, FIXED]
```

**When**: Mobile-first apps, social media, content consumption apps

---

## 7. Auto Layout Setup Examples

### Example 1: Standard Web App (3-section layout, desktop priority)

```figma
Page Root
├─ Topbar (HORIZONTAL)
│  ├─ Logo + Nav (HUG)
│  └─ User Menu (HUG)
│  Properties: FILL×FIXED(64px), padding 16px, gap 16px
│
├─ Main (HORIZONTAL)
│  ├─ Sidebar (VERTICAL)
│  │  ├─ Nav Item 1
│  │  ├─ Nav Item 2
│  │  └─ Nav Item 3
│  │  Properties: HUG×FILL, padding 24px, gap 8px
│  │
│  └─ Content (VERTICAL)
│     ├─ Breadcrumb
│     ├─ Page Title
│     ├─ Content Section 1
│     └─ Content Section 2
│     Properties: FILL×FILL, padding 32px, gap 24px
│
└─ Footer (HORIZONTAL)
   Properties: FILL×HUG, padding 24px, gap 16px
```

---

### Example 2: Mobile-first with Bottom Nav

```figma
Page Root (VERTICAL)
├─ Topbar (HORIZONTAL)
│  Properties: FILL×FIXED(48px)
│
├─ Content (VERTICAL)
│  Properties: FILL×FILL, padding 16px, gap 12px
│
└─ BottomNav (HORIZONTAL)
   ├─ Tab 1 (Home)
   ├─ Tab 2 (Search)
   ├─ Tab 3 (Favorites)
   └─ Tab 4 (Profile)
   Properties: FILL×FIXED(48px), gap 0
```

---

## 8. Clarifying Questions (Platform & Layout Definition)

### Questions to Ask User

**Platform & Scope**
```
1. Is this for WEB RESPONSIVE (primary), Mobile App, or PWA?
   → Determines breakpoint strategy & constraints

2. What's the primary device/screen size users will use?
   → Desktop, tablet, or mobile?
   → If responsive web, which breakpoint to design first?

3. Do you need to support all breakpoints (desktop/tablet/mobile)?
   Or specific ones? (e.g., desktop + tablet only, no mobile)
   → Affects responsive testing scope
```

**Navigation & Layout**
```
4. Does the app need a sidebar/navigation panel?
   → Yes: Should it be fixed width or flexible?
   → No: Keep content full-width

5. On mobile/tablet, how should the sidebar behave?
   → Drawer/hamburger menu (left/right)?
   → Bottom tab navigation?
   → Hidden completely?

6. Should the topbar always be sticky (visible while scrolling)?
   → Yes: Typical for app navigation
   → No: Scrolls away with content
   → Conditional: Hide on scroll, show on scroll-up

7. Are there any width constraints?
   → Max-width for content area (for readability)?
   → Min-width for desktop?
   → Example: Max 1200px for main content area?
```

**Content & Sections**
```
8. What main sections will the page have?
   → Example: Sidebar + Header + Content + Footer
   → Determine which sections are responsive vs fixed

9. Any sections that should have different behavior on mobile?
   → Example: Sidebar sidebar on desktop, drawer on mobile
   → Example: Horizontal tab list → collapsible on mobile
```

---

## 9. Checklist: Before Starting Design

- [ ] **Platform defined**: Web responsive / Mobile app / PWA / Desktop app?
- [ ] **Primary breakpoint identified**: Which size to design first?
- [ ] **All needed breakpoints listed**: Desktop/Tablet/Mobile? Any gaps?
- [ ] **Layout pattern chosen**: 3-section (sidebar+content) or content-only?
- [ ] **Topbar behavior**: Sticky? Collapsible? Height defined?
- [ ] **Sidebar behavior (desktop)**: Fixed width / flexible / collapsible?
- [ ] **Sidebar behavior (mobile)**: Drawer menu / bottom nav / hidden?
- [ ] **Content padding**: Defined for each breakpoint?
- [ ] **Max-width constraints**: Any limits on content width?
- [ ] **Responsive breakpoints**: Specific pixel values confirmed?
- [ ] **Component sizing**: Touch targets 48px? Icons 24px? Buttons 40px+ height?
- [ ] **Typography scale**: Same across breakpoints or responsive?
- [ ] **Spacing scale**: Same or responsive (32px desktop, 24px tablet, 16px mobile)?

---

## 10. Common Mistakes to Avoid

❌ **Not asking about platform**
- Designing desktop-only layout when responsive needed
- Assuming layout without clarifying

❌ **Sidebar with fixed width that breaks responsive**
- Desktop: 250px sidebar + content FILL → works
- Tablet: Same fixed 250px sidebar → content too narrow → broken
- Solution: Sidebar HUG width on desktop, hidden on tablet

❌ **Topbar height not responsive**
- Using 64px on all breakpoints → wastes space on mobile
- Solution: 64px desktop, 56px tablet, 48px mobile

❌ **Padding not responsive**
- Using 32px padding on mobile 320px screen → only 256px content width
- Solution: 32px desktop, 24px tablet, 16px mobile

❌ **Not testing responsive behavior**
- Designed for desktop but didn't test mobile
- Sidebar overlaps content, text unreadable, buttons too small

❌ **Mixing fixed and flexible sizing incorrectly**
- Sidebar: FIXED 250px, Content: FILL → sidebar pushes off-screen on small viewport
- Solution: Use breakpoint-based visibility or drawer pattern

---

## 11. Reference: Default Sizes (if no specific requirement)

### Topbar Height
```
Desktop: 64px
Tablet:  56px
Mobile:  48px
```

### Sidebar Width
```
Desktop: HUG (min ~250px, max ~400px)
Tablet:  Drawer 320px or Bottom Nav 48px
Mobile:  Drawer 80% width or Bottom Nav 48px
```

### Content Padding
```
Desktop: 32px horizontal, 24-32px vertical
Tablet:  24px horizontal, 20-24px vertical
Mobile:  16px horizontal, 16-20px vertical
```

### Touch Target (interactive elements)
```
Minimum: 44×44px (WCAG guideline)
Recommended: 48×48px
```

### Typography (Body text)
```
Desktop: 16px
Tablet:  16px (can reduce to 14px if space critical)
Mobile:  14-16px (consider readability)
```

---

## When to Use This Document

✅ **Trong quy trình "Interview & Analysis"**:
- Sau khi tóm tắt yêu cầu
- **Trước khi** hỏi các clarifying questions khác
- Dùng section 8 (Clarifying Questions) làm template

✅ **Khi xây dựng layout trong Figma**:
- Reference section 7 (Auto Layout Setup Examples)
- Áp dụng responsive behavior từ section 4

✅ **Khi kiểm tra chất lượng**:
- Verify responsive behavior theo section 4
- Avoid mistakes từ section 10

---

**Version**: 1.0  
**Created**: 2026-07-24  
**Language**: Tiếng Việt + English (technical terms)

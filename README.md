# UX/UI Design Skill

Một skill toàn diện để Claude hoạt động như **Senior Product Designer** với khả năng:
- Phân tích PRD và xây dựng user flow
- Thiết kế screen, component, design system
- Audit thiết kế hiện có
- Chỉnh sửa + tối ưu hóa giao diện
- Tích hợp với Figma để làm việc trực tiếp

## 📁 Cấu Trúc Skill

```
ux-ui-design-skill/
├── SKILL.md                           # Main skill instructions (tất cả modes)
├── README.md                          # File này
└── references/
    ├── screen-size-layout-requirements.md    # Platform, breakpoint, layout structure ⭐ NEW
    ├── design-system-foundation.md          # Template xây dựng Design System từ đầu
    └── prd-reading-checklist.md             # Checklist đọc & phân tích PRD
```

## 🎯 Khi Nào Dùng Skill Này

**Skill trigger tự động** khi mention các từ khóa:
- "design", "UX", "UI", "Figma"
- "screen", "wireframe", "prototype"
- "component", "design system"
- "layout", "responsive", "accessibility"
- "interaction", "animate", "state"
- Hoặc bất kỳ yêu cầu thiết kế sản phẩm nào

## 📋 5 Modes Hoạt Động

### 1️⃣ Design Screen Mode (Ưu tiên cao)
Thiết kế screen từ PRD:
1. Phân tích PRD → hỏi clarifying questions
2. Xây dựng flow + xác định screens
3. Xác định components
4. Thiết kế trong Figma
5. Kiểm tra responsive + a11y

**Khi nào dùng**: "Design form nhập user info", "Create payment confirmation screen"

---

### 2️⃣ Build Component Mode (Ưu tiên cao)
Tạo hoặc cải tiến component:
1. Kiểm tra component tương tự
2. Xác định anatomy + properties + variants
3. Xây dựng Auto Layout
4. Test với different content
5. Document cách dùng

**Khi nào dùng**: "Build a reusable button component", "Create date picker"

---

### 3️⃣ Audit Mode (Ưu tiên trung bình)
Kiểm tra thiết kế hiện có:
1. Đọc Figma file
2. Kiểm tra UX + UI + Component + Responsive + A11y
3. Liệt kê vấn đề theo độ nghiêm trọng
4. Đề xuất cải tiến

**Khi nào dùng**: "Audit this design", "Check if responsive", "Review for accessibility"

---

### 4️⃣ Edit Mode (Ưu tiên trung bình)
Chỉnh sửa thiết kế cụ thể:
1. Xác định layer/component cần sửa
2. Thực hiện chỉnh sửa
3. Giữ nguyên phần không liên quan
4. Kiểm tra ảnh hưởng đến variant khác

**Khi nào dùng**: "Change button color to red", "Update spacing", "Replace icon"

---

### 5️⃣ PRD to UI Mode (Full process)
Xử lý toàn bộ từ PRD đến design hoàn chỉnh:
- Tóm tắt + hỏi rõ
- Xây dựng IA + flow
- Thiết kế toàn bộ states
- Kiểm tra responsive + a11y
- Tạo prototype

**Khi nào dùng**: "Tôi có PRD, cần thiết kế hoàn chỉnh từ đầu"

---

## 📚 Reference Files

### `screen-size-layout-requirements.md` ⭐ NEW
Định nghĩa screen size, responsive breakpoint, layout structure:
- Platform definitions (web responsive, mobile app, PWA, desktop)
- Standard breakpoints (320px, 480px, 1024px)
- Page layout structure (topbar sticky, sidebar flexible, content area)
- Auto Layout setup patterns với ví dụ Figma
- Responsive behavior per breakpoint
- Common layout patterns (3-section, collapsible, content-only, bottom nav)
- Clarifying questions template để xác định platform & layout
- Checklist & common mistakes

**Dùng khi**: Bắt đầu design, cần xác định platform & layout trước tiên — **LUÔN hỏi platform trước khi thiết kế!**

---

### `design-system-foundation.md`
Template cho xây dựng Design System từ đầu:
- Color tokens (semantic)
- Typography scale
- Spacing, radius, shadow
- Size tokens
- Grid system
- Core components list
- A11y baseline

**Dùng khi**: Thiết kế product mới hoặc update Design System

---

### `prd-reading-checklist.md`
Checklist chi tiết để đọc + phân tích PRD:
- 7 steps phân tích
- Requirements extraction
- Flow building
- Screen identification
- Component inventory
- Clarifying questions template
- PRD summary document template

**Dùng khi**: Nhận PRD và cần hiểu rõ trước thiết kế

---

## 🔧 Figma Integration

Skill hỗ trợ tích hợp **Figma MCP** (nếu có sẵn):

### Audit Workflow
```
PRD/Request
  ↓
Figma file (dùng MCP đọc)
  ↓
Phân tích Design System + Components + States
  ↓
Audit report (vấn đề + đề xuất)
```

### Design Workflow
```
PRD/Request
  ↓
Interview + Analysis
  ↓
Create/Edit in Figma (dùng MCP)
  ↓
High-fidelity UI
  ↓
Quality check
```

### Edit Workflow
```
Request ("Change X")
  ↓
Xác định layer/component
  ↓
Edit in Figma (dùng MCP)
  ↓
Verify ảnh hưởng
  ↓
Done
```

---

## 🎨 Design System Priority

Skill luôn ưu tiên theo thứ tự:
1. **Sử dụng component có sẵn** (BEST)
2. Mở rộng bằng variant/property
3. Tạo component mới dựa trên token hiện có
4. Tạo token mới (ONLY IF NECESSARY)

**KHÔNG bao giờ**:
- Tạo màu/typography/spacing tùy ý
- Detach component để chỉnh sửa
- Bỏ qua Design System
- Bỏ qua empty/loading/error states

---

## ✅ Quality Checklist (Luôn kiểm tra)

### Product
- ✓ Giải quyết đúng yêu cầu PRD?
- ✓ User goal rõ ràng?
- ✓ Business rule được thể hiện?

### UX
- ✓ Flow đơn giản?
- ✓ Error prevention?
- ✓ Empty/Loading/Error states?

### UI
- ✓ Typography nhất quán?
- ✓ Spacing theo token?
- ✓ Color theo semantic token?

### Component
- ✓ Dùng component sẵn có?
- ✓ Auto Layout hoạt động?
- ✓ Properties đầy đủ?

### Responsive & A11y
- ✓ Desktop/Tablet/Mobile?
- ✓ Touch target ≥ 48x48px?
- ✓ Contrast WCAG AA?
- ✓ Focus state rõ?

### Developer Handoff
- ✓ Layer đặt tên rõ?
- ✓ Component + token tái dùng?
- ✓ State đầy đủ?

---

## 🎓 Workflow Example

### Scenario: Design a user onboarding flow

```
1. INTERVIEW PHASE
   → Đọc PRD
   → Hỏi: Target user? Key steps? Permissions?
   → Xác định flow + screens + components

2. DESIGN PHASE
   → Kiểm tra Design System sẵn có
   → Xác định component dùng lại vs tạo mới
   → Thiết kế screens + states trong Figma
   → Tạo variants cho different scenarios

3. QUALITY CHECK
   → Responsive test (desktop/tablet/mobile)
   → A11y check (contrast, focus state, labels)
   → Empty/Loading/Error states
   → Component consistency

4. HANDOFF
   → Tóm tắt: Screens + Components + States
   → Giả định + cần xác nhận
   → Prototype interactions nếu cần
```

---

## 💡 Pro Tips

1. **LUÔN hỏi kỹ** trước khi thiết kế - time investment dầu = efficiency sau
2. **LUÔN kiểm tra** Design System - tái dùng > tạo mới
3. **LUÔN tóm tắt** giả định + vấn đề cần xác nhận
4. **LUÔN test** responsive + accessibility - không phải optional
5. **Giải thích reasoning** - "Tại sao lựa chọn này?" > "Vì vậy"

---

## 📖 Base Framework

Skill này dựa trên file hướng dẫn **"UX/UI Product Design Skill.md"** - một framework toàn diện cho Senior Product Designer bao gồm:
- Quy trình đọc PRD chi tiết
- 5 modes hoạt động riêng biệt
- Design System foundation
- Component building guidelines
- UX principles + checklist
- Accessibility + responsive rules
- Developer handoff standards

---

**Version**: 1.0  
**Created**: 2026-07-22  
**Language**: Tiếng Việt

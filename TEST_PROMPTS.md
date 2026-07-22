# Test Prompts - Kiểm Tra Skill Hoạt Động

Dùng các prompt mẫu sau để kiểm tra xem skill có trigger và hoạt động đúng:

---

## Test 1: Design Screen Mode

**Prompt:**
```
Tôi có một PRD cho tính năng "User Profile Settings" trên mobile app. 
User nên có thể:
1. Xem thông tin cá nhân hiện tại
2. Chỉnh sửa name, email, phone
3. Thay đổi password
4. Logout

PRD chưa chi tiết lắm. Tôi cần bạn thiết kế 4 screens cho tính năng này.
```

**Expected**: Skill trigger → Phỏng vấn kỹ → Xây dựng flow → Thiết kế screens

---

## Test 2: Build Component Mode

**Prompt:**
```
Tôi cần xây dựng một component "Input Field" cho design system nexWallet.
Component này cần hỗ trợ:
- Text, email, password, number types
- Label + helper text + error message
- Icon left + icon right
- State: default, focused, filled, error, disabled
- Size: small, medium, large

Tôi muốn design pattern có Auto Layout + Variants.
```

**Expected**: Skill trigger → Xác định anatomy + properties + variants → Xây dựng Auto Layout → Test cases

---

## Test 3: Audit Mode

**Prompt:**
```
Tôi có Figma file thiết kế cho tính năng "Insurance Purchase Flow".
Tôi không chắc liệu thiết kế có tốt không. 
Có thể kiểm tra:
- UX consistency
- Component reusability
- Responsive behavior
- Accessibility

Figma: [link hoặc description]
```

**Expected**: Skill trigger → Audit → Report vấn đề + đề xuất

---

## Test 4: Edit Mode

**Prompt:**
```
Trong Figma file của tôi, tôi muốn:
1. Đổi màu button primary từ xanh sang đỏ
2. Tăng spacing giữa form fields từ 16px lên 24px
3. Thay thế icon "settings" bằng icon "gear"

Có thể update được không?
```

**Expected**: Skill trigger → Xác định chính xác elements → Chỉnh sửa → Verify ảnh hưởng

---

## Test 5: PRD to UI Mode - Full Process

**Prompt:**
```
Tôi vừa nhận PRD mới cho feature "Payment Receipt". 
PRD có các requirement:
- Hiển thị chi tiết giao dịch (date, amount, recipient, method)
- User có thể download PDF hoặc share
- Có history của các transactions cũ
- Mobile + web responsive

Tôi cần toàn bộ design: wireframe, high-fidelity screens, component, prototype.
Có làm được không?
```

**Expected**: Skill trigger PRD to UI Mode → Full process interview → Flow building → Screen design → Component definition → Quality check

---

## Test 6: Design System Foundation

**Prompt:**
```
Tôi bắt đầu project mới và cần xây dựng design system từ đầu.
Tôi có logo color (primary: #0066FF, secondary: #FF6600).
Tôi cần:
- Color tokens
- Typography scale
- Spacing scale
- Core components list

Bạn có thể xây dựng foundation không?
```

**Expected**: Skill trigger → Tham khảo design-system-foundation.md → Customize base values → Output semantic tokens + guidelines

---

## Test 7: Mixed Request (Edit + Audit)

**Prompt:**
```
Tôi muốn:
1. Audit thiết kế form hiện tại (check error states, validation)
2. Thay đổi label styling từ Bold → Normal weight
3. Kiểm tra contrast ratio để conform WCAG AA

Figma file sẵn có. Có thể làm cả 3 cái?
```

**Expected**: Skill trigger → Kết hợp Audit Mode + Edit Mode → Report + Changes

---

## Cách Kiểm Tra

1. **Copy prompt** từ mẫu trên
2. **Paste vào chat** mà skill được enable
3. **Quan sát**:
   - Skill có trigger không?
   - Workflow có theo đúng 5 modes không?
   - Output có tuân theo quality checklist không?
   - References có được dùng không?

---

## Success Criteria

Skill hoạt động tốt nếu:

✅ Trigger khi mention design/UX/UI/Figma/...  
✅ Interview kỹ trước thiết kế (không vội vàng)  
✅ Tuân theo đúng 5 modes  
✅ Kiểm tra Design System trước tạo mới  
✅ Kiểm tra responsive + accessibility  
✅ Cung cấp quality checklist  
✅ Tóm tắt giả định + vấn đề cần xác nhận  
✅ Giải thích reasoning cho các quyết định  
✅ Output có structure rõ ràng  

---

## Notes

- Skill tốt nhất khi có **Figma MCP** enable (cho tích hợp trực tiếp)
- Nếu không có Figma MCP, skill vẫn hoạt động tốt (hỗ trợ design guidance)
- Test prompts trên là realistic - giống yêu cầu từ thực tế
- Bạn có thể điều chỉnh prompts để match product của mình

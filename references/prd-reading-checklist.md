# PRD Reading & Analysis Checklist

## Step 1: Tóm tắt sản phẩm

Xác định các thông tin cơ bản:

- [ ] **Tên tính năng**: Tính năng này gọi là gì?
- [ ] **Mục tiêu tính năng**: Tại sao tính năng này được tạo?
- [ ] **Đối tượng sử dụng**: Ai là primary user?
- [ ] **Vấn đề cần giải quyết**: Problem statement là gì?
- [ ] **Giá trị mang lại**: User benefit + business value là gì?
- [ ] **Phạm vi thiết kế**: Cái gì TRONG scope, cái gì NGOÀI scope?
- [ ] **Success metrics**: Làm thế nào để đo thành công?

---

## Step 2: Trích xuất yêu cầu (Requirements)

Phân loại từng yêu cầu trong PRD:

### Functional Requirements (Những gì phải làm?)
- [ ] User có thể làm hành động gì?
- [ ] System phải xử lý input nào?
- [ ] Output cần cung cấp là gì?

### Business Rules (Quy tắc kinh doanh)
- [ ] Có validation rules nào?
- [ ] Có business logic nào ảnh hưởng đến flow?
- [ ] Có dependency với feature khác không?

### User Permissions (Quyền hạn)
- [ ] Có loại user khác nhau không?
- [ ] Mỗi loại user thấy được cái gì?
- [ ] Ai có quyền làm hành động gì?

### Data Requirements (Dữ liệu)
- [ ] Dữ liệu nào cần hiển thị?
- [ ] Dữ liệu nào cần input từ user?
- [ ] Giới hạn dữ liệu (max length, format) là gì?

### Validation Rules (Xác thực)
- [ ] Required fields là gì?
- [ ] Email, phone, number format ra sao?
- [ ] Có cross-field validation không?

### Error Cases (Lỗi có thể xảy ra)
- [ ] Validation failed → error message nào?
- [ ] API error → user thấy gì?
- [ ] Timeout → user thấy gì?
- [ ] Permission denied → message nào?

### Empty Cases (Không có dữ liệu)
- [ ] List rỗng → hiển thị gì?
- [ ] No results → message nào?
- [ ] Có call-to-action gì không?

### Loading Cases (Đang tải)
- [ ] Skeleton, spinner, hay loading text?
- [ ] Loading duration có lâu không?
- [ ] Có cancel button không?

### Success Cases (Thành công)
- [ ] Hành động thành công → feedback nào?
- [ ] Confirmation needed không?
- [ ] Redirect đi đâu?

### Edge Cases (Trường hợp đặc biệt)
- [ ] Very long text → truncate hay wrap?
- [ ] Very large number → format ra sao?
- [ ] Very old/new date → xử lý sao?
- [ ] Mobile vs Desktop → khác nhau?

### Responsive Requirements
- [ ] Mobile, Tablet, Desktop có khác không?
- [ ] Priority content khác theo breakpoint không?
- [ ] Layout nào là flexible?

### Accessibility Requirements
- [ ] Có mention a11y requirement không?
- [ ] WCAG level target?
- [ ] Dark mode cần support không?
- [ ] RTL language support cần không?

---

## Step 3: Xây dựng User Flow

Xác định luồng người dùng:

### Entry Points
- [ ] User bắt đầu từ đâu?
- [ ] Có triggered by notification/email không?
- [ ] Deep link cần support không?

### Happy Path (Con đường lý tưởng)
- [ ] Step 1: User action?
- [ ] Step 2: System response?
- [ ] Step 3-N: ...
- [ ] Success: User mencapai goal?

### Alternative Paths
- [ ] Path nào khác có thể xảy ra?
- [ ] Conditional logic nào tồn tại?

### Error Paths
- [ ] Nếu validation fail → next step?
- [ ] Nếu API error → next step?
- [ ] Nếu user cancel → next step?

### Exit Points
- [ ] Success state → user đi đâu?
- [ ] Error state → user retry hay cancel?
- [ ] Incomplete state → auto-save hay discard?

### Confirmation Points
- [ ] Hành động destructive (delete, submit) cần confirm?
- [ ] Confirmation là modal, inline, hay step?

---

## Step 4: Xác định Màn hình (Screens/Pages)

Liệt kê TẤT CẢ screen/state cần thiết:

### Main Screens
- [ ] List Page / Dashboard
- [ ] Detail Page / Record View
- [ ] Create Page / New Record
- [ ] Edit Page / Record Edit
- [ ] Search / Filter Results

### State Variations
- [ ] Empty state (no data yet)
- [ ] Loading state (fetching data)
- [ ] Error state (something went wrong)
- [ ] Permission denied (access denied)
- [ ] No results (search/filter empty)

### Modal / Overlay States
- [ ] Confirmation modal (before delete/submit)
- [ ] Success modal (operation completed)
- [ ] Error modal (detailed error)
- [ ] Validation errors (inline)

### Notification / Toast
- [ ] Success notification (action completed)
- [ ] Error notification (action failed)
- [ ] Warning notification (something needs attention)
- [ ] Info notification (helpful info)

---

## Step 5: Xác định Component

Liệt kê component cần thiết:

### Existing Components (Dùng lại)
- [ ] Button (primary, secondary, tertiary)
- [ ] Input field (text, email, password, number)
- [ ] Select / Dropdown
- [ ] Checkbox / Radio
- [ ] Modal / Dialog
- [ ] Table / List
- [ ] Card
- [ ] Tabs
- [ ] Pagination
- [ ] Toast / Alert

### New Components (Cần tạo)
- [ ] Component X: Anatomy + States + Variants?
- [ ] Component Y: Anatomy + States + Variants?

### Component Properties
- [ ] Size: Small, Medium, Large?
- [ ] Variant: Primary, Secondary, Danger?
- [ ] State: Default, Hover, Active, Disabled?
- [ ] Content: Label, Icon, Badge?

---

## Step 6: Hỏi Clarifying Questions

Nếu PRD còn mơ hồ, cần hỏi:

### Về User
- [ ] Persona nào là primary?
- [ ] Skill level của user (beginner, expert)?
- [ ] Context sử dụng (mobile, desktop, both)?

### Về Data
- [ ] Sample data ra sao?
- [ ] Max/min values?
- [ ] Real data hay placeholder?

### Về Behavior
- [ ] User expectation ra sao?
- [ ] Có onboarding cần không?
- [ ] Batch action cần support không?

### Về Constraints
- [ ] Browser support?
- [ ] Performance constraint?
- [ ] Security requirement?

### Về Priority
- [ ] Cái gì là MUST HAVE?
- [ ] Cái gì là NICE TO HAVE?
- [ ] Cái gì có thể defer?

---

## Step 7: Kiểm tra lại

Trước khi bắt đầu thiết kế, kiểm tra:

- [ ] PRD clear + complete?
- [ ] Tất cả questions đã được trả lời?
- [ ] Flow logic hợp lý?
- [ ] Tất cả screens đã được xác định?
- [ ] Tất cả edge cases đã xem xét?
- [ ] Design System nào sẽ dùng?
- [ ] Components nào có sẵn?
- [ ] Components nào cần tạo mới?

---

## Output: PRD Summary Document

Sau khi đọc xong, viết tóm tắt:

```
## Feature: [Feature Name]

### Overview
[1-2 câu mô tả tính năng]

### User Goal
[Primary user goal]

### Business Value
[Why this feature matters]

### Scope
✓ In scope: [...]
✗ Out of scope: [...]

### Key Requirements
- Functional: [...]
- Business rules: [...]
- Data: [...]
- Permissions: [...]
- Validation: [...]
- Error handling: [...]
- Empty/Loading/Success states: [...]

### User Flow
1. User action → System response
2. ...
3. Success: [outcome]

### Screens Needed
- [ ] List page (empty, loading, error)
- [ ] Detail page
- [ ] Create page (validation, submit, success)
- [ ] Confirmation modal
- [ ] Success notification
- ...

### Components
- [ ] Reuse: Button, Input, Modal, Table
- [ ] Create: CustomComponent X, Y
- [ ] Variants/Properties: [...]

### Assumptions & Questions
- Assume A because [reason]
- Need clarification on B: [question]
- Alternative approach C: [reasoning]

### Success Criteria
- User dapat [goal] dalam [X] steps
- Error message jelas + actionable
- Mobile/Desktop sama-sama ok
```

---

**Tips:**
- Jangan skip step ini! Waktu defront untuk hỏi rõ = hemat waktu redesign belakangan
- Dokumentasi checklist ini membantu developer nanti implement
- Jika PRD missing something critical, list it dan discuss sebelum design

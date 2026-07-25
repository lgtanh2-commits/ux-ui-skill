# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.3.0] - 2026-07-25

### Added

#### 🎨 Creative Excellence & Design Thinking Framework
- **Design Thinking Protocol** — 4 core questions before any design (Purpose, Tone, Constraints, Differentiation)
- **Aesthetic Direction Options** — 11 distinctive directions to choose from (Brutally Minimal, Maximalist Chaos, Retro-futuristic, etc.) — commit BOLDLY instead of "neutral" design
- **"Commit Boldly" Philosophy** — after choosing direction, execute with precision (no half-measures)

#### ❌ Avoid Generic AI-Generated Aesthetics (Concrete Red Lines)
- Specific fonts to NEVER use: Inter, Roboto, Arial, Space Grotesk (AI generation favorites)
- Specific colors to NEVER use: Generic SaaS blue (#3B82F6), purple gradients on white
- Specific patterns to NEVER use: Glass morphism, Apple mimicry, cookie-cutter layouts, liquid/blob backgrounds
- Added check: "Does this look AI-generated?" → must be NO
- ✅ Alternatives: unexpected fonts, unique color pairs (Terracotta + Charcoal, Sage + Navy, Coral + Slate)

#### 📝 Typography Excellence Framework (Enhanced)
- Font selection strategy: Max 3 typefaces, but UNEXPECTED & characterful
- Font pairing logic: Category contrast (Serif + Sans), Weight contrast (Light + Bold), Personality contrast (Geometric + Humanist)
- Typographic scale with mathematical ratio (1.25x or 1.333x)
- UI typography specifics: Button (semi-bold 600, 14-16px), Labels (400, 14px above input), Input (400, 16px minimum)
- Responsive typography with CSS clamp for fluid sizing

#### 🎨 Color System Architecture (Enhanced)
- Two-role palette structure: Base/Neutral (4-5 colors) + Accent (1-3 colors)
- Warm greys vs Cool greys intentional choice
- Unique color strategy: avoid timid, evenly-distributed colors → use dominant color + SHARP accents
- Create atmosphere: gradient meshes, noise textures, layered transparencies, dramatic shadows (intentional)
- Color accessibility: contrast ≥4.5:1, don't rely on color alone

#### 🖱️ Modern Interaction Patterns (New Section)
- Direct Manipulation (drag/drop to reorder, inline editing, sliders, pinch/zoom)
- Immediate Feedback (visual, haptic, audio, loading, success, error states within 100ms)
- Conversational Interfaces (pure chat, command palette, smart search, form alternatives)
- Adaptive Layouts (time-based dark mode, device-based simplification, connection-based optimization, usage-based prioritization)
- Forgiveness & Recovery (prevention strategies, soft deletes, undo/redo, clear error messages)

#### ✅ Reorganized Forbidden vs Always-Do Lists
- **❌ STRICTLY FORBIDDEN**: Separated into Design Process, Visual Aesthetics, Component & System, Interaction & Accessibility
- **✅ ALWAYS DO**: Separated into Design Mindset, Visual Excellence, Component & System, Handoff & Documentation
- Clear, actionable guidance instead of scattered bullet points

#### 🧪 Comprehensive Testing Checklist (New Section)
- **Visual Testing** (9 items): breakpoints, touch targets, content lengths, rendering, fonts, colors, icons, images, animations, AI check
- **Accessibility Testing** (10 items): keyboard nav, screen reader, contrast, focus, semantic HTML, captions, form labels, error messages, WCAG AA
- **State & Interaction Testing** (10 items): default/hover/active/focus/disabled/loading/success/error/empty states, transitions
- **Component Testing** (9 items): reuse, auto-layout, text/icon handling, properties, instances, nested components
- **Responsive & Layout Testing** (9 items): breakpoints, reflow, scrolling, touch targets, modals, orientations, images, tables
- **Cross-Browser & Device Testing** (7 items): browsers, real devices, screen densities, OS defaults, gestures, haptics
- **Design System & Consistency Testing** (8 items): colors, typography, spacing, radius, shadows, icons, terminology
- **Performance & Load Testing** (6 items): asset optimization, font loading, animation performance, layout thrashing, lazy loading, page weight
- **Uniqueness Check** (6 items): ⭐ distinctive fonts, unique palette, unexpected layout, committed direction, no generic patterns

### Context

Merged insights from **Bencium Innovative UX Designer** skill to elevate design thinking from "avoid generic" to "commit boldly to distinctive aesthetic". Inspired by successful modern design studios and creative agencies.

Key realization: Generic AI designs fail because they lack intentional aesthetic direction. Adding "Design Thinking Protocol" + "Aesthetic Direction Options" + "Concrete Red Lines" transforms designers from reactive (avoiding bad) to proactive (committing bold).

### Breaking Changes
None — all additions are backward compatible with v1.2.0 approaches.

---

## [1.2.0] - 2026-07-24

### Added
- 🧩 "Kiểm tra sức khỏe component có sẵn" — khi tái sử dụng/nest 1 component có sẵn (vd icon set) làm phần tử con của component mới, set thử 1 property trên 1 instance bất kỳ của nó TRƯỚC. Component có sẵn lỗi cấu trúc từ trước (vd variant đặt tên sai định dạng) có thể chặn property của toàn bộ instance dùng nó trong FILE, kể cả component mới hoàn toàn không liên quan.
- 📐 "FILL chỉ có ý nghĩa khi parent đang FIXED width" — dùng FILL bên trong 1 parent đang HUG cho kích thước không xác định/sai. Ghi rõ cách chọn HUG-root/FIXED-inner hay ngược lại tuỳ nhu cầu co giãn.
- 📝 Ghi chú giới hạn: text node có thể không set được layoutSizingHorizontal/Vertical trực tiếp qua 1 số MCP tool — workaround bọc frame hoặc dùng width cố định.
- ⚠️ "Tool trả 'thành công' không đồng nghĩa giá trị đúng" — luôn get_node_info lại để xác minh sau các thao tác mutate quan trọng (đặc biệt sau reparent, instance-swap).
- 🧭 "Auto Layout bỏ qua x/y khi tạo/move node mới" — node luôn bị đẩy về cuối danh sách con theo layout flow; cách chèn đúng vị trí bằng reparent lại sibling liền kề.
- ⏱️ "Giới hạn batch tool-call" — chia nhỏ theo nhóm (3-8 lệnh), verify lại sau mỗi nhóm thay vì tin 1 batch lớn (~20+ lệnh) dễ timeout/thất bại âm thầm từng phần.
- 📄 "File nhiều page" — get_document_info/get_selection chỉ phản ánh page đang mở trên UI của user; xác nhận chuyển tab bằng cách nhờ user click chọn 1 layer rồi đọc get_selection.

### Context
Rút ra từ phiên build component library (Input Field 7-state + Toast 3-state) qua Figma MCP bridge — gặp: component "Field Icon" có sẵn trong file bị lỗi cấu trúc từ trước khiến toàn bộ property của mọi instance dùng nó (kể cả component mới không liên quan) bị chặn; Toast co sai kích thước do FILL trong parent HUG; icon-swap phải bỏ property INSTANCE_SWAP giữa chừng do không ổn định; batch 26 lệnh song song timeout hàng loạt.

---

## [1.1.0] - 2026-07-22

### Added
- 🧪 "Kiểm tra giới hạn công cụ trước khi build" — bước xác minh khả năng thật của MCP/plugin Figma đang dùng (Paint/Text Style thật, alpha/opacity, xoá component property, xoá layer con mặc định, ẩn phần tử trong Auto Layout) trước khi build hàng loạt component. Báo giới hạn cho user ngay từ đầu, không đợi đến báo cáo cuối.
- 📏 "Layout Token (Content Width)" — chốt 1 con số content-width chuẩn cho khu vực nội dung (form/card) áp dụng thống nhất cho mọi component liên quan, tránh lệch mép giữa input/button/alert khi ráp chung màn hình.
- ✅ Bước "test property ngay sau khi build" trong Build Component Mode: tạo instance test, toggle từng property (boolean/variant/instance-swap) ngay sau khi build xong 1 component, không dồn lại test ở cuối.
- ✅ 2 mục mới trong Quality Checklist (Component): đã test toggle property trên instance thật chưa, các component chung khu vực có cùng content width không.
- 💭 Tách "nội dung tự bịa" ra khỏi mục "Giả định" chung — đánh dấu riêng, nổi bật hơn để dễ bắt và sửa ngay.
- ❓ Thêm mục "Giới hạn công cụ phát sinh trong lúc build" vào "Cần xác nhận".

### Context
Rút ra từ 1 phiên build thật (component library + rebuild 9 màn hình "Quên mật khẩu" trên Figma qua MCP bridge) — phát hiện nhiều bug chỉ lộ ra sau khi user review bằng mắt (Error text không wrap, ẩn icon làm cả instance render trắng, input box lệch 20px so với button do padding ẩn). Các mục thêm ở bản này nhằm bắt các lớp lỗi đó sớm hơn, ở giai đoạn build thay vì giai đoạn review.

---

## [1.0.0] - 2026-07-22

### Added
- ✨ Initial release of UX/UI Design Skill
- 🎨 5 distinct operating modes:
  - Design Screen Mode (from PRD to high-fidelity UI)
  - Build Component Mode (create/improve design system components)
  - Audit Mode (review existing designs)
  - Edit Mode (targeted design modifications)
  - PRD to UI Mode (full end-to-end process)
- 📋 Comprehensive SKILL.md with detailed guidelines
- 📚 Reference files:
  - Design System Foundation template
  - PRD Reading & Analysis Checklist
- 🔧 Figma MCP integration support
- ✅ Quality checklist (responsive, accessibility, consistency)
- 📖 Complete documentation in Vietnamese
- 🧪 Test prompts for validating skill behavior
- 🎯 Interview-first design approach
- 🌐 Design System prioritization (reuse > create new)

### Features
- Senior Product Designer mindset
- Systematic requirements analysis
- UX principles and best practices
- WCAG accessibility guidelines
- Developer handoff standards
- Component library best practices
- Responsive design approach
- Semantic token-based design system

### Documentation
- SKILL.md: Main skill instructions (490 lines)
- README.md: Overview and quick start
- design-system-foundation.md: DS template (300+ lines)
- prd-reading-checklist.md: PRD analysis guide (350+ lines)
- TEST_PROMPTS.md: Test cases and validation
- LICENSE: MIT license
- CHANGELOG.md: Version history

### Language
- Vietnamese (Tiếng Việt)
- Professional product design terminology

---

## Future Roadmap

### v1.4 (Planned)
- [ ] Animation timing & easing specifications (motion spec framework)
- [ ] Micro-interaction patterns & state machine diagrams
- [ ] Dark mode design guidelines & implementation
- [ ] Design pattern library (card layouts, form patterns, data visualization)

### v1.5 (Planned)
- [ ] Component library examples (real Figma files)
- [ ] Design tokens export templates (JSON/CSS/TS formats)
- [ ] Figma plugin integration guide (advanced MCP patterns)
- [ ] Accessibility audit checklist (WCAG AAA aspirational)

### v2.0 (Planned)
- [ ] Interactive design decision tree
- [ ] Figma template file with aesthetic examples
- [ ] Video tutorials (Design Thinking Protocol walkthrough)
- [ ] Live design system examples (multiple aesthetic directions)

---

## How to Contribute

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Commit with clear messages (`git commit -m 'Add: new feature'`)
5. Push to the branch (`git push origin feature/improvement`)
6. Open a Pull Request

---

## Support

For questions, issues, or suggestions:
- Open an issue on GitHub
- Contact: [your contact info]

---

## Author

**Tâm Anh (Lương Tâm Anh)**
- Product Manager / Business Analyst at QTS (Quang Truong Solutions)
- CCBA Certified
- Specializes in: Product Design, Design Systems, Figma, nexWallet Platform

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Last Updated**: 2026-07-25  
**Current Version**: 1.3.0  
**Maintainer**: Tâm Anh

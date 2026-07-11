# Catalog — Tài nguyên QLDA Xây lắp & PMP/PMI trên GitHub (đã fact-check)

> Kiểm chứng ngày **2026-07-11**. Số sao/ngày cập nhật có thể đã thay đổi — bấm link để xem realtime.
> Cột **Còn bảo trì?** là tiêu chí quan trọng nhất cho yêu cầu "được vá lỗi liên tục".

---

## 1) Skills chuyên ngành XÂY DỰNG (đúng trọng tâm nhất)

### ⭐ dleerdefi/claude-code-construction
- **Link:** https://github.com/dleerdefi/claude-code-construction
- **Loại:** Claude Code skills (Python + SKILL) cho dân xây dựng / quản lý thi công
- **License:** MIT ✅ (được vendor/sửa/thương mại, giữ attribution)
- **Sao:** ~19 · **Ngôn ngữ:** Python 95%
- **Còn bảo trì?** Nhỏ, cộng đồng — theo dõi commit trước khi phụ thuộc
- **9 skill:** `/project-setup`, `/sheet-splitter` (tách bộ bản vẽ PDF), `/spec-splitter` (tách chương spec), `/schedule-extractor` (xuất bảng cửa/hoàn thiện/panel ra Excel), `/submittal-log-generator` (lập sổ submittal từ spec), `/bid-tabulator` (so sánh báo giá thầu phụ), `/bid-evaluator` (chấm điểm rủi ro/thiếu scope), `/code-researcher` (tra mã/tiêu chuẩn xây dựng), `/subcontract-writer` (soạn hợp đồng thầu phụ)
- **Use case hiệu quả:** Bóc tách hồ sơ thầu, lập submittal log, so sánh & đánh giá báo giá thầu phụ, soạn hợp đồng thầu phụ theo scope. Rất hợp vai Tổng thầu / QS / hồ sơ thầu.
- **Cảnh báo:** Skill tra "building codes" mặc định theo **tiêu chuẩn Mỹ**; với VN cần bổ sung QCVN/TCVN. Repo còn nhỏ, hãy tự test trước khi dùng cho hồ sơ chính thức.

---

## 2) MCP server cho LẬP TIẾN ĐỘ / CONTROLS (Primavera P6)

### ⭐ osama-ata/p6xer-mcp-server
- **Link:** https://github.com/osama-ata/p6xer-mcp-server
- **Loại:** MCP server đọc/phân tích file **Primavera P6 `.xer`**
- **License:** MIT ✅
- **Sao:** ~9 · **CHANGELOG.md** có (đánh version)
- **Còn bảo trì?** Mới, quy mô nhỏ nhưng có changelog — kiểm tra commit gần nhất
- **Chạy được với:** Claude Desktop, Claude Code, Cursor. Cài nhanh: `claude mcp add p6xer -- uvx p6xer-mcp-server`
- **13 tool:** `parse_xer_file`, `get_project_activities`, `get_critical_path`, `analyze_resource_utilization`, `check_schedule_quality` (kiểm tra **DCMA 14-point**), `get_resources`, `get_resource_assignments`, WBS, quan hệ, lịch, EVM…
- **Use case hiệu quả:** Hỏi Claude "đường găng của tiến độ này?", "chất lượng schedule theo DCMA?", "tài nguyên chỗ nào quá tải?" ngay trên file P6 `.xer` — cực hợp Planning Engineer / Project Controls.
- **Cảnh báo:** Chỉ đọc `.xer` (không ghi ngược P6). Không hỗ trợ trực tiếp MS Project `.mpp`.

> **Ghi chú:** Chưa tìm thấy MCP server ổn định chuyên cho **MS Project `.mpp`**. Với MS Project, dùng skill nội bộ `construction-planner-mep` (xuất XML → .mpp) hoặc thư viện Python `mpxj`.

---

## 3) Bộ Skills QLDA tổng quát (Agile/Jira) — repo lớn, bảo trì tốt

### ⭐ alirezarezvani/claude-skills
- **Link:** https://github.com/alirezarezvani/claude-skills · thư mục [`project-management`](https://github.com/alirezarezvani/claude-skills/tree/main/project-management)
- **License:** MIT ✅
- **Sao:** ~22.1k · **Bản mới:** v2.9.0 (28/05/2026) · **1.228 commit**
- **Còn bảo trì?** ✅ **Rất tích cực** (semantic versioning, PR liên tục) — đáp ứng tốt yêu cầu "vá lỗi liên tục"
- **Skill PM:** Senior Project Manager, Scrum Master, Jira Expert (JQL), Confluence Expert, Atlassian Admin, Template Creator. Tích hợp Jira/Confluence qua MCP.
- **Use case hiệu quả:** QLDA phần mềm/Agile, tự động hoá Jira/Confluence, báo cáo sprint.
- **Cảnh báo:** **KHÔNG chuyên xây dựng, KHÔNG theo PMBOK/waterfall.** Nghiêng về Agile & SaaS. Lấy làm khung skill/quy ước SKILL.md để tự viết skill xây dựng thì tốt; đừng kỳ vọng nội dung xây lắp. Là mega-repo tổng hợp — kiểm license từng phần con nếu vendor.

### phuryn/pm-skills
- **Link:** https://github.com/phuryn/pm-skills — "PM Skills Marketplace 100+ skills" (discovery→strategy→execution→launch→growth). Thiên về **Product Management**, không phải xây dựng. Dùng tham khảo cấu trúc skill.

---

## 4) Template PMP / PMI / PMBOK dạng Markdown

### ⭐ jerzydziewierz/PMBOK-doc-templates
- **Link (GitHub):** https://github.com/jerzydziewierz/PMBOK-doc-templates
- **Bản còn cập nhật (Codeberg):** https://codeberg.org/greycodes/PMBOK-doc-templates
- **Loại:** ~58 template tài liệu theo **PMBOK Guide 6th** (markdown): Business Docs, 10 Knowledge Areas (Integration, Scope, Schedule, Cost, Quality, Resources, Communications, Risk, Procurement, Stakeholder), Management Plans, Project Documents.
- **License:** **Modified Apache-2.0** ✅ (kiểm tra điều khoản sửa đổi trong repo trước khi thương mại hoá)
- **Sao:** ~25 · **v1.0:** 11/01/2026
- **Còn bảo trì?** ⚠️ **ĐÃ ARCHIVE trên GitHub (12/03/2026 — read-only).** Đã migrate sang **Codeberg** → muốn "vá lỗi liên tục" thì theo dõi bản Codeberg.
- **Use case hiệu quả:** Khởi tạo bộ hồ sơ QLDA chuẩn PMI (Project Charter, PM Plan, Risk/Scope/Schedule plan…) để điền cho dự án thực.

### bradleysawler/project_management_notes
- **Link:** https://github.com/bradleysawler/project_management_notes
- **Loại:** Sơ đồ quy trình / Inputs–Outputs PMBOK **5th** dạng markdown phẳng (hợp Obsidian). Dùng học/ôn PMP, tra process flow.

### jkuharev/project-management
- **Link:** https://github.com/jkuharev/project-management — có **PMP Cheat Sheet** cho PMBOK 5 & 6.

---

## 5) Awesome-lists (để tự đào sâu — chỉ dẫn link, không copy)

| Repo | Ghi chú |
|---|---|
| [anthropics/skills](https://github.com/anthropics/skills) | **Chính chủ Anthropic** — chuẩn viết Skill, bảo trì tốt. Nền tảng để tự viết skill xây dựng. |
| [VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills) | 1000+ skill từ official teams + cộng đồng |
| [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) | 1000+ skill/plugin production-ready |
| [travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) · [karanb192/awesome-claude-skills](https://github.com/karanb192/awesome-claude-skills) | Danh sách tuyển chọn, actively maintained |

---

## Bảng tổng hợp nhanh (fact-check)

| Repo | Loại | License | Sao | Cập nhật | Còn bảo trì? | Hợp xây dựng/PMP? |
|---|---|---|---|---|---|---|
| dleerdefi/claude-code-construction | Skills | MIT | ~19 | — | Nhỏ/cộng đồng | ✅ Xây dựng (US codes) |
| osama-ata/p6xer-mcp-server | MCP P6 | MIT | ~9 | có changelog | Mới, nhỏ | ✅ Tiến độ P6 |
| alirezarezvani/claude-skills | Skills PM | MIT | ~22.1k | 05/2026 | ✅ Rất tốt | ❌ Agile, không xây dựng |
| jerzydziewierz/PMBOK-doc-templates | Template MD | Apache-2.0* | ~25 | 01/2026 | ⚠️ Archived→Codeberg | ✅ PMBOK 6 |
| bradleysawler/project_management_notes | Notes MD | (xem repo) | — | — | — | ✅ PMBOK 5 |
| anthropics/skills | Chuẩn/Skills | (xem repo) | lớn | thường xuyên | ✅ Official | Nền tảng tự viết |

\* Modified Apache-2.0 — đọc kỹ điều khoản sửa đổi.

---
*Nguồn tìm kiếm & kiểm chứng qua GitHub + web search, 2026-07-11.*

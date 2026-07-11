# Nguồn & Attribution — claude-code-construction

- **Repo gốc:** https://github.com/dleerdefi/claude-code-construction
- **Tác giả:** dleerdefi
- **License:** MIT (xem file `LICENSE` kèm theo — bản gốc, giữ nguyên)
- **Lấy về (vendored):** 2026-07-11, clone `--depth 1` nhánh mặc định
- **Nội dung vendor:** thư mục `.claude/skills/` gốc (13 skill SKILL.md) + `CLAUDE.md`

## 13 skill kèm theo
`bid-evaluator`, `bid-tabulator`, `code-researcher`, `pe-review`, `project-setup`,
`rfi-drafter`, `schedule-extractor`, `sheet-splitter`, `spec-splitter`,
`subcontract-writer`, `submittal-log-generator`, `tag-audit-and-takeoff`,
`viewport-highlighter`.

> Phần Python tools/scripts KHÔNG được vendor — clone repo gốc nếu cần chạy đầy đủ.

## ⚠️ Điều chỉnh cho Việt Nam
Skill `code-researcher` mặc định tra **building codes của Mỹ**. Với dự án VN cần thay bằng
**QCVN / TCVN** và hồ sơ ràng buộc dự án. Không dùng nguyên si cho hồ sơ pháp lý chính thức
mà chưa rà soát.

## Cách dùng
Copy thư mục skill vào `.claude/skills/` trong project của bạn, hoặc trỏ Claude Code tới đây.
Theo giấy phép MIT: được sửa/thương mại hoá, chỉ cần giữ thông báo bản quyền.

# Project "PMP SKILL" — Bộ khởi tạo Claude Project

Thư mục này chứa mọi thứ để dựng một **Claude Project** tên **"PMP SKILL"** gộp toàn bộ skill
quản lý dự án xây lắp & MEP.

## Cách tạo Project trên claude.ai (thủ công, 5 phút)

1. Vào **claude.ai** → menu trái **Projects** → **Create project**.
2. Tên: **PMP SKILL**. Mô tả: *"Trợ lý QLDA xây lắp & MEP VN theo PMP/PMI."*
3. Mở **Set instructions** (hoặc "Add instructions") → **dán toàn bộ nội dung**
   [`INSTRUCTION.md`](INSTRUCTION.md).
4. Mở **Add content / Knowledge** → **upload** các file SKILL.md theo checklist dưới.
5. Xong. Mở một chat trong Project và thử lệnh mẫu ở cuối.

## Checklist file upload vào Knowledge

Từ repo **blue-tuan** (public):
- [ ] `skills/qlda-xaylap-vn/SKILL.md` ← skill điều phối chính
- [ ] 13 file `skills/claude-code-construction/*/SKILL.md`
- [ ] Vài template `templates-pmbok/PMBOK-templates/` (Project charter, PM Plans, Risk/Scope/Schedule)
- [ ] `mcp/README.md`

Từ repo **test** (private — file gốc của bạn):
- [ ] `Planner Skill/construction-planner-mep/SKILL.md`
- [ ] `AI KHỐI LƯỢNG M&E/.../me-takeoff-mep_source/SKILL.md`
- [ ] `QS Skill/SKILL.md` + `QS Skill/skills/qs-*/SKILL.md` (11 file)
- [ ] `QAQC SKILL/SKILL.md`
- [ ] `Filling Doc/` semantic-data-entry

> **Lưu ý riêng tư:** các skill trong repo `test` là file riêng của bạn — upload trực tiếp
> vào Project (không cần đưa lên repo public). Nếu Project giới hạn dung lượng, ưu tiên các
> SKILL.md; scripts/references tải sau khi cần.

## Lệnh mẫu để test sau khi tạo Project
- *"Lập WBS + kế hoạch tổng thể cho dự án tòa A, 25 tầng; tôi đính kèm hợp đồng + BOQ."*
- *"Lập tiến độ HT & MEP cuốn chiếu 3 tầng/cụm, khởi công 01/08/2026, xuất Excel + MS Project XML."*
- *"Kiểm tra mốc phạt tiến độ theo hợp đồng đính kèm và tính float tới từng mốc."*
- *"So sánh 3 báo giá thầu phụ điện đính kèm, chấm điểm rủi ro & thiếu scope."*
- *"Lập Material Submittal cho cáp CU/XLPE theo spec + danh sách vendor đính kèm."*

Mỗi lệnh, trợ lý sẽ tự **định tuyến** sang skill phù hợp theo bảng trong INSTRUCTION.

---
name: qlda-xaylap-vn
description: >
  Trợ lý Quản lý dự án xây lắp Việt Nam theo chuẩn PMP/PMI kết hợp thực tiễn
  công trường VN (QCVN/TCVN, hợp đồng FIDIC/Nghị định VN). Hỗ trợ lập WBS, tiến độ
  cuốn chiếu theo tầng, đường găng (CPM), mốc phạt tiến độ, đường cong S, quản lý
  rủi ro, nghiệm thu & thanh toán. Kích hoạt khi người dùng nói 'quản lý dự án xây
  dựng', 'lập kế hoạch thi công', 'tiến độ xây lắp', 'WBS', 'mốc phạt', 'cuốn chiếu
  theo tầng', 'PMP', 'PMI', 'PMBOK cho xây dựng'.
argument-hint: "[loại-công-việc: wbs | tien-do | rui-ro | mốc-phạt | thanh-toan]"
---

# Quản lý dự án Xây lắp Việt Nam (PMP/PMI + thực tiễn VN)

Trợ lý này giúp **Chỉ huy trưởng / PM / Planning Engineer** của Tổng thầu hoặc Nhà thầu
lập và kiểm soát dự án xây dựng nhà cao tầng tại Việt Nam. Kết hợp:

- **Khung PMBOK/PMI** (10 knowledge areas, 5 process groups) — tính hệ thống, chuẩn hoá.
- **Thực tiễn công trường VN** — cuốn chiếu theo tầng, phối hợp Xây–Tô–MEP, mốc phạt,
  nghiệm thu theo QCVN/TCVN, thanh toán theo hợp đồng nhiều bên (CĐT/NTP/NCC).

> **Luật nền: KHÔNG bịa số.** Mọi con số (khối lượng, đơn giá, năng suất, ngày) phải lấy
> từ **hợp đồng / BOQ / bản vẽ / định mức** người dùng cung cấp. Nếu thiếu, hỏi hoặc ghi
> rõ giả định `[GIẢ ĐỊNH]` — tuyệt đối không điền số "trông hợp lý".

## Thứ tự viện dẫn (khi có mâu thuẫn)
1. **Hồ sơ ràng buộc dự án**: Hợp đồng, PLHĐ, Spec kỹ thuật, bản vẽ, quy trình phối hợp.
2. **Pháp luật VN**: Luật Xây dựng, các Nghị định/Thông tư, **QCVN**, **TCVN**.
3. **Tiêu chuẩn quốc tế** (khi hồ sơ cho phép áp dụng): FIDIC, ACI, BS, ASTM…
4. **PMBOK/PMI**: dùng cho phương pháp luận quản lý, không thay thế hồ sơ pháp lý.

---

## Định tuyến theo yêu cầu

| Người dùng cần | Vào mục |
|---|---|
| Phân rã công việc | [1. WBS](#1-wbs--phân-rã-công-việc) |
| Lập tiến độ, đường găng | [2. Tiến độ CPM & cuốn chiếu](#2-tiến-độ-cpm--cuốn-chiếu-theo-tầng) |
| Kiểm mốc phạt hợp đồng | [3. Mốc & phạt tiến độ](#3-mốc--phạt-tiến-độ) |
| Đường cong S, kiểm soát | [4. Đường cong S & EVM](#4-đường-cong-s--kiểm-soát-evm) |
| Rủi ro | [5. Quản lý rủi ro](#5-quản-lý-rủi-ro) |
| Nghiệm thu & thanh toán | [6. Nghiệm thu & thanh toán](#6-nghiệm-thu--thanh-toán) |

Với các tác vụ chuyên sâu (bóc khối lượng, lập tiến độ MS Project, hồ sơ QA/QC, dự toán),
hãy dùng các skill chuyên ngành có sẵn: `construction-planner-mep`, `me-takeoff-mep`,
`iqc-mep-qaqc`, `qs-mep`.

---

## 1. WBS — Phân rã công việc

Phân rã theo **cấu trúc chuẩn cho nhà cao tầng VN**:

```
Dự án
├─ 1. Chuẩn bị (huy động, lán trại, điện nước tạm, biện pháp)
├─ 2. Phần ngầm (cọc → đào đất → đài/giằng → hầm → chống thấm)
├─ 3. Phần thân (kết cấu BTCT theo tầng: cột/vách → dầm/sàn)
├─ 4. Phần hoàn thiện (xây → tô → chống thấm → ốp lát → sơn → trần)
├─ 5. Cơ điện MEP (điện, cấp thoát nước, HVAC, PCCC, ELV)
├─ 6. Hạ tầng & cảnh quan
└─ 7. Nghiệm thu, chạy thử, bàn giao (T&C, hồ sơ hoàn công)
```

**Nguyên tắc:**
- Mỗi gói công việc (work package) phải **đo được, giao được cho 1 tổ/đội, gắn được chi phí**.
- Với phần thân & hoàn thiện: phân rã **theo tầng** để phục vụ cuốn chiếu.
- Gắn mã WBS thống nhất với BOQ và mã chi phí (cost code) để tổng hợp EVM về sau.

---

## 2. Tiến độ CPM & cuốn chiếu theo tầng

### Logic cuốn chiếu (repetitive / line-of-balance)
Nhà cao tầng thi công lặp theo tầng. Mỗi tầng đi qua chuỗi:
```
Kết cấu tầng N → Xây tầng N → Tô tầng N → MEP đi ngầm → Hoàn thiện → MEP hoàn thiện
```
Trong khi tầng N làm hoàn thiện thì tầng N+1 đã làm kết cấu → **các tổ đội chạy song song
lệch tầng** (đội hình cuốn chiếu). Đây là chìa khoá rút ngắn tổng tiến độ.

### Các lag/ràng buộc kỹ thuật BẮT BUỘC (theo thực tiễn & QCVN/TCVN)
> Con số dưới đây là **mặc định thực tiễn phổ biến** — luôn ưu tiên giá trị trong
> **Spec/quy trình phối hợp của dự án**. Nếu dự án quy định khác, dùng theo dự án.

| Ràng buộc | Lag mặc định | Lý do |
|---|---|---|
| Tháo cốp pha sàn (không chống lại) | theo cường độ bê tông đạt (TCVN 4453) | an toàn kết cấu |
| Xây tường → tô trát | **≥ 48h** | khối xây ổn định, vữa ninh kết |
| Tô trát → sơn/ốp | ẩm độ tường đạt yêu cầu | tránh bong, phồng |
| MEP âm tường ↔ tô trát | phối hợp trước khi tô | tránh đục phá |
| Bê tông → chất tải thi công | theo cường độ đạt (%) | TCVN 4453 |

### Cách lập
1. Xác định **số tầng, chu kỳ tầng (floor cycle)** từ hợp đồng/BOQ và năng lực đội.
2. Lập mạng CPM cho **1 tầng điển hình** → nhân bản + gán lag lệch tầng.
3. Xác định **đường găng (critical path)**: chuỗi công việc float = 0.
4. Kiểm tra ràng buộc mặt bằng, cẩu tháp, vận thăng (tài nguyên chia sẻ → nút thắt).
5. Xuất Gantt + đánh dấu critical path.

**Công cụ:** dùng skill `construction-planner-mep` để xuất Excel Gantt và file MS Project
(XML → .mpp), hoặc MCP `p6xer` để phân tích file Primavera `.xer`.

---

## 3. Mốc & phạt tiến độ

**Quy trình bắt buộc:**
1. Trích từ **hợp đồng/PLHĐ** toàn bộ **mốc hợp đồng (contractual milestones)**: ngày khởi
   công, các mốc trung gian (top-out kết cấu, bao che, đóng điện…), ngày hoàn thành.
2. Đọc **điều khoản phạt**: mức phạt/ngày chậm, **trần phạt** (thường % giá trị hợp đồng
   theo Luật Xây dựng / hợp đồng), điều kiện gia hạn (EOT).
3. Map mốc hợp đồng vào tiến độ CPM → tính **float tới từng mốc**.
4. Cảnh báo mốc có float thấp/âm và **ước lượng rủi ro tiền phạt** = số ngày chậm dự kiến ×
   mức phạt/ngày (không vượt trần).
5. Liệt kê **cơ sở xin EOT** hợp lệ (thay đổi thiết kế, chậm mặt bằng của CĐT, bất khả
   kháng…) để bảo vệ nhà thầu.

> ⚠️ Không tự "chế" mức phạt. Trích đúng con số & điều khoản trong hợp đồng; nếu không có
> trong hồ sơ, ghi `[CẦN BỔ SUNG: điều khoản phạt từ hợp đồng]`.

---

## 4. Đường cong S & kiểm soát (EVM)

- **Đường cong S kế hoạch (Planned Value)**: phân bổ giá trị/khối lượng theo thời gian từ
  tiến độ đã duyệt → vẽ luỹ kế.
- Theo dõi định kỳ: **EV (giá trị đạt được)**, **AC (chi phí thực)**.
- Chỉ số: **SPI = EV/PV** (tiến độ), **CPI = EV/AC** (chi phí). SPI/CPI < 1 → cảnh báo.
- Dự báo: **EAC = BAC/CPI** (ước tính chi phí khi hoàn thành).

Trình bày kết quả kèm **nhãn nguồn số liệu** (từ báo cáo khối lượng nào, kỳ nào).

---

## 5. Quản lý rủi ro

Lập **Risk Register** theo PMI, ưu tiên rủi ro đặc thù VN:

| Nhóm | Ví dụ rủi ro | Ứng phó |
|---|---|---|
| Mặt bằng/pháp lý | Chậm bàn giao mặt bằng của CĐT | căn cứ EOT, văn bản kịp thời |
| Thời tiết | Mùa mưa ảnh hưởng đổ bê tông, hoàn thiện ngoài | bố trí công tác che chắn |
| Vật tư | Biến động giá thép/xi măng, chậm cung ứng | kế hoạch mua sắm sớm, chốt giá |
| Nhân lực | Thiếu tổ đội cao điểm, sau Tết | dự phòng đội, san tải |
| Phối hợp | Xung đột MEP–kết cấu (đục phá) | shop drawing & phối hợp trước khi tô |
| Nghiệm thu | Trượt mốc do chờ TVGS/CĐT | lịch nghiệm thu đặt trước |

Mỗi rủi ro: **xác suất × mức độ = mức ưu tiên**, gắn người chịu trách nhiệm & mốc rà soát.

---

## 6. Nghiệm thu & thanh toán

**Nghiệm thu:** theo trình tự công việc → bộ phận → giai đoạn → hoàn thành (Nghị định về
quản lý chất lượng & bảo trì công trình). Mỗi bước cần **ITP/checklist + biên bản** đúng
QCVN/TCVN áp dụng. Dùng skill `iqc-mep-qaqc` cho hồ sơ QA/QC MEP.

**Thanh toán:** lập **bảng giá trị hoàn thành** theo BOQ đã nghiệm thu, đối chiếu điều khoản
tạm ứng/giữ lại (retention)/kỳ thanh toán trong hợp đồng. Đa bên: CĐT ↔ Tổng thầu ↔ NTP ↔
NCC — mỗi luồng có bill riêng. Dùng skill `qs-mep` cho dự toán/bill/cash flow.

---

## Checklist khi khởi tạo dự án mới

- [ ] Thu thập: Hợp đồng + PLHĐ, BOQ, bản vẽ, Spec, quy trình phối hợp, tiến độ hợp đồng.
- [ ] Lập WBS gắn mã BOQ/cost code.
- [ ] Trích mốc hợp đồng + điều khoản phạt/EOT.
- [ ] Lập CPM 1 tầng điển hình → cuốn chiếu → đường găng.
- [ ] Vẽ đường cong S kế hoạch.
- [ ] Lập Risk Register.
- [ ] Thiết lập nhịp báo cáo (tuần/tháng) + chỉ số SPI/CPI.

---
*Skill do blue-tuan biên soạn (thuần Việt), 2026-07-11. Dựa trên khung PMBOK/PMI + thực tiễn
công trường VN. Không thay thế hồ sơ hợp đồng và quy chuẩn pháp lý — luôn viện dẫn hồ sơ dự án.*

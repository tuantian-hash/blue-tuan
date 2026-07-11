# MCP Servers cho Quản lý dự án Xây dựng

MCP (Model Context Protocol) server giúp Claude Desktop / Claude Code đọc & phân tích
dữ liệu chuyên ngành. Dưới đây là server đã fact-check cho lĩnh vực tiến độ/controls.

---

## p6xer-mcp-server — Phân tích tiến độ Primavera P6 (.xer)

- **Repo:** https://github.com/osama-ata/p6xer-mcp-server
- **License:** MIT ✅ · dựa trên thư viện `PyP6XER`
- **Chạy được:** Claude Desktop, Claude Code, Cursor

### Cài đặt (Claude Code)
```bash
claude mcp add p6xer -- uvx p6xer-mcp-server
```

### Cấu hình Claude Desktop (`claude_desktop_config.json`)
```json
{
  "mcpServers": {
    "p6xer": {
      "command": "uvx",
      "args": ["p6xer-mcp-server"]
    }
  }
}
```

### 13 tool chính
`parse_xer_file`, `get_project_activities`, `get_critical_path`,
`analyze_resource_utilization`, `check_schedule_quality` (DCMA 14-point),
`get_resources`, `get_resource_assignments`, WBS, quan hệ, lịch, EVM, chi tiết activity.

### Use case
> "Đọc file `.xer` này, cho tôi đường găng và các activity float âm."
> "Chấm chất lượng tiến độ theo DCMA 14-point."
> "Tài nguyên nào bị quá tải tuần này?"

### Giới hạn
- Chỉ **đọc** `.xer` (không ghi ngược vào P6).
- **Không** hỗ trợ MS Project `.mpp` trực tiếp.

---

## Ghi chú: MS Project (.mpp)
Chưa có MCP server ổn định chuyên `.mpp`. Lựa chọn thay thế:
- Skill nội bộ `construction-planner-mep` (lập tiến độ CPM → xuất XML → chuyển `.mpp`).
- Thư viện Python **`mpxj`** (đọc/ghi MPP/MPX/XER/P6) để tự viết tool.

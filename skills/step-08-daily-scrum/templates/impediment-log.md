---
artifact_name: Scrum Master Impediment Log
purpose: Provide a flat, Excel-friendly tracking table for the Scrum Master to log, monitor, and resolve impediments surfaced during the Daily Scrum or throughout the Sprint, ensuring maximum transparency and accountability.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When generating or updating the Impediment Log, the AI Agent MUST adhere to these rules:
1.  **Format:** Output ONLY a standard Markdown table. Do not use nested lists or complex formatting inside the table cells to ensure it remains 100% copy-paste compatible with Microsoft Excel or Google Sheets.
2.  **Impediment Definition:** Only log true impediments (external blockers outside the Developers' direct control). Do not log standard technical challenges.
3.  **Required Fields:** Ensure every logged item has an Owner, an Impact assessment (relative to the Sprint Goal), a Target Resolution Date, and a Days Open count.
4.  **Days Open Calculation:** 
    *   If Status is **Open**: `Days Open` = Current Date - Date Raised.
    *   If Status is **Resolved**: `Days Open` = Date Resolved - Date Raised.
    *   If `Days Open` exceeds the Sprint length (e.g., > 10 days for a 2-week sprint), prepended a critical warning flag: `⚠️ [N] days`.
5.  **Escalation Guidance:** If "Escalated?" is marked "Yes", the SM must specify the target authority (e.g., "Yes (To CTO)", "Yes (To Head of DevOps)") to ensure accountability rather than a simple binary marker.
6.  **Output Generation:** Output ONLY the section below the horizontal rule. If new impediments are logged, append them as new rows to the table.

---

# 🚧 SPRINT IMPEDIMENT LOG

**⚠️ LƯU Ý DÀNH CHO SCRUM MASTER:**
*Bảng theo dõi này nhằm mục đích làm minh bạch hóa (Transparency) các rào cản. Các rào cản cần được giải quyết càng nhanh càng tốt để bảo vệ **Sprint Goal**. Quét khối bảng dưới đây và dán trực tiếp vào Excel/Sheets nếu cần thao tác lọc (filter) hoặc làm báo cáo.*

| ID | Date Raised | Impediment Description | Affected (PBI / Person) | Sprint Goal Impact | Owner | Target Date | Escalated? | Days Open | Status | Resolution Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| *IMP-01* | *[YYYY-MM-DD]* | *[Vd: Vendor Kambi chưa cấp Test API Keys]* | *PBI #102 / Toàn bộ Devs* | *[Vd: Không thể test luồng thanh toán, nguy cơ tạch Sprint Goal]* | *[Tên SM/PO]* | *[YYYY-MM-DD]* | *Yes (Kambi Support)* | *0* | **Open** | *Đã gửi email hối thúc Vendor lúc 9h sáng.* |
| *IMP-02* | *[YYYY-MM-DD]* | *[Mô tả rào cản, từ đâu ra, tại sao]* | *[Tên Dev hoặc ID Thẻ]* | *[Hậu quả nếu không giải quyết]* | *[Tên Người xử lý]* | *[Hạn chót cần giải quyết]* | *No* | *3* | **Resolved** | *Đã cấp đủ quyền truy cập DB.* |

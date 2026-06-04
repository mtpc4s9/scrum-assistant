---
artifact_name: Sprint Progress Radiator (Flow Digest)
purpose: Provide an analytical overlay of the Sprint Backlog (from JIRA/ADO) to highlight flow health, bottlenecks, and alignment with the Sprint Goal. It supplements live PM tools by converting raw data into actionable insights for the Developers.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When generating this progress radiator, the AI Agent MUST adhere to these rules:
1.  **Tool Integration:** Pull real-time data from the connected PM Tool (e.g., JIRA, ADO). Do NOT list every single task. 
2.  **Flow Analysis (Not Status):** Analyze the WIP (Work In Progress). Identify cards that have not moved in > 24 hours. Identify columns with too many cards (bottlenecks).
3.  **Burndown Interpretation:** Interpret the burndown trend conceptually (e.g., "Trending Late", "Trending Early", "On Time") based on completed Story Points vs. Elapsed Days.
4.  **Actionable Nudges:** Suggest "Swarming" opportunities to the Developers if items are piling up in testing/review.
5.  **Output Generation:** Output ONLY the section below this line as a clean, copy-pasteable Slack/Teams friendly digest.

---

# 📡 SPRINT FLOW & PROGRESS RADIATOR
**📅 Cập nhật lúc:** *[Agent: Insert Time]* | **⏳ Ngày Sprint thứ:** *[Agent: X / Total Days]* 
**🎯 SPRINT GOAL:** *[Agent: Insert Sprint Goal]*

### 1. 📉 PHÂN TÍCH BURNDOWN / BURNUP (TIẾN ĐỘ TỔNG QUAN)
*   **Trạng thái xu hướng (Trend):** *[Agent: Evaluate as 🟢 ON TIME / 🟡 EARLY / 🔴 LATE]*
*   **Điểm dữ liệu:** Nhóm đã hoàn thành **[X]%** tổng khối lượng công việc (Story Points/Số lượng thẻ), trong khi thời gian Sprint đã trôi qua **[Y]%**.
*   **Nhận định nhanh:** *[Agent: Vd: "Đường burndown đang đi ngang trong 2 ngày qua. Chúng ta có dấu hiệu kẹt thẻ ở khâu Kiểm thử."]*

### 2. 🌊 SỨC KHỎE LUỒNG CÔNG VIỆC (FLOW HEALTH)
*Phân tích này dựa trên dữ liệu quét từ bảng JIRA hiện tại của nhóm:*

*   **✅ Cột Done:** *[X]* thẻ đã hoàn thành. 
*   **🔥 Cột In Progress / To Verify:** Đang có *[Y]* thẻ. *(Agent: Nếu Y quá lớn so với số lượng Developers, thêm cảnh báo vi phạm WIP Limit).*
*   **⚠️ Thẻ kẹt (WIP Aging):** 
    *   *[Agent: Vd: PBI #205 - Tích hợp Payment API đã nằm ở cột 'In Progress' 3 ngày. Có rào cản ẩn nào không?]*
    *   *[Agent: Vd: PBI #108 - Nằm ở cột 'To Verify' 2 ngày. Cần người hỗ trợ test.]*

### 3. 🚀 GỢI Ý HÀNH ĐỘNG CHO NHÓM (SWARMING NUDGES)
*   🛑 **Ngưng bắt đầu việc mới (Stop Starting):** Kho khoan kéo thêm thẻ từ cột 'To Do'.
*   🐝 **Bắt đầu hoàn thành (Start Finishing):** Có ai trong nhóm trống tay (capacity) để **Swarm** (tập trung) vào test thẻ *[Agent: Insert ID đang kẹt]* giúp đồng đội để đưa nó sang "Done" trong hôm nay không?
*   🚧 **Rào cản (Nếu có):** Rào cản *[Agent: Insert ID từ Impediment Log]* vẫn đang được **Scrum Master** xử lý. Nhóm hãy tiếp tục làm việc trên các thẻ không bị ảnh hưởng.

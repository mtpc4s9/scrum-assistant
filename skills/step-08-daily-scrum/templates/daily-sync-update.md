---
artifact_name: Daily Scrum - Developer Sync Update
purpose: Provide a concise, Sprint-Goal-focused preparation sheet for individual Developers (including dual-role SM/BA) to effectively communicate progress, actionable plans, and impediments during the 15-minute Daily Scrum.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When generating this update for a Developer, the AI Agent MUST adhere to these rules:
1.  **Goal-Centric:** Always place the Sprint Goal at the very top. Frame all completed and planned items in the context of how they help achieve this goal.
2.  **Bucket Sorting:** Categorize the user's assigned Sprint Backlog items into: 'Done (Last 24h)', 'Focus for Today', and 'Impediments/Blockers'.
3.  **No Status Reporting:** Keep the tone peer-to-peer. Strip out any task-level micro-details (e.g., "I spent 2 hours fixing a typo") unless they directly impact the Sprint Goal.
4.  **Markdown Table Format:** Output the data in a clean, copy-pasteable Markdown table so the user can easily drop it into Slack, Teams, or read it directly.
5.  **Output Generation:** Output ONLY the section below this line.

---

# 🔄 DAILY SCRUM SYNC: *[Agent: Insert Developer Name]*
**📅 Date:** *[Agent: Insert Date]*
**🎯 SPRINT GOAL:** *[Agent: Insert current Sprint Goal]*

### 🗣️ MY UPDATE (PREPARATION SHEET)
*Lưu ý: Bảng dưới đây giúp bạn chuẩn bị thông tin ngắn gọn, súc tích để chia sẻ với các **Developers** khác. Hãy tập trung vào giá trị mang lại cho **Sprint Goal**, không phải liệt kê danh sách công việc.*

| Category | Work Item (ID & Title) | Impact on Sprint Goal / Actionable Plan |
| :--- | :--- | :--- |
| **✅ DONE** *(Last 24h)* | *[Vd: #105 - Cập nhật luồng UX/UI cho Cổng thanh toán]* | *[Vd: Đã xong tài liệu BA, team Dev có thể bắt đầu code phần API tích hợp ngay hôm nay.]* |
| **🚀 FOCUS** *(Next 24h)* | *[Vd: #108 - Viết Acceptance Criteria cho tính năng Lịch sử giao dịch]* | *[Vd: Sẽ chốt điều kiện nghiệm thu với PO vào chiều nay để đảm bảo thẻ này sẵn sàng test vào ngày mai.]* |
| **🚧 BLOCKERS** *(Impediments)* | *[Vd: Chờ tài liệu API từ đối tác Kambi]* | *[Vd: Đang bị block thẻ #110. Cần sự hỗ trợ của **Scrum Master** để hối thúc Vendor.]* |

---
**⚡ CÂU HỎI TỰ KIỂM TRA TRƯỚC KHI VÀO HỌP:**
- [ ] Phần việc tôi làm hôm nay có đang nằm trên "đường găng" (critical path) của **Sprint Goal** không? Nếu không, tôi có nên tạm dừng để giúp (Swarming) người khác không?
- [ ] Tôi có đang giữ rào cản nào mà chưa báo cho **Scrum Master** biết không?

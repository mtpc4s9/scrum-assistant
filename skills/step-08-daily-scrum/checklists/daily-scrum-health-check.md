---
artifact_name: Daily Scrum Health Check
purpose: Provide the Scrum Master and AI Agent with a diagnostic tool to evaluate whether the Daily Scrum is functioning as an empirical planning event or degrading into a status report or problem-solving meeting.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When evaluating the health of a Daily Scrum or responding to user prompts regarding this event, the AI Agent MUST use the following checklist to detect anti-patterns.
1.  **Anti-Status Report Rule:** If the user attempts to generate a "status report for management" from the Daily Scrum, the Agent MUST respectfully decline and remind the user that the Daily Scrum is a planning event for Developers, not a reporting tool.
2.  **Goal-Centric Focus:** Ensure updates emphasize the **Sprint Goal** over individual task completion.
3.  **Output Generation:** Output ONLY the section below this line when the user requests a health check evaluation.

---

# 🏥 DAILY SCRUM HEALTH CHECK (DIAGNOSTIC TOOL)

**⚠️ LƯU Ý DÀNH CHO SCRUM MASTER:**
*Bộ công cụ này dùng để chẩn đoán mức độ trưởng thành của nhóm **Developers** trong việc duy trì một sự kiện tinh gọn, tự quản lý (**Self-managing**) và hướng tới mục tiêu. Hãy quan sát (không can thiệp thô bạo) và sử dụng các dữ liệu này cho buổi **Sprint Retrospective** tiếp theo.*

### 1. 🎯 SỰ TẬP TRUNG VÀO MỤC TIÊU (GOAL & FOCUS)
- [ ] Nhóm có sử dụng **Sprint Goal** làm trung tâm của cuộc thảo luận không? (Thay vì chỉ liệt kê "Tôi đã làm task A, task B").
- [ ] Bảng **Sprint Backlog** có được cập nhật trực quan và sử dụng làm công cụ dẫn dắt cuộc họp (Walk the Board) không?
- [ ] Khi kết thúc, nhóm có một kế hoạch hành động rõ ràng (actionable plan) cho 24 giờ tiếp theo để tiến gần hơn đến **Sprint Goal** không?

### 2. 👥 GIAO TIẾP VÀ TỰ QUẢN LÝ (COMMUNICATION & SELF-MANAGING)
- [ ] Giao tiếp Ngang hàng (Peer-to-peer): Các **Developers** có đang nói chuyện, giao tiếp bằng mắt với nhau không? *(Báo động đỏ: Mọi người đều quay mặt về phía **Scrum Master** hoặc **Product Owner** để báo cáo).*
- [ ] Tinh thần Làm việc bầy đàn (Swarming): Khi một người báo cáo gặp rào cản hoặc nguy cơ trễ hạn, những người khác có chủ động đề nghị tạm dừng việc của mình để giúp đỡ không?
- [ ] Không Đổ lỗi (Blame-free): Khi có sự cố, nhóm tập trung vào giải pháp cho phần còn lại của **Sprint** thay vì tìm kiếm người chịu trách nhiệm?

### 3. ⏱️ QUẢN LÝ THỜI GIAN VÀ RÀO CẢN (TIMEBOX & IMPEDIMENTS)
- [ ] Sự kiện có bắt đầu đúng giờ và kết thúc dứt điểm trong vòng 15 phút (Timeboxed) không?
- [ ] Không Giải quyết vấn đề (No Problem-Solving): Các cuộc tranh luận kỹ thuật sâu có được nhận diện và chủ động chuyển sang "thảo luận ngoại tuyến" (offline/after-meeting) để không chiếm dụng thời gian của cả nhóm không?
- [ ] Tính minh bạch (**Transparency**) về Rào cản: Các trở ngại (Impediments) có được nêu ra rõ ràng, không giấu giếm, và ngay lập tức được **Scrum Master** ghi nhận vào Impediment Log không?

---
**📊 ĐÁNH GIÁ SỨC KHỎE (HEALTH SCORECARS):**
- **Toàn bộ ô được tick (Xanh):** Nhóm đang thực hành Scrum xuất sắc.
- **Thiếu phần Timebox (Vàng):** Nhóm cần học cách giao tiếp ngắn gọn và phân định giữa "Đồng bộ hóa" và "Giải quyết vấn đề".
- **Thiếu phần Peer-to-peer và Goal (Đỏ):** Sự kiện đang bị biến tướng thành Báo cáo trạng thái (Status Report). **Scrum Master** cần can thiệp thông qua huấn luyện (coaching) ngay lập tức.

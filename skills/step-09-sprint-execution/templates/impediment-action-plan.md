---
artifact_name: Cross-Departmental Impediment Action Plan
purpose: Provide the Scrum Master with a comprehensive, actionable strategy to analyze root causes, orchestrate cross-departmental collaboration, and execute escalation paths to resolve critical blockers during Sprint Execution.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When generating this action plan based on an ID from `impediment-log.md`, the AI Agent MUST adhere to these rules:
1.  **AI-to-User Interview Trigger:** Review the input data. If critical context is missing (e.g., *Who is the contact person in the external department? What is the technical root cause? What prior communication has occurred?*), the Agent MUST STOP generating the document and state: 
    👉 *"⚠️ CHẾ ĐỘ PHỎNG VẤN (AI-TO-USER INTERVIEW TRIGGERED): Dữ liệu từ Impediment Log không đủ để lập kế hoạch phối hợp liên phòng ban. Xin vui lòng trả lời 3 câu hỏi sau để tôi thiết kế Action Plan chính xác nhất: [Liệt kê 3 câu hỏi ngắn gọn]."*
2.  **Cross-Departmental Focus:** Structure the resolution plan to clearly assign actions across different organizational silos (e.g., DevOps, Legal, Vendor).
3.  **Contingency for Developers:** Always include a section guiding the Developers on what to focus on (Swarming) while the Scrum Master resolves this blocker.
4.  **Output Generation:** Output ONLY the section below this line ONCE all necessary information is gathered.

---

# 🚨 IMPEDIMENT ACTION PLAN: *[Agent: Insert Impediment ID - Title]*

## 1. 📋 THÔNG TIN TỔNG QUAN LỖI (IMPEDIMENT CONTEXT)
*   **Trạng thái hiện tại:** *[Agent: Ví dụ: Open / Escalated]*
*   **Mức độ ảnh hưởng (Impact to Sprint Goal):** *[Agent: Phân tích chi tiết rủi ro đối với Sprint Goal và Definition of Done nếu rào cản này không được gỡ bỏ trong X ngày tới.]*
*   **Các bên liên quan (Affected Parties):** Nhóm **Developers**, *[Agent: Tên các phòng ban khác bị ảnh hưởng hoặc cần phối hợp, vd: Security Team, Kambi Vendor]*

## 2. 🔍 PHÂN TÍCH NGUYÊN NHÂN GỐC RỄ (ROOT CAUSE ANALYSIS - 5 WHYS)
*Để giải quyết triệt để, chúng ta không chỉ chữa triệu chứng mà phải tìm ra nguyên nhân gốc.*
1.  **Why?** *[Agent: Điền lý do 1. Vd: Tại sao không thể test luồng thanh toán? -> Vì API Key môi trường Staging bị thu hồi.]*
2.  **Why?** *[Agent: Điền lý do 2. Vd: Tại sao bị thu hồi? -> Vì chính sách bảo mật mới của team InfoSec]*
3.  **Why?** *[Agent: Điền lý do 3]*
*   **👉 Kết luận Root Cause:** *[Agent: Tóm tắt nguyên nhân cốt lõi]*

## 3. 🤝 KẾ HOẠCH PHỐI HỢP & LEO THANG (CROSS-DEPARTMENTAL ACTION PLAN)
*Chiến lược thực thi dành cho **Scrum Master** để làm việc với các bộ phận liên quan.*

| Action Item | Phụ trách (Owner) | Phối hợp với (Cross-Dept) | Hạn chót (Target) | Trạng thái |
| :--- | :--- | :--- | :--- | :--- |
| *[Vd: Tổ chức họp khẩn 15p làm rõ chuẩn bảo mật mới]* | **Scrum Master** | Head of InfoSec | *[Date/Time]* | To Do |
| *[Vd: Cấp lại API Key tạm thời với quyền Read-only]* | *[Tên người bên InfoSec]* | **Developers** (Lead) | *[Date/Time]* | To Do |
| *[Vd: Cập nhật tài liệu quy trình xin Key mới để tránh lặp lại]* | **Scrum Master** | DevOps Team | *[Post-Sprint]* | To Do |

## 4. 📝 BẢN NHÁP GIAO TIẾP LEO THANG (ESCALATION COMMUNICATION DRAFT)
*Sử dụng bản nháp email/tin nhắn (Tiếng Anh/Việt) dưới đây để gửi cho các **Stakeholder** hoặc Quản lý cấp cao nhằm yêu cầu hỗ trợ (Remove barriers between stakeholders and Scrum Teams).*

> **Subject:** [URGENT] Blocker Impacting Sprint Goal - Action Required from [Department Name]
> **Hi [Stakeholder Name],**
> 
> Our Scrum Team is currently blocked by *[Describe blocker briefly]*. This directly impacts our ability to deliver the *[Insert Sprint Goal]*, which is critical for *[Insert Business Value / Release Date]*. 
> 
> To resolve this and prevent a Sprint failure, we urgently need *[Specific action]* from your team by *[Date/Time]*. I have set up a quick 10-minute sync at *[Time]* to finalize the next steps. Let me know if we can proceed.
> 
> Best,
> **[Scrum Master Name]**

## 5. 🛡️ PHƯƠNG ÁN DỰ PHÒNG CHO NHÓM (DEVELOPERS' CONTINGENCY PLAN)
*Trong lúc **Scrum Master** đi giải quyết rào cản này, nhóm **Developers** cần thực hành Tính thích ứng (**Adaptation**):*
*   **Stop/Pause:** Tạm dừng mọi nỗ lực code/test đối với PBI *[Insert ID]* để tránh lãng phí (Waste).
*   **Swarm:** Chuyển hướng sức chứa (Capacity) sang hỗ trợ hoàn thành PBI *[Insert ID khác]* đang ở cột In Progress, hoặc giải quyết các khoản Nợ kỹ thuật (Technical Debt) nhỏ trong lúc chờ đợi.

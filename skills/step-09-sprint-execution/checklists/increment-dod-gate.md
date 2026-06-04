---
artifact_name: Increment Definition of Done (DoD) Quality Gate
purpose: Serve as a strict, non-negotiable quality filter before any Product Backlog Item (PBI) can be declared "Done" and integrated into the Increment. It uniquely combines software engineering standards with stringent iGaming/Lottery regulatory and compliance checks.
---

### 🤖 AGENT DIRECTIVE (HIDDEN FROM FINAL OUTPUT)
When a Developer requests to update a PBI status to "Done", or states that they have "finished" an item, the AI Agent MUST silently execute this checklist.
1.  **Strict Enforcement:** If ANY item in this checklist is unchecked or unverified by the Developer's update, the Agent MUST NOT mark the item as Done. 
2.  **Intervention Prompt:** The Agent must reply with a friendly but firm coaching prompt: *"Great progress! However, to meet our Definition of Done and safely integrate this into the Increment, we still need to verify [Missing Criteria]. Do you need to swarm with QA or Compliance to finish this today?"*
3.  **No Partial Done:** Remind the team that "Done" is binary. There is no "Done for Dev" or "80% Done".
4.  **Output Generation:** Output ONLY the section below this line when the Scrum Master or Developers request to review the current DoD constraints.

---

# 🛑 INCREMENT QUALITY GATE: DEFINITION OF DONE (DoD)

**⚠️ LƯU Ý DÀNH CHO DEVELOPERS:**
*Một **Increment** chỉ được sinh ra khi toàn bộ các tiêu chí dưới đây được thỏa mãn [2]. Bất kỳ hạng mục nào không đạt chuẩn sẽ không được phép đưa vào **Sprint Review** và phải quay trở lại **Product Backlog** [2].*

### 1. 🛠️ CHẤT LƯỢNG KỸ THUẬT VÀ TÍCH HỢP (TECHNICAL & INTEGRATION)
- [ ] **Code Review:** Mã nguồn đã được peer-review bởi ít nhất 1 Developer khác.
- [ ] **Unit / Integration Tests:** Các bài test tự động (Automated tests) đã được viết và vượt qua ngưỡng bao phủ (coverage) quy định (ví dụ: >85%).
- [ ] **CI/CD Pipeline:** Mã nguồn đã được merge an toàn vào nhánh chính (main branch) và toàn bộ pipeline CI/CD đều báo xanh (Green).
- [ ] **No Blocker/Critical Bugs:** Không có lỗi nghiêm trọng (Severity 1 & 2) nào được ghi nhận trên đoạn code này.

### 2. 🎲 ĐẶC THÙ NGÀNH iGAMING & LOTTERY (DOMAIN & COMPLIANCE)
- [ ] **RTP & Math Validation:** Nếu tính năng có can thiệp vào logic game, thuật toán tạo số ngẫu nhiên (RNG) và Tỷ lệ trả thưởng (RTP) đã được chạy giả lập và xác nhận bằng toán học.
- [ ] **Payment Sandbox:** Nếu tính năng liên quan đến nạp/rút, đã test thành công trên môi trường Sandbox của đối tác cổng thanh toán (VD: Kambi, Pragmatic, Momo).
- [ ] **Security & Anti-Fraud:** Đã chạy rà soát lỗ hổng bảo mật cơ bản và xác nhận không vi phạm các luật chống gian lận/rửa tiền (AML).

### 3. 🎯 NGHIỆP VỤ VÀ NGƯỜI DÙNG (BUSINESS & USER CENTRIC)
- [ ] **Acceptance Criteria (AC):** Toàn bộ các tiêu chí nghiệm thu (được viết dưới dạng BDD/Gherkin) của thẻ PBI này đều đã vượt qua [6, 7].
- [ ] **Usability & UX:** Giao diện (nếu có) hiển thị đúng trên các thiết bị mục tiêu (Mobile/Desktop) và tuân thủ thiết kế từ team UI/UX.
- [ ] **Documentation:** Các tài liệu Release Notes, API Swagger, hoặc User Guide (nếu bị ảnh hưởng) đã được cập nhật bản nháp.

---
*Trạng thái: 🟢 SẴN SÀNG TRỞ THÀNH MỘT PHẦN CỦA INCREMENT.*

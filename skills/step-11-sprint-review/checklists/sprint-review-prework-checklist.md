---
artifact_name: Sprint Review Prework & AI Interview Protocol
purpose: Act as a mandatory gatekeeper before generating the Sprint Review Slide Deck. It forces the AI Agent to conduct a Socratic interview with the Product Owner to ensure all logistics, demonstrations, and DoD validations (including early PO approval) are confirmed.
---

### 🤖 AGENT DIRECTIVE (AI-TO-USER INTERVIEW TRIGGERED)
When the user requests to prepare for the Sprint Review or generate the `sprint-review-slide-deck.md`, the AI Agent MUST NOT generate the slide deck immediately. Instead, the Agent MUST pause and initiate the following interview protocol based on the Essential Scrum Prework framework.

#### 1. INTERVIEW PROTOCOL (Ask these 4 questions to the User/PO)
Present the following questions to the user in a professional, conversational tone. Wait for their answers before proceeding.

1.  **Confirming "Done" (The PO Gate):** *"Trước khi đưa các thẻ vào Slide, bạn (với vai trò **Product Owner**) đã trực tiếp nghiệm thu (Early Review) và xác nhận các thẻ này vượt qua **Definition of Done** 100% chưa? (Tuyệt đối không đưa thẻ chưa Done vào demo)."*
2.  **Determine Whom to Invite:** *"Ngoài **Scrum Team**, có những **Stakeholder** đặc thù nào (ví dụ: Marketing, Legal, Khách hàng VIP) cần được mời dựa trên tính năng vừa hoàn thành không?"*
3.  **Prepare for Demonstration:** *"Tính năng nào sẽ là tâm điểm Demo hôm nay? Và ai trong nhóm **Developers** sẽ là người trực tiếp cầm chuột thao tác (Show, don't tell)?"*
4.  **Review the Sprint Goal:** *"Nhìn lại **Sprint Goal**, bạn đánh giá chúng ta đã Đạt, Đạt một phần, hay Không đạt để tôi đưa vào bản tóm tắt?"*

#### 2. EVALUATION & SLIDE DECK GENERATION
Once the user provides the answers:
*   If the user admits some items are NOT fully approved by the PO, advise them strictly to remove those items from the demonstration list to protect **Transparency**.
*   Synthesize the answers to automatically populate the variables in `templates/sprint-review-slide-deck.md` (e.g., Target Stakeholders, Demo Presenter, Goal Status).
*   Generate and output the final Slide Deck.

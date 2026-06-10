---
artifact_name: Sprint Retrospective Prework & AI Interview Protocol
purpose: Act as a mandatory gatekeeper before generating the Sprint Retrospective Slide Deck. It forces the AI Agent to conduct a Socratic interview with the Scrum Master to define the focus, gather objective data, and verify the completion of past improvement actions.
---

### 🤖 AGENT DIRECTIVE (AI-TO-USER INTERVIEW TRIGGERED)
When the user requests to prepare for the **Sprint** Retrospective or generate the `sprint-retrospective-slide-deck.md`, the AI Agent MUST NOT generate the slide deck immediately. Instead, the Agent MUST pause and initiate the following 4-step interview protocol based on the Essential Scrum Prework framework.

#### 1. INTERVIEW PROTOCOL (Ask these 4 questions to the User/Scrum Master)
Present the following questions to the user in a professional, conversational tone. Wait for their answers before proceeding.

1.  **Review Previous Actions (The Accountability Check):** *"Trước khi bắt đầu, hãy nhìn lại Hành động cải tiến (Improvement Action) của **Sprint** trước. Nhóm **Developers** đã hoàn thành nó chưa? (Nếu chưa, chúng ta cần đưa nó vào Slide đầu tiên để nhóm phân tích lý do)."*
2.  **Define the Focus:** *"Trọng tâm (Focus) của buổi Retrospective kỳ này là gì? (Ví dụ: Cải thiện kỹ năng Test-Driven Development, Khắc phục tình trạng thắt cổ chai ở khâu QA, hay Xử lý Technical Debt?)"*
3.  **Gather Objective Data:** *"Vui lòng cung cấp Dữ liệu khách quan (Objective Data) của Sprint vừa rồi để tôi đưa vào biểu đồ: Vận tốc (Velocity) đạt được là bao nhiêu? Biểu đồ Burndown diễn biến ra sao? Có bao nhiêu lỗi (bugs) phát sinh?"*
4.  **Select Exercises:** *"Bạn dự định dùng kỹ thuật điều phối (Exercises) nào chiều nay? (Ví dụ: Event Timeline, Dot Voting, Silent Grouping, hay Emotions Seismograph?)"*

#### 2. EVALUATION & SLIDE DECK GENERATION
Once the user provides the answers:
*   If the user indicates that previous actions were completely ignored, politely remind the **Scrum Master** that "Don't separate, integrate!" is the rule, and ask if those actions should be re-prioritized before tackling new insights.
*   Synthesize the answers to automatically populate the variables in `templates/sprint-retrospective-slide-deck.md` (e.g., Focus Title, Objective Data placeholders, and Exercise instructions).
*   Generate and output the final Slide Deck.

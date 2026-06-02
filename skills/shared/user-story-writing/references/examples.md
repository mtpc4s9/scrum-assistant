---
description: 7 production-grade, high-fidelity User Story and Gherkin Acceptance Criteria examples spanning common online education (EdTech) and e-commerce domains.
metadata:
  tags: [examples, agile, user-story, acceptance-criteria, edtech]
  source: internal
---

# User Story & Acceptance Criteria Production Examples

This document provides seven production-grade, high-fidelity examples of User Stories and Given-When-Then Gherkin Acceptance Criteria (AC). These examples cover common product modules in online learning platforms (EdTech), e-commerce, and enterprise B2B partner portals.

*Note: Domain-specific brandings have been genericized (e.g., Platform X, Academy Y, Provider Z) to ensure broad enterprise applicability.*

---

## Example 1: Course Registration & Payments

### US-ENROLL-001: Course Registration via Digital Wallet Payment

*   **AS A:** Registered student with an active account and a linked digital wallet,
*   **I WANT TO:** Purchase the "Business Analysis Fundamentals" course and pay via my linked wallet,
*   **SO THAT:** I can immediately access the learning materials without waiting for manual bank transfer validation.

#### INVEST Self-Check
*   **Independent:** ✅ Wallet linking is already developed (handled in a separate upstream story).
*   **Negotiable:** ✅ Payment gateway integration details are kept abstract to allow developer flexibility.
*   **Valuable:** ✅ Students receive immediate learning access; the business realizes automated instant revenue.
*   **Estimable:** ✅ Payment logic flows are similar to previously implemented payment stories.
*   **Small:** ✅ Estimated at approximately 3 development days.
*   **Testable:** ✅ All scenarios have clear, measurable pass/fail criteria.

#### Acceptance Criteria

**AC1: Successful payment and enrollment (Happy Path)**
*   **GIVEN** the student has selected the "BA Fundamentals" course priced at $150,
*   **AND** the student's linked wallet balance is $\ge$ $150, and the course has available seats,
*   **WHEN** the student clicks "Register Now" $\rightarrow$ confirms payment $\rightarrow$ enters their wallet secure PIN,
*   **THEN** the system deducts $150 from the linked wallet within 5 seconds,
*   **AND** automatically enrolls the student in the course,
*   **AND** sends a confirmation email containing the course access link, saving the course to "My Learning Dashboard".

**AC2: Insufficient wallet balance (Negative Path)**
*   **GIVEN** the student's wallet balance is $80, and the course is priced at $150,
*   **WHEN** the student clicks "Register Now",
*   **THEN** the system blocks the transaction and displays the message: "Insufficient balance. You need an additional $70 to purchase this course.",
*   **AND** provides two options: "Top Up Wallet" and "Choose Another Payment Method",
*   **AND** does not deduct any funds or create an enrollment record.

**AC3: Network connection loss during payment processing (Edge Case)**
*   **GIVEN** the student has confirmed payment and the system is actively communicating with the gateway,
*   **WHEN** the network connection is lost for up to 30 seconds,
*   **THEN** the system displays a loading indicator with the message: "Verifying transaction state...",
*   **AND** once the connection is restored, automatically checks the transaction status with the gateway,
*   **AND** displays the final success or failure screen without executing a double deduction.

---

## Example 2: One-on-One Mentor Booking

### US-MENTOR-BOOK-001: Schedule a 1-on-1 Mentoring Session

*   **AS A:** Premium student currently enrolled in the "Advanced Business Analysis" program,
*   **I WANT TO:** Book a 1-on-1 mentoring session with a mentor specializing in my topic of interest,
*   **SO THAT:** I can receive tailored guidance on my practical capstone project without waiting for the next cohort live class.

#### Acceptance Criteria

**AC1: Successful slot booking (Happy Path)**
*   **GIVEN** the student selects a mentor, a vacant slot on 15/06/2026 at 20:00,
*   **AND** the student has at least 1 remaining 1-on-1 session quota in their monthly package,
*   **WHEN** the student confirms the booking and enters their specific query description,
*   **THEN** the system generates booking ID `MNT-20260615-001`,
*   **AND** creates a Google Meet invitation sent to both the student's and mentor's calendars,
*   **AND** deducts 1 session from the student's monthly quota,
*   **AND** schedules a reminder notification sent via email and push 1 hour before the session.

**AC2: Booking race condition - slot taken simultaneously (Edge Case)**
*   **GIVEN** the student is on the slot confirmation screen for 15/06/2026 at 20:00,
*   **WHEN** the student clicks "Confirm Booking" but the slot was booked by another student 3 seconds prior,
*   **THEN** the system blocks the booking and displays the message: "This slot is no longer available. Please select another time.",
*   **AND** updates the mentor's availability calendar in real-time,
*   **AND** does not deduct from the student's session quota.

**AC3: Mentor cancels booking (Negative Path)**
*   **GIVEN** the student has a successfully booked session,
*   **WHEN** the mentor cancels the session at least 6 hours before the scheduled time,
*   **THEN** the system automatically refunds 1 session to the student's monthly quota,
*   **AND** sends a cancellation email explaining the reason and suggesting 3 alternative slots for the next 7 days,
*   **AND** logs the cancellation on the mentor's profile for the internal quality team's audit.

---

## Example 3: Learning Progress Dashboard

### US-PROGRESS-001: View Personal Learning Progress Reports

*   **AS A:** Student enrolled in multiple parallel courses,
*   **I WANT TO:** View a centralized learning progress dashboard showing progress per course,
*   **SO THAT:** I can identify my current position in the curriculum and prioritize reviewing uncompleted lessons.

#### Acceptance Criteria

**AC1: Correct dashboard metrics display (Happy Path)**
*   **GIVEN** the student is enrolled in "BA Fundamentals" (60% complete) and "Agile for BA" (20% complete),
*   **WHEN** the student accesses the "My Learning Progress" page,
*   **THEN** the system displays the percentage completed, lessons viewed, and remaining lessons for each course,
*   **AND** highlights the "Next Suggested Lesson" CTA for each active course,
*   **AND** ensures the data updates within 60 seconds after the student completes any lesson.

**AC2: Course purchased but not yet started (Edge Case)**
*   **GIVEN** the student has purchased the "SQL for BA" course but has not yet opened any lesson,
*   **WHEN** the student views the progress dashboard,
*   **THEN** the system displays: "0% Complete - Start Learning Now!" with a prominent "Start Lesson 1" CTA,
*   **AND** does not display raw null errors or faulty calculations.

**AC3: Offline progress sync (Edge Case)**
*   **GIVEN** the student completed 3 lessons offline via the mobile application,
*   **WHEN** the mobile application establishes a stable internet connection,
*   **THEN** the system synchronizes the offline progress to the server within 60 seconds,
*   **AND** updates the completion percentage accurately without overwriting or resetting other progress states,
*   **AND** displays a Toast notification: "Your progress has been synchronized."

---

## Example 4: Automated Course Certificate Issuance

### US-CERT-001: Automated Completion Certificate Issuance

*   **AS A:** Student who has completed 100% of the lessons and passed the final exam,
*   **I WANT TO:** Receive an official, authenticated completion certificate showing my name, course title, and verification ID,
*   **SO THAT:** I can share it on LinkedIn and include it as verified proof of skill in my job applications.

#### Acceptance Criteria

**AC1: Automated certificate generation (Happy Path)**
*   **GIVEN** student "John Doe" has completed 100% of the lessons and achieved a score of $\ge$ 70% on the "BA Fundamentals" final exam,
*   **WHEN** the exam engine validates the passing score,
*   **THEN** the system generates a secure PDF certificate with verification ID `CERT-BAF-2026-00123`,
*   **AND** emails the certificate as a PDF attachment to the student within 5 minutes,
*   **AND** displays the certificate under "My Achievements" in the student portal.

**AC2: Minimum passing score not met (Negative Path)**
*   **GIVEN** the student has completed 100% of the lessons but scores 55% on the final exam,
*   **WHEN** the exam engine validates the score,
*   **THEN** the system blocks certificate generation,
*   **AND** displays the message: "You need a score of 70% or higher to earn a certificate. Your current score: 55%. Would you like to retake the exam?",
*   **AND** locks the retake option for 24 hours to encourage review.

**AC3: External certificate verification (Edge Case)**
*   **GIVEN** an external recruiter has received a PDF certificate and accesses the verification URL,
*   **WHEN** the recruiter inputs verification ID `CERT-BAF-2026-00123` at `verify.platformx.com`,
*   **THEN** the system displays the student's name, course title, completion date, and syllabus covered,
*   **AND** if the ID does not exist or has been tampered with, displays: "Invalid Verification Code."

---

## Example 5: Live Class Q&A Queue

### US-LIVE-001: Submit Questions during a Live Online Class

*   **AS A:** Student attending a live online stream,
*   **I WANT TO:** Submit a text question through the stream sidebar while the instructor is presenting,
*   **SO THAT:** I can log my query without interrupting the speaker, ensuring it is addressed during the Q&A segment.

#### Acceptance Criteria

**AC1: Successful question submission (Happy Path)**
*   **GIVEN** the student is actively attending an ongoing live stream class,
*   **WHEN** the student inputs a question (max 500 characters) and clicks "Submit Question",
*   **THEN** the question appears in the instructor's Q&A moderator queue,
*   **AND** the student sees the status indicator: "Question Submitted - Awaiting Q&A Session",
*   **AND** other students attending the live stream can upvote the question (+1).

**AC2: Duplicate question detection (Edge Case)**
*   **GIVEN** a student's input matches an existing question in the queue with a similarity score of $\ge$ 80%,
*   **WHEN** the student clicks "Submit Question",
*   **THEN** the system prompts: "A similar question has already been asked. Would you like to upvote it instead?",
*   **AND** if accepted, increments the vote count of the original question rather than posting a duplicate.

**AC3: Submitting to a completed live stream (Negative Path)**
*   **GIVEN** the live class stream has ended (status: "Ended"),
*   **WHEN** the student attempts to submit a question through the interface,
*   **THEN** the system disables the text input field and displays: "This class has ended. You can view the recording or post your questions in the course forum.",
*   **AND** provides a direct link to the specific course discussion forum.

---

## Example 6: B2B Enterprise Partner Portal

### US-B2B-ENROLL-001: Bulk Employee Course Enrollment via File Upload

*   **AS A:** Corporate HR Manager of a signed enterprise partner,
*   **I WANT TO:** Upload an Excel file containing employee names and emails to allocate training seats,
*   **SO THAT:** I can enroll up to 100 employees simultaneously without performing individual registrations.

#### Acceptance Criteria

**AC1: Successful bulk upload and enrollment (Happy Path)**
*   **GIVEN** the HR Manager uploads an Excel sheet matching the official template containing 50 employee records,
*   **AND** the corporate account has 50 or more unallocated seat licenses available,
*   **WHEN** the HR Manager clicks "Confirm Allocations",
*   **THEN** the system registers and enrolls the 50 employees within 2 minutes,
*   **AND** sends automated welcome emails with temp credentials to each employee,
*   **AND** displays a success report: "Successfully enrolled 50/50 employees."

**AC2: Partial record errors (Edge Case)**
*   **GIVEN** the Excel sheet contains 50 records, but 3 rows have invalid email formats and 2 rows contain duplicate emails,
*   **WHEN** the HR Manager uploads the file,
*   **THEN** the system halts processing and displays a validation preview highlighting the 5 erroneous rows with descriptive error flags,
*   **AND** provides the option to: "Proceed with the 45 valid records" or "Upload corrected file",
*   **AND** does not enroll or deduct seat licenses for the invalid rows if the manager chooses to proceed with the subset.

**AC3: Insufficient seat licenses (Negative Path)**
*   **GIVEN** the corporate account has only 30 unallocated seat licenses remaining,
*   **WHEN** the HR Manager attempts to upload a file containing 50 employee records,
*   **THEN** the system blocks the enrollment action and displays: "Insufficient seats. You uploaded 50 employees but only have 30 seats available. Please contact account management to purchase more.",
*   **AND** does not deduct any seat licenses or enroll any users.

---

## Example 7: Community Forum Moderation

### US-FORUM-REPORT-001: Report Community Guidelines Violations

*   **AS A:** Community member reading forum discussions,
*   **I WANT TO:** Flag a post or comment as a community guidelines violation,
*   **SO THAT:** Internal moderators can review and remove harmful or off-topic content to preserve community quality.

#### Acceptance Criteria

**AC1: Successful flag submission (Happy Path)**
*   **GIVEN** the member is viewing a post containing spam or inappropriate content,
*   **WHEN** the member clicks the "Flag" button $\rightarrow$ selects a reason code $\rightarrow$ adds optional details $\rightarrow$ clicks "Submit Report",
*   **THEN** the system generates flag ticket `RPT-20260506-001`,
*   **AND** routes the ticket to the moderator dashboard queue,
*   **AND** if the same post receives $\ge$ 5 flags within a 1-hour window, automatically hides the post and queues it for high-priority moderator review.

**AC2: Report resolution notifications (Happy Path)**
*   **GIVEN** a member has flagged a post,
*   **WHEN** a moderator updates the ticket status (e.g., to "Resolved - Post Removed" or "Dismissed - No Violation"),
*   **THEN** the system sends a notification to the reporting member containing the outcome,
*   **AND** if the report is confirmed as valid, displays: "Thank you for helping keep our community safe."

**AC3: Violation of Moderation SLA (Edge Case)**
*   **GIVEN** a flag ticket has been created but remains unaddressed in the queue for more than 48 hours,
*   **WHEN** the system's cron job executes,
*   **THEN** it escalates the ticket status to "Overdue SLA" and assigns it directly to the Community Manager,
*   **AND** sends a notification to the reporting member apologizing for the delay and committing to resolve it within 12 hours.

---

## Strategic Design Patterns Identified

1.  **Strict Persona Context:** Personas are never generic "users." They always state the exact role and system state (e.g., "student with a linked wallet", "HR Manager of a signed B2B partner").
2.  **Measurable Outcomes:** Goals focus on specific, testable values (e.g., "50 employees", "$\ge$ 70% exam score", "500 characters limit").
3.  **Outcome-Driven Value:** "So that..." statements focus on business outcome and user capability (e.g., "immediate course access", " LinkedIn verification", "bulk seat allocation").
4.  **Three-Path AC Structure:** Every story has at least three Gherkin scenarios representing the **Happy Path**, **Edge Case**, and **Negative/Error Path**.
5.  **Purely Functional Scenarios:** Free of any UI dimensions, button colors, programming frameworks, or specific database column schemas, keeping them highly negotiable and testable.

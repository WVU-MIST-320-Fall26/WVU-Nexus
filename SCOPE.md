WVU Nexus: Project Scope Statement
Course: MIST 320, Fall 2026 Project Manager: Ethan W Version: 1.0 Status: Baselined

This document translates the project charter into a scope baseline. Changes to it follow the change control process in section 9.


1. Problem Statement
WVU students manage academic and campus life across more than fifteen disconnected applications. None of these systems share data with each other, so the student is the integration layer.

Three specific pain points:

Deadlines live in two places and neither is complete. Blackboard calendars carry only what professors enter there. Syllabi carry the rest, often as a table in a PDF a student reads once in August.
Campus status requires hunting. PRT status, dining hours, and library hours each live in a different app or page.
Risk is invisible until it is too late. A student rarely knows a single assignment is worth 25 percent of the grade until after they miss it.

The root cause is a lack of integration, not a lack of data. Most of the required information is already public or already belongs to the student.


2. Product Scope vs Project Scope
Product scope is the functionality the student interacts with: the dashboard, deadline import, syllabus extraction, and the risk indicator. It is measured against the acceptance criteria in section 6.

Project scope is the work required to deliver it: sprint planning, the issue backlog, testing, the accessibility audit, deployment, pilot recruitment, and course deliverables. It is measured against the project board and the six team deliverables.


3. In-Scope Deliverables
#
Deliverable
Epic
D1
Responsive web application with account creation and sign in
epic:foundation
D2
Deployed environment with CI running on every change
epic:foundation
D3
Live PRT status display
epic:campus-data
D4
Campus information: academic calendar, dining and library hours, alerts
epic:campus-data
D5
Blackboard calendar import by student-supplied share link
epic:deadlines
D6
Unified deadline list and detail views
epic:deadlines
D7
Syllabus upload and automated extraction of assignments, dates, and grade weights
epic:syllabus
D8
Student review and correction of extracted items
epic:syllabus
D9
Academic risk indicator built on syllabus weight, deadline proximity, and completion status
epic:insights
D10
Dashboard combining deadlines, risk, and campus status
epic:insights
D11
Accessibility conformance to WCAG 2.1 AA, documented
epic:trust
D12
Privacy and security design with a consent flow
epic:trust
D13
Pilot deployment to WVU students with usage analytics
epic:trust



4. Out-of-Scope Exclusions
These boundaries exist to prevent scope creep and each has a reason.

Excluded
Reason
Banner and STAR grade synchronization
Requires institutional credentials a student team cannot obtain in one semester
DegreeWorks degree progress
Same access constraint
Any feature assuming future institutional API access
The architecture will not depend on approval that has not been granted in writing
Native iOS and Android applications
Delivery capacity. The product is a responsive web application.
Payment processing, dining account balances, laundry machine status
Vendor systems requiring commercial agreements
Replacement of Okta or other authentication systems
Security scope beyond the team's mandate
Machine learning models trained on official grade data
The training data is out of reach. The risk indicator uses a transparent rule based calculation instead.
Social features, messaging, and anonymous feeds
Moderation and safety obligations the team cannot staff


Anything not listed in section 3 is out of scope by default.


5. Requirements
5.1 Functional requirements
ID
Requirement
FR1
Students can create an account and sign in
FR2
The system displays current PRT operating status
FR3
Students can connect a Blackboard calendar share link and import events
FR4
Students can upload a syllabus PDF and receive extracted assignments, dates, and weights
FR5
Students can review, correct, and confirm extracted items before they are saved
FR6
The system displays all deadlines in one chronological view
FR7
The system calculates and displays a risk indicator per course
FR8
Students can enter grades received and mark work complete
FR9
Students can delete their account and all associated data

5.2 Non-functional requirements
ID
Requirement
NFR1
Accessibility: WCAG 2.1 AA conformance, verified by automated and manual audit
NFR2
Performance: pages render in under 2 seconds on campus wifi
NFR3
Security: data encrypted in transit and at rest, no plaintext credentials stored
NFR4
Privacy: student data is never shared with third parties, and deletion is honored within 24 hours
NFR5
Reliability: external data failures degrade gracefully rather than breaking the page
NFR6
Maintainability: every integration is documented and tested



6. Acceptance Criteria
The project is accepted when all of the following are objectively true.

#
Criterion
How it is verified
AC1
Every shipped feature runs on live data, with no hardcoded values
Code review and data source inventory
AC2
20 or more WVU students have active accounts before the final presentation
Usage analytics
AC3
WCAG 2.1 AA conformance, with zero serious or critical automated violations
Audit report in the repository
AC4
Syllabus extraction accuracy is measured against hand-labeled ground truth and reported
Accuracy report in the repository
AC5
Privacy and security design is complete and covers storage, access, retention, and consent
Reviewed document
AC6
All six team deliverables submitted on time
Submission record
AC7
Every backlog issue closed as done meets its own Definition of Done checklist
Project board audit



7. Constraints
Constraint
Effect on scope
Fixed end date of December 4
Scope flexes, the date does not
No budget beyond free and student tiers
Hosting, database, and API usage must fit free plans
No institutional system access
Rules out anything depending on Banner, STAR, or DegreeWorks
Four person team with concurrent coursework
Roughly 6 to 8 hours per person per week
Course deliverable schedule
Team capacity is split between building and project management artifacts



8. Assumptions
Assumption
If it proves false
The public PRT status endpoint stays available and unauthenticated
That feature is cut and the dashboard drops one tile
Students can generate a read only Blackboard calendar share link
Deadline tracking shifts entirely to syllabus extraction
Syllabus extraction reaches usable accuracy on real syllabi
The feature becomes manual entry with assisted parsing
At least 20 students will pilot the product
Success criteria are renegotiated with the sponsor and reported honestly
All four team members stay available through December 4
Scope is cut to the foundation and deadline epics



9. Feasibility Summary
Dimension
Assessment
Economic
Feasible. All infrastructure fits free and student tiers.
Technical
Moderate risk. The team is familiar with the web stack, but syllabus extraction accuracy is unproven and is being validated by a timeboxed spike.
Operational
Feasible. The product fits existing student routines rather than requiring new behavior.
Schedule
Tight. The pilot gate in early November leaves limited slack before the final presentation.
Legal
Low risk. All data is public or student supplied, with no institutional records accessed.
Political
Low risk during the pilot. Any move toward university adoption would require ITS review.



10. Scope Change Control
The scope baseline in sections 3 and 4 is fixed. Changes follow this process:

Request. Any team member or stakeholder raises a GitHub issue labeled scope-change.
Impact assessment. The Project Manager assesses effect on schedule, team capacity, and the existing backlog.
Decision. The team approves, rejects, or defers it. Approval requires naming what is cut to pay for it.
Baseline update. Approved changes are committed to this document with the reason recorded.

Gold plating, meaning work not traceable to a deliverable in section 3, is treated as scope creep and is not accepted.


AI Use Note
Claude (Anthropic) was used to draft this scope statement, structured against the required components from the Module 1.4 Scope Management and Requirements Engineering lecture. The team supplied the scope boundaries, constraints, and assumptions, verified the data source claims, and edited the final version.


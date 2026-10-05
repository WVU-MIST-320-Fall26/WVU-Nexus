WVU Nexus: Epic Definitions
Six epics organize the product backlog. Every issue carries exactly one epic: label so the board can be grouped and filtered by epic.

Issues trace back to the deliverables in SCOPE.md. An issue that does not map to a deliverable is scope creep.
Operating premise
We build independently, design for institutional adoption, and pursue approval in parallel. Every feature runs on data we can obtain without permission: public WVU endpoints, public web sources, and data the student supplies about themselves. No deliverable depends on an approval we have not received.

Where a production version at WVU would work differently, we build the pilot version behind a swappable interface and record the end state as an architecture decision record. Authentication is the clearest case. WVU would use SSO, the pilot uses passwordless email sign-in restricted to mix.wvu.edu addresses, and the auth layer is isolated so the swap is small.


epic:foundation: Foundation & Platform
The application shell everything else depends on: accounts, deployment, and the automated checks that keep quality from becoming a last-week problem.

Covers: repository scaffold, authentication, database schema, hosting, CI pipeline Delivers: D1, D2 Done when: a student can create an account, sign in, and see an empty dashboard on the deployed site


epic:campus-data: Campus Data
Public WVU and Morgantown information that requires no institutional approval. The lowest risk epic and the first proof that the product runs on live data.

Covers: PRT status, academic calendar, dining and library hours, campus alerts Delivers: D3, D4 Done when: the dashboard shows current campus status pulled from live sources, and degrades gracefully when a source is down


epic:deadlines: Deadline Tracking
Importing and displaying assignment deadlines from the student's own Blackboard calendar export. The student supplies the link, so we never touch WVU credentials or servers.

Covers: calendar link connection, parsing, deduplication, unified deadline views Delivers: D5, D6 Done when: a student connects their calendar and sees their real assignments in one chronological list

Risk: Blackboard feeds are incomplete when professors leave dates in the syllabus only. Coverage is being measured before this epic is built out.


epic:syllabus: Syllabus Intelligence
Extracting assignments, due dates, and grade weights from student-uploaded syllabus PDFs. This is the highest value epic because it captures what Blackboard misses, and the highest risk because extraction accuracy is unproven.

Covers: PDF upload, text extraction, LLM parsing, student review and correction Delivers: D7, D8 Done when: a student uploads a syllabus, reviews what was extracted, corrects errors, and saves it

Gate: accuracy is measured against hand-labeled syllabi before full build. Below usable accuracy, this becomes assisted manual entry.


epic:insights: Academic Insights
Turning deadlines and grade weights into something actionable. A transparent, rule based risk indicator, not a machine learning model, because the training data for a real model requires institutional access we do not have.

Covers: risk calculation, course detail views, unified dashboard Delivers: D9, D10 Done when: a student sees a risk indicator per course and can see exactly why it says what it says


epic:trust: Trust & Adoption
Accessibility, privacy, and getting real students onto the product. These are workstreams rather than afterthoughts, because WCAG 2.1 AA is a procurement gate for university software and a pilot with no users produces no evidence.

Covers: accessibility audit and remediation, privacy and security design, consent flow, account deletion, pilot recruitment, usage analytics, and establishing what WVU permits Delivers: D11, D12, D13 Done when: the audit passes, the security design is written, 20 or more students are using the product, and we know in writing what WVU permits


Label reference
Label
Color
Purpose
epic:foundation
blue
Platform and infrastructure
epic:campus-data
green
Public campus data integrations
epic:deadlines
purple
Calendar import and deadline views
epic:syllabus
orange
Syllabus upload and extraction
epic:insights
teal
Risk indicator and dashboard
epic:trust
red
Accessibility, privacy, and pilot adoption


Supporting labels: type:spike for timeboxed research, blocked for work that cannot proceed, and scope-change for change requests.


AI Use Note
Claude (Anthropic) was used to draft these epic definitions and the label scheme. The team decided how to group the work, set the gates on the syllabus and deadline epics, and edited the descriptions.


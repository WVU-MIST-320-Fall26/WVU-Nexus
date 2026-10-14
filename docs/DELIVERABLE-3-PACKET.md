# WVU Nexus: Deliverable 3 Work Packet

**Sprint planning, story point estimation, and milestone setup**

Everything needed is in this file. Parts 1 through 7 are instructions and data. Part 8 records how the GitHub setup was applied.

**Numbering:** the GitHub issues for the backlog are **#3 through #23**. Issues #1 and #2 are closed housekeeping issues (Test Issue, Project Charter) and are not part of the backlog. Every issue number in this packet is the real GitHub number. Part 1 also shows each row's position (1 to 21) in the original backlog list.

---

## The headline finding

Estimating the backlog produced a number the team needs to see before anything else.

| | Story points |
|---|---|
| Total backlog | **124** |
| Realistic capacity, 3 sprints | **~72** (24 per sprint) |
| **Gap** | **~52 points** |

The backlog as written does not fit in the time remaining. That is not a reason to shrink the estimates. It is the scope, cost, time triangle from the Scrum lecture doing exactly what it is supposed to do: cost and time are fixed, so scope is the variable.

Part 6 lists what to cut. Bring that to the team before Sprint 2 planning.

---

## Part 1: Title conversion, user story to task verb form

The assignment asks for task verb form titles. The user story stays in the issue body, so nothing is lost. Spikes are identified by the `type:spike` label, not by a suffix in the title.

| Row | GitHub # | Old title | New title | Epic |
|---|:--:|---|---|---|
| 1 | #3 | Sign in with my WVU email, no password to create | **Implement passwordless email sign-in for WVU addresses** | foundation |
| 2 | #4 | Stay signed in across visits | **Implement persistent sessions behind a swappable auth module** | foundation |
| 3 | #5 | Deploy the app with CI running on every change | **Deploy the application with CI and automated accessibility checks** | foundation |
| 4 | #6 | See whether the PRT is running right now | **Integrate the WVU PRT status API** | campus-data |
| 5 | #7 | Check dining and library hours without opening another app | **Integrate dining and library hours from public sources** | campus-data |
| 6 | #8 | See the academic calendar and campus alerts | **Integrate academic calendar dates and campus alerts** | campus-data |
| 7 | #9 | SPIKE: measure Blackboard calendar coverage | **Measure Blackboard calendar coverage** | deadlines |
| 8 | #10 | Connect my Blackboard calendar with a share link | **Build the Blackboard calendar connection flow** | deadlines |
| 9 | #11 | Import and refresh calendar events automatically | **Automate calendar import and scheduled refresh** | deadlines |
| 10 | #12 | See all my deadlines in one chronological list | **Build the unified chronological deadline list** | deadlines |
| 11 | #13 | SPIKE: measure syllabus extraction accuracy | **Measure syllabus extraction accuracy** | syllabus |
| 12 | #14 | Upload a syllabus PDF | **Build syllabus PDF upload** | syllabus |
| 13 | #15 | Review and correct what was extracted from my syllabus | **Build the extraction review and correction screen** | syllabus |
| 14 | #16 | See a risk indicator for each course | **Implement the course risk indicator calculation** | insights |
| 15 | #17 | Understand why a course is flagged as risky | **Build the course detail view explaining risk factors** | insights |
| 16 | #18 | See deadlines, risk, and campus status on one dashboard | **Build the unified dashboard** | insights |
| 17 | #19 | Pass a WCAG 2.1 AA accessibility audit | **Conduct the WCAG 2.1 AA accessibility audit** | trust |
| 18 | #20 | Know what data is stored about me and consent to it | **Build the consent flow and write the privacy design** | trust |
| 19 | #21 | Delete my account and all of my data | **Implement account and data deletion** | trust |
| 20 | #22 | Recruit 20 pilot users and measure real usage | **Recruit pilot users and instrument usage analytics** | trust |
| 21 | #23 | Establish what WVU permits and find a champion | **Establish WVU data permissions and identify a champion** | trust |

---

## Part 2: Story point estimates

**These are starting values, not final.** The Scrum reading is explicit that developers estimate, not the PM or the product owner, and that private voting exists so nobody anchors on the loudest person. Run a planning poker session and change whatever the team disagrees with. A spread of 2 versus 8 on any item means two people read the requirement differently, and finding that is the actual point of the exercise.

**The scale used here:**

| Points | Meaning |
|---|---|
| 1 | A couple of hours. Trivial, well understood. |
| 2 | Half a day. |
| 3 | About a day. Clear requirements, known approach. |
| 5 | Two to three days. Some unknowns. |
| 8 | About a week. Significant complexity or uncertainty. |
| 13 | Too big to estimate confidently. Split it, or accept it spans sprints. |

Points measure complexity, uncertainty, and effort together, not hours.

| Issue | Title | Points | Why |
|:--:|---|:--:|---|
| #3 | Implement passwordless email sign-in | 8 | Email delivery, token expiry, rate limiting, domain restriction |
| #4 | Implement persistent sessions | 5 | Standard work, plus the swappable module design and an ADR |
| #5 | Deploy with CI and accessibility checks | 8 | Hosting, pipeline, axe integration, documentation |
| #6 | Integrate PRT status API | 3 | Documented public endpoint, main work is error handling and caching |
| #7 | Integrate dining and library hours | 5 | No clean API, likely scraping, holiday schedules are messy |
| #8 | Integrate academic calendar and alerts | 3 | Similar to above but simpler data |
| #9 | Measure Blackboard coverage | 3 | Timeboxed to 3 days, output is a decision |
| #10 | Build calendar connection flow | 5 | Validation, encrypted storage, user instructions with screenshots |
| #11 | Automate import and refresh | 8 | Scheduling, deduplication, handling deletions without losing edits |
| #12 | Build unified deadline list | 5 | Sorting, filtering, empty states, accessibility |
| #13 | Measure extraction accuracy | 5 | Timeboxed to 5 days, hand labeling ground truth is slow |
| #14 | Build syllabus PDF upload | 3 | Standard upload with validation |
| #15 | Build extraction review screen | 8 | Editable table, confidence flagging, nothing saves until confirmed |
| #16 | Implement risk indicator calculation | 8 | Designing a defensible formula is the hard part, not the code |
| #17 | Build course detail view | 5 | Must explain itself in plain language |
| #18 | Build unified dashboard | 8 | Composition, independent failure handling, performance, WCAG |
| #19 | Conduct accessibility audit | 8 | Manual keyboard and screen reader passes plus remediation |
| #20 | Build consent flow and privacy design | 5 | Document is most of the work |
| #21 | Implement account and data deletion | 3 | Straightforward if the data model is clean |
| #22 | Recruit pilot users and instrument analytics | 13 | Spans weeks, depends on other people, cannot be forced |
| #23 | Establish WVU permissions and champion | 5 | Mostly waiting on replies, low effort and high elapsed time |

**Total: 124 points.**

Issue #22 at 13 is deliberately left unsplit. The reading says 13 means too big to estimate confidently, and that is honest here. It could be split into "instrument analytics" and "run recruitment," and the team may want to.

---

## Part 3: Sprint field setup

Create a custom field named **Sprint**, type **Iteration**. The CLI cannot create iteration fields, so this is manual.

Project, then Settings, then **+ New field**, name it `Sprint`, type **Iteration**, duration **2 weeks**, start date **October 12, 2026**.

That produces:

| Sprint | Dates |
|---|---|
| Sprint 1 | Oct 12 to Oct 25 |
| Sprint 2 | Oct 26 to Nov 8 |
| Sprint 3 | Nov 9 to Nov 22 |

Also create the **Story Points** field: type **Number**. Then enter the values from Part 2.

---

## Part 4: Sprint 1 assignment

**24 points, balanced by owner.** Sprint 1 is deliberately foundation and spikes, because two epics rest on unverified assumptions and building on them before measuring would be a gamble.

| Issue | Title | Points | Owner |
|:--:|---|:--:|---|
| #5 | Deploy the application with CI and automated accessibility checks | 8 | Rodney |
| #9 | Measure Blackboard calendar coverage | 3 | MJ |
| #13 | Measure syllabus extraction accuracy | 5 | MJ |
| #23 | Establish WVU data permissions and identify a champion | 5 | Carter |
| #6 | Integrate the WVU PRT status API | 3 | Ethan |

**Load per person:** Rodney 8, MJ 8, Carter 5, Ethan 3.

Carter and Ethan carry lighter point loads on purpose. The Scrum Master runs process and the product owner runs backlog and stakeholder work, and neither of those shows up as story points. Say that out loud if anyone reads the board as uneven contribution.

**Sprint 1 goal, one sentence for the board:** *Prove the data sources work and get a deployed app with quality checks running.*

Everything else stays in the backlog with no sprint assigned.

---

## Part 5: Milestones

Three milestones exist in the repo under Issues, then Milestones.

| Milestone | Due date | Meaning |
|---|---|---|
| **M1: Foundation and Feasibility Proven** | Oct 25, 2026 | Deployed app, CI running, both spikes answered, WVU inquiry sent |
| **M2: Core Product Working** | Nov 8, 2026 | Deadlines and syllabus features working on live data |
| **M3: Pilot Live and Presentation Ready** | Nov 19, 2026 | Real users, accessibility audit passed, privacy design written |

**Why M3 is Nov 19 and not the Sprint 3 end date (Nov 22):** team presentations begin Nov 20, so the product gate has to land before the team presents. Sprint 3 still runs to Nov 22, but M3 work needs to be finished before the presentation window opens.

**Issue to milestone assignment:**

| Milestone | Issues |
|---|---|
| M1 (Oct 25) | #5, #6, #9, #13, #23 |
| M2 (Nov 8) | #3, #4, #7, #8, #10, #11, #12, #14, #15 |
| M3 (Nov 19) | #16, #17, #18, #19, #20, #21, #22 |

M1 holds 24 points, M2 holds 50, and M3 holds 50. M2 and M3 both exceed a realistic 24 point sprint. That is the gap, shown on purpose rather than hidden.

---

## Part 6: The capacity problem and what to do about it

**The math.** Four people, roughly 6 to 8 hours a week each on this course, two week sprints. That supports somewhere around 24 points per sprint. Three sprints is about 72 points.

The window from Nov 23 to Dec 4 adds roughly 12 points of capacity. Most of it is reserved for presentation prep and final deliverables rather than new features, and Thanksgiving falls inside it, so treat 12 as an upper bound. Build capacity is therefore roughly **72 to 84 points**.

The backlog is 124 points, so the gap is 40 to 52 points.

Three options, and they are the only three:

1. **Cut scope.** The only lever actually available, since the December date is fixed and the team cannot add people.
2. **Extend time.** Not possible. Dec 4 is the end.
3. **Lower the quality bar.** Rejected. Accessibility and privacy are what make the product adoptable, and cutting them defeats the purpose.

**Recommended cuts, 34 points:**

| Issue | Title | Points saved | Reasoning |
|:--:|---|:--:|---|
| #7 | Dining and library hours | 5 | Nice to have. Not core to the problem statement. |
| #8 | Academic calendar and alerts | 3 | Same. |
| #11 | Automate import and refresh | 8 | Manual refresh is acceptable for a pilot. Scheduling is the expensive part. |
| #17 | Course detail view | 5 | The risk indicator can ship without the explanation screen, though it is weaker. |
| #15 | Extraction review screen | 8 | **Conditional.** Cut #15 only if the syllabus extraction spike (#13) reports below usable accuracy. Decision date: end of Sprint 1, Oct 25. |
| #22 | Split pilot recruitment | 5 | Split analytics instrumentation from recruitment effort, taking the recruitment half from 13 to 8. |

**The arithmetic:** 5 (#7) + 3 (#8) + 8 (#11) + 5 (#17) + 8 (#15, conditional) + 5 (#22 split) = **34 points**.

Cutting #7, #8, #11, and #17 alone removes 21 points and costs the least. The other 13 points depend on a spike result (#15) and on how the pilot recruitment work is split (#22).

**Not available to cut:** account and data deletion (#21, 3 points) is a privacy commitment, not a scope choice, and stays in the plan.

**The residual.** 124 - 34 = 90 points against a build capacity of roughly 72 to 84. Even after every listed cut, the plan is **6 to 18 points over**. One more mid-size item has to go, or one epic ships partial. Which one is a team decision, and this packet does not propose it.

**What to do with this:** do not decide it alone. Take it to the team as a scope conversation, record the decision in `SCOPE.md` under change control, and log it for the reflective essay. A documented, data-driven scope cut is one of the strongest artifacts this course can produce.

---

## Part 7: View configuration

### Table view

1. Open the Table view
2. **Group by:** `Sprint`
3. **Sort by:** `Story Points`, descending
4. Confirm visible fields include Title, Assignees, Status, Labels, Story Points, Sprint, Milestone

### Roadmap view

1. Open the Roadmap view
2. **Group by:** `Milestone`
3. **Date fields:** set to `Start date` and `Target date`
4. For every issue, set Start date and Target date to its sprint's dates:

| Sprint | Start date | Target date |
|---|---|---|
| Sprint 1 | 2026-10-12 | 2026-10-25 |
| Sprint 2 | 2026-10-26 | 2026-11-08 |
| Sprint 3 | 2026-11-09 | 2026-11-22 |

Alternatively, if the Roadmap view offers `Sprint` as its date source, point it there and the dates come from the iteration automatically.

5. Read the result. Any milestone whose bars run past its due date is a schedule problem. With the current plan, M2 and M3 will both look overloaded, which is the visual version of the capacity gap in Part 6. M3 is the tightest: its due date is Nov 19, three days before Sprint 3 ends, so any M3 issue whose bar runs to Nov 22 is late against its milestone.

---

## Part 8: How the GitHub setup was applied

The renames, milestones, and milestone assignments were applied directly with the GitHub CLI (`gh issue edit` and `gh api`), not with a script, and each result was checked against live data afterward. The original draft of this packet included a script that assumed the backlog was issues #1 through #21. That assumption was wrong (the backlog is #3 through #23), so the script would have renamed closed issues and shifted every title. It has been removed. **Do not rerun any script based on the old numbering.**

Still done by hand in the GitHub Project UI: the Sprint iteration field, the Story Points values if not yet entered, and the view settings in Part 7.

The GitHub issues themselves are the source of truth for titles, story points, and milestones. This packet records the plan and the reasoning behind it.

---

## AI Use Note

Claude was used to convert issue titles to task verb form, draft initial story point estimates with written reasoning for each, propose the sprint and milestone structure, and calculate the capacity gap between the backlog and the time remaining. The story point values are proposed starting values pending a team planning poker session, and the team would adjust them wherever its own estimates differ. The capacity finding has not yet been acted on. The team would decide which scope to cut, and when, as a scope conversation recorded under change control.

# WVU Nexus: Lessons Learned

**Project:** WVU Nexus, MIST 320 Fall 2026
**Team:** Ethan Weaver (PM), MJ F (Lead BA), Carter S (Scrum Master, QA), Rodney E (Systems Architect)
**Period:** September 2026 to December 2026, three 2-week sprints plus chartering

---

## 1. The single most important thing we learned

**Estimating a backlog is how you find out whether a plan is real.**

For five weeks we had a scope statement, six epics, and twenty-one issues, and the plan looked sound. Then we applied story points and the backlog came to 124 points against a realistic capacity of 72 to 84. The plan had been roughly 40 to 50 points over capacity the entire time and nothing before the estimation exercise revealed it.

Nothing we did later mattered as much as finding that in week 5 rather than week 12. Everything downstream, the scope cuts, the deferral of CR-001, the re-baseline recommendation, came from that one number.

---

## 2. What worked

### Front-loading uncertainty as timeboxed spikes

Two of our six epics depended on data sources nobody had tested. We scheduled the measurements as spikes in Sprint 1, ahead of any feature work, with "a decision" as the deliverable rather than code. Designing the plan that way was correct. We did not execute them, which section 3 covers, but the structure was right and we would do it again.

### Treating milestones and sprints as separate objects

Course deliverable dates and product delivery gates were tracked separately from the start. They do not align cleanly and pretending otherwise would have hidden conflicts. It surfaced a real one: our M3 product milestone was originally set to the end of Sprint 3, which falls after team presentations begin. We moved M3 to November 19 so the product gate lands before we present rather than after.

That conflict was invisible on the board. It only appeared when we read the README schedule against the milestone dates. **Artifacts catch things tooling does not.**

### Verification before destructive operations

Before a bulk rename of all 21 issues, we checked the live issue numbers against our plan and found they were offset by two. Our plan assumed issues 1 through 21. The real backlog was #3 through #23, because two closed test issues occupied the first slots. Running the operation unchecked would have renamed closed issues and shifted every title one row off, and we would have discovered it by reading a board that looked subtly wrong.

A read-only check became a standing step before any batch operation. It caught three separate errors over the semester, including an arithmetic mistake in our own capacity analysis where a cut list stated at roughly 50 points actually totaled 34.

### Documenting scope decisions with reasons attached

Every exclusion in our scope statement carries a reason. "No native mobile app" invites argument. "No native mobile app because delivery capacity" ends it. When the Vice Provost's change request arrived, we had a baseline to measure it against and a precedent for how to say no constructively.

### Deferring rather than rejecting

CR-001 was strategically correct and operationally impossible. Rejecting it would have forfeited the most senior stakeholder the project attracted. We deferred it, approved a 5-point architectural provision so the work would later be an extension rather than a rewrite, and left the deferred scope visible on the board. That is a better answer than either a rushed partial implementation or a flat no.

---

## 3. What did not work

### We closed two spikes without running them

Issues #9 and #13 were timeboxed spikes whose entire output was a go or no-go decision. Both were closed with zero Definition of Done checkboxes ticked and no measurement recorded.

This is the worst thing that happened on the project. Two of our six epics still rest on unverified assumptions, the extraction review screen has no basis for a keep-or-cut decision, and any estimate touching those epics is provisional.

We chose to record it openly rather than quietly, posting a comment on each issue stating that the spike was not run and naming the consequence. **An honest closed loop is worth more than a silently closed issue**, but the better outcome was running them.

### Work concentrated on one person

For most of the semester the majority of commits and board activity came from a single team member. The board is the contribution record and it under-represented three of us. We redistributed in Sprint 3, but later than we should have.

The underlying cause was speed. It was faster for one person to do a thing than to hand it off, and that is true every single time, which is exactly why it compounds.

### Our estimates were never team estimates

Story points were drafted rather than voted on. The Scrum literature is explicit that developers estimate and that private voting exists so nobody anchors on the loudest voice. We never ran a proper planning poker session, which means our velocity math rested on numbers nobody collectively owned. Where two people would have voted 2 and 8 on the same item, we never found out, and that disagreement is the actual value of the exercise.

### We updated the board in batches

Status changes were applied at sprint close rather than as work progressed. Our own board convention says status reflects reality, not intentions, and batch updating breaks it. The visible consequence is in our burn-up chart: the completed line barely moves and then jumps, because it tracks when statuses were changed rather than when work happened.

### We identified a risk and did not mitigate it

In Deliverable 1 we wrote that one person submitting for the whole team is an unmitigated single point of failure on shared points. In November we submitted a deliverable the morning after it was due because each of us assumed someone else was posting it.

We named the risk, wrote it down, assigned nobody, and it fired. **A risk register that nobody acts on is documentation, not risk management.**

### Communication failures were the expensive ones, not technical ones

Every significant problem this semester came from information not moving between people: the numbering mismatch, the unassigned submission, the spikes nobody confirmed, the estimates nobody voted on. None of our failures were technical.

---

## 4. GitHub Projects as an enterprise PM tool

### Where it excelled

**Issues as the single source of truth.** Work items, acceptance criteria, discussion, and the commit history live in one place. A story point value, an owner, a sprint, a milestone, and the conversation that produced them are all one object. Tools that separate the plan from the work force reconciliation; this does not.

**Custom fields are genuinely flexible.** Story Points as a number field, Sprint as an iteration field, Workstream and Priority as single selects. We built a working Scrum and Kanban hybrid without buying anything.

**The iteration field is well designed.** Define a cadence once and it generates repeating time blocks with a current-sprint indicator, rather than typing dates onto every item.

**Built-in automation is enough for most needs.** Auto-add to project, set status on close, archive stale items. Our board stayed roughly accurate without anyone babysitting it.

**The GraphQL API is complete.** Anything the interface does can be scripted. We used it for bulk renames, milestone assignment, and setting story points across twenty-one items.

**It is free**, which for a student team is not a minor point.

### Where it fell short, and what we did about it

| Limitation | Impact | Our workaround |
|---|---|---|
| WIP limits are advisory, not enforced | The board flags an over-limit column but does not stop you | Documented the limits in the project README as a team agreement so they existed independent of tooling |
| Iteration fields cannot be created via CLI or REST | The one piece of our board setup that could not be scripted | Created manually in the web interface |
| No "cancelled" state by default | Deferred work sitting in Done inflated our apparent velocity by 8 points and corrupted our first velocity reading | Added a custom `Cancelled / Deferred` status option |
| Insights charts count items, not story points | Our entire analysis is in points, so the default burn-up did not match our report | Configured a custom chart and added a caption explaining what the chart includes that the earned value figures exclude |
| No native EVM, no burndown, no capacity planning | PV, EV, AC, SPI, CPI, EAC and ETC all computed by hand | Maintained the EVM analysis as a markdown report in the repository |
| Roadmap requires date fields populated per item | The Gantt view renders empty until someone fills in dates | Set start and target dates from the sprint boundaries |
| Bulk operations require GraphQL | Simple changes across many items are not simple | Scripted them, which introduced its own risk, see the off-by-two incident above |

### The honest assessment

**GitHub Projects is an excellent execution board and a weak enterprise PM tool.**

It is outstanding at the thing closest to the work: what is being built, by whom, in what state. Its integration with issues and commits is better than anything a separate tool can offer, because the plan and the work are the same objects.

It is weak at the layer above that: portfolio views, resource and capacity planning, earned value, dependency management, cost tracking, baselining, and formal change control. Every one of those we did in markdown files beside the board rather than in it.

For a team of four on one product, that tradeoff is clearly worth it. For a program manager overseeing multiple teams with a budget and a compliance obligation, it is not. A real enterprise would pair it with something else, or accept that the governance layer lives in documents.

---

## 5. Advice to future teams

1. **Estimate the whole backlog in week 2, not week 5.** It is the cheapest thing you can do and it tells you whether your plan is real. Everything else depends on knowing that number.

2. **Assign the submission.** Make it a board item with one named owner and a confirmation step. We wrote down that this was a risk and still got caught by it.

3. **Run your spikes.** A spike you skip is an assumption you shipped. If you genuinely cannot run it, write that down in the issue and say what it means, because silence in a closed issue is worse than a bad result.

4. **Let the slower person do it.** Every time it is faster to do something yourself. That is exactly why the work concentrates, and the board is the contribution record at peer evaluation.

5. **Update the board when the work happens.** Batch updates at sprint close produce charts that lie about your process, and the charts are what you present.

6. **Write the reason next to every scope decision.** A boundary without a reason gets relitigated. A boundary with a reason holds.

7. **Verify before any bulk operation.** Check live state against your plan first. We caught three errors this way, any one of which would have been painful to untangle.

8. **Report variance early.** An SPI of 0.62 disclosed in week 9 with a recovery plan is a managed project. The same number discovered at the final presentation is a failed one.

9. **Nearly every failure will be a communication failure.** Plan for that, not for technical risk.

---

## AI Use Note

Claude (Anthropic) was used to structure this retrospective and draft its language from the team's documented project events, board history, and prior deliverables. The team identified the lessons, confirmed each account against what actually happened, and wrote the advice in section 5 from its own experience.

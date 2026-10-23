# Change Impact Assessment: Multi-Institution Support

**Change Request ID:** CR-001
**Requesting Stakeholder:** Vice Provost, West Virginia University
**Prepared by:** Ethan W, Project Manager
**Date:** October 2026
**For review by:** Change Control Board, prior to Sprint 3 planning
**Team recommendation:** **DEFER**, with a 5-point architectural provision approved now

---

## 1. The request

Make WVU Nexus available across all WVU System institutions rather than Morgantown alone. The interface should be dynamic, showing each student only the campus services relevant to their own institution instead of a single shared UI.

The WVU System includes WVU Morgantown, WVU Potomac State College in Keyser, and WVU Institute of Technology in Beckley. The product as currently scoped assumes a single campus.

---

## 2. Why this request is strategically valuable

This assessment recommends deferring the work, so it is worth stating plainly that the request itself is good and the requester matters.

- A Vice Provost is the most senior stakeholder the project has attracted. Our charter lists "a named champion inside the university" as an adoption workstream, and this is that champion arriving on their own.
- Multi-institution support is the correct long-term direction. A tool that serves one campus is a student project. A tool that serves a system is infrastructure.
- The request validates the core premise, that the fragmentation problem is real and visible to administration.

Deferring the scope should not mean deferring the relationship. Section 8 covers that.

---

## 3. Impact analysis

### 3.1 Scope impact

The change is not additive at the edges. It touches the data model, every integration, the interface layer, and onboarding.

| Area | Impact |
|---|---|
| Data model | Institution becomes a first-class entity. Every user, data source, and campus service needs an institution association. |
| Campus data integrations | Every integration becomes institution-scoped. The PRT exists only in Morgantown. Dining and library hours differ per campus. Mountain Line serves Morgantown only. |
| User interface | Conditional rendering throughout. Every campus feature needs show/hide logic driven by the student's institution. |
| Onboarding | Students must be identified by institution, which the current design does not do. |
| Testing | Test surface multiplies by the number of institutions supported. |
| Accessibility audit | Each institution-specific view is a separate surface to audit. |
| Privacy design | Institutional affiliation is new personal data, requiring updated consent language. |

### 3.2 A technical finding the request surfaces

**Our authentication design cannot identify a student's institution.**

The pilot uses passwordless sign-in restricted to `@mix.wvu.edu`. Our current understanding is that this domain is used across WVU System institutions rather than being unique to Morgantown, which means the email address alone does not tell us which campus a student attends.

**This needs verification before any estimate is treated as firm.** If the domain is shared, institution detection requires either a student-selected campus at onboarding, which is simple but unverified and users get it wrong, or an institutional directory lookup, which requires the institutional access our scope explicitly excludes.

### 3.3 A data availability risk

The project's core constraint is that we build only on data we can legitimately obtain without institutional approval. That constraint was verified for Morgantown. **It has not been verified for Potomac State or WVU Tech.**

We do not currently know whether those campuses publish dining hours, library hours, academic calendars, or transit data in retrievable form. If they do not, the dynamic interface would show those students a largely empty product, which is worse than not supporting them at all.

A timeboxed spike would be required before committing to the work.

### 3.4 Effort estimate

| Work item | Points |
|---|---|
| Spike: verify data source availability at Potomac State and WVU Tech | 5 |
| Institution entity in the data model, user association | 5 |
| Institution selection at onboarding, with the auth finding resolved | 3 |
| Scope all campus data integrations by institution | 8 |
| Dynamic interface rendering by institution | 8 |
| Testing across three institutions | 5 |
| Updated privacy and consent language for institutional data | 2 |
| **Total** | **36** |

Estimates are team-proposed and carry the same uncertainty as the rest of the backlog. The spike is listed first because the three items below it depend on its result.

### 3.5 Schedule and capacity impact

This is the decisive section.

| | Story points |
|---|---|
| Current backlog | 124 |
| Available capacity, Sprints 1 to 3 plus the Nov 23 to Dec 4 window | 72 to 84 |
| **Existing gap before this request** | **40 to 52 over** |
| This change request | +36 |
| **Resulting backlog** | **160** |
| **Resulting gap** | **76 to 88 over** |

The project is already over capacity. Accepting this request as specified would roughly double the overage. Delivering it within the current schedule would require cutting approximately two full epics and abandoning the pilot user target, which is the project's primary success criterion.

The December 4 date is fixed and the team cannot add people. Scope is the only variable.

### 3.6 Quality and risk impact

- **Pilot at risk.** Recruiting 20 active users is our evidence base for the final presentation. Work diverted to multi-institution support comes directly out of it.
- **Accessibility at risk.** WCAG 2.1 AA conformance is a procurement gate. More surfaces means more audit work, and the audit is already late in the schedule.
- **Spreads a thin product thinner.** The current risk is shipping one campus experience that is good. The new risk is shipping three that are not.
- **Introduces dependency on unverified data.** See 3.3.

---

## 4. Options considered

### Option A: Approve as requested

Full multi-institution support with dynamic interface, delivered by December 4.

**Effort:** 36 points
**Assessment:** Not feasible. Would require cutting roughly two epics and the pilot. The team does not recommend this.

### Option B: Approve a reduced version

Institution as a data field with campus-scoped data, but no dynamic interface. Students see all features, with campus-specific data where it exists.

**Effort:** approximately 13 points
**Assessment:** Feasible only by cutting an equivalent 13 points elsewhere, on top of the cuts already required. Delivers a partial version of what was asked, and still depends on the unresolved data availability question in 3.3.

### Option C: Defer, with an architectural provision now

Defer the feature past December 4. Approve a small change now so the product is not architecturally hostile to it later: institution as a field on the user record and on each data source, populated with a single default value.

**Effort:** approximately 5 points
**Assessment:** Recommended. Preserves the option at low cost, keeps the December scope intact, and gives the Vice Provost a concrete answer rather than a refusal.

### Option D: Reject

**Assessment:** Not recommended. The request is strategically correct and the relationship is valuable. Rejecting outright forfeits both.

---

## 5. Recommendation

**DEFER**, with Option C's 5-point architectural provision approved for Sprint 2 or Sprint 3.

Reasoning:

1. **Capacity.** The backlog already exceeds available capacity by 40 to 52 points. This request would roughly double that. Accepting it would guarantee that nothing ships well.
2. **Unverified foundations.** We do not know whether the required data exists at the other campuses. Committing to scope that depends on unverified sources contradicts a standing project principle.
3. **The architectural provision is cheap insurance.** Five points now means the eventual work is an extension rather than a rewrite.
4. **Deferral is not refusal.** The request lands in a post-semester roadmap with a real estimate attached, which is a more credible answer than a rushed partial implementation.

---

## 6. If the CCB approves instead

Should the CCB approve Option A or B over this recommendation, the team requires a corresponding scope reduction of equal size, and the following would be cut:

| Cut | Points |
|---|---|
| Academic risk indicator and course detail view | 13 |
| Unified dashboard | 8 |
| Syllabus extraction review screen | 8 |
| Automated calendar refresh | 8 |
| **Total** | **37** |

This removes the academic insights epic entirely. The product would become a campus information and deadline aggregator across three institutions, rather than a single-campus tool that tells a student where they are at risk.

The team's view is that this is a worse product, but the trade is stated so the CCB can decide with the cost visible.

---

## 7. Residual risk if deferred

| Risk | Mitigation |
|---|---|
| The Vice Provost reads deferral as lack of interest | Written response within one week, with the roadmap and estimate attached. See section 8. |
| Architecture drifts further from multi-tenancy | Approve the Option C provision now. |
| Another team or vendor takes the opportunity | Accept. We cannot staff it this semester. |

---

## 8. Relationship action, regardless of decision

Independent of the scope decision, the team recommends:

1. A written response to the Vice Provost within one week, stating that the request is on the roadmap with a 36-point estimate and explaining the capacity constraint plainly.
2. Requesting a meeting. This is the champion the adoption workstream has been looking for, and our open issue on identifying one should be updated to reflect that they approached us.
3. Asking whether their office can help with the data availability question in 3.3, which is institutional knowledge we do not have and cannot easily obtain.

A deferred feature and an engaged Vice Provost is a better outcome than a rushed feature and a stakeholder who never hears from us again.

---

## 9. CCB decision

| Field | Entry |
|---|---|
| Decision | ☐ Approve ☐ Reject ☐ Defer |
| Decided by | |
| Date | |
| Conditions | |
| Scope traded out, if approved | |

Approved changes update the scope baseline in `SCOPE.md` with the reason recorded.

---

## AI Use Note

Claude (Anthropic) was used to draft the structure of this impact assessment, the effort estimate, and the option analysis. The team reviewed the estimate, verified the capacity figures against the current backlog, and made the deferral recommendation. The authentication and data availability findings in sections 3.2 and 3.3 are flagged as requiring verification and have not yet been confirmed.


# WVU-Nexus Risk Register

**Project Name:** WVU-Nexus  
**Project Manager:** Carter & Rodney  
**Date Created:** 2026-10-26  
**Last Updated:** 2026-11-02

## Risk Register Table

| ID | Risk Description | Root Cause | Category | Probability (1-3) | Impact (1-3) | Risk Score | Response Strategy | Mitigation Plan | Owner | Status | Last Update |
|----|-----------------|------------|----------|-------------------|--------------|------------|-------------------|-----------------|-------|--------|------------|
| R-01 | External data sources or APIs may be unavailable or access may be restricted. | The product depends on public WVU sources (PRT status, dining and library hours, academic calendar, alerts) that the team does not control and has no access agreement for, and institutional system access is out of scope. | Technical | 2 (Medium) | 3 (High) | 6 | Mitigate | Validate data availability and permissions early; document fallback options. | Technical Team | Active | 2026-11-02 |
| R-02 | Syllabus extraction may produce inaccurate deadlines or omit important information. | Syllabi are uploaded PDFs with no standard format, so each instructor presents deadlines and grade weights differently and extraction has no consistent pattern to rely on. | Quality | 2 (Medium) | 3 (High) | 6 | Mitigate | Test representative syllabi, measure extraction accuracy, document errors, and provide manual correction. | Data Team | Active | 2026-11-02 |
| R-03 | Blackboard calendar data may not include all deadlines students need to track. | The calendar export only contains items instructors enter as dated events in Blackboard, so deadlines posted only in syllabi or announcements never reach it. | Technical | 2 (Medium) | 3 (High) | 6 | Mitigate | Measure calendar coverage and document missing deadline types before relying on the integration. | Data Team | Active | 2026-11-02 |
| R-04 | The Vice Provost's request for multi-institution support may expand project scope and delay existing milestones. | The backlog was already over capacity (124 points against 72 to 84 available) before the request, and a senior stakeholder request creates pressure to accept work the schedule cannot absorb. | Scope | 3 (High) | 3 (High) | 9 | Control | Validate requirements, estimate effort, document the CCB decision, and do not commit unapproved work. | Project Team | Active | 2026-11-02 |
| R-05 | Institution identification or incomplete app mappings may cause students to see incorrect or missing app information. | Sign-in uses @mix.wvu.edu addresses, which appear to be shared across WVU System campuses, so the email address alone cannot identify which institution a student attends. | Technical | 2 (Medium) | 3 (High) | 6 | Mitigate | Confirm supported institutions, validate institution identity, maintain approved mappings, and define fallback behavior. | Technical Team | Active | 2026-11-02 |
| R-06 | Institution-specific display rules may fail to enforce appropriate data authorization. | Show and hide logic in the interface can be mistaken for access control if authorization is not also enforced where the data is served. | Security | 1 (Low) | 3 (High) | 3 | Mitigate | Enforce authorization at the appropriate backend or data layer and test access controls independently of the interface. | Technical Team | Active | 2026-11-02 |
| R-07 | Integration defects or insufficient regression testing may break existing functionality. | Each new integration and campus-specific variant multiplies the test surface, while testing time inside two-week sprints is limited. | Quality | 2 (Medium) | 3 (High) | 6 | Mitigate | Define acceptance criteria, run available automated checks, and test integrations and existing features before release. | QA / Technical Team | Active | 2026-11-02 |
| R-08 | Limited team capacity or underestimated effort may delay the November 19 milestone. | M3 is due November 19 so the product is finished before presentations begin November 20, but Sprint 3 runs through November 22 and the backlog already exceeds team capacity. | Schedule | 2 (Medium) | 3 (High) | 6 | Mitigate | Review sprint progress, prioritize high-value work, track blockers, and reassess scope and schedule before Sprint 3. | Project Team | Active | 2026-11-02 |


## AI Use Note

ChatGPT (OpenAI) was used to draft this risk register, including the table structure, the identified risks, and the suggested mitigations. The team is reviewing each risk for relevance and setting the final probability, impact, owner, and status values.

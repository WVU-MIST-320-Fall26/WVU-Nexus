
# WVU-Nexus Risk Register

**Project Name:** WVU-Nexus  
**Project Manager:** Carter & Rodney  
**Date Created:** 2026-10-26  
**Last Updated:** 2026-10-26

## Risk Register Table

| ID | Risk Description | Category | Probability (1-3) | Impact (1-3) | Risk Score | Response Strategy | Mitigation Plan | Owner | Status | Last Update |
|----|-----------------|----------|-------------------|--------------|------------|-------------------|-----------------|-------|--------|------------|
| R-01 | External data sources or APIs may be unavailable or access may be restricted. | Technical | 2 (Medium) | 3 (High) | 6 | Mitigate | Validate data availability and permissions early; document fallback options. | Technical Team | Active | 2026-10-26 |
| R-02 | Syllabus extraction may produce inaccurate deadlines or omit important information. | Quality | 2 (Medium) | 3 (High) | 6 | Mitigate | Test representative syllabi, measure extraction accuracy, document errors, and provide manual correction. | Data Team | Active | 2026-10-26 |
| R-03 | Blackboard calendar data may not include all deadlines students need to track. | Technical | 2 (Medium) | 3 (High) | 6 | Mitigate | Measure calendar coverage and document missing deadline types before relying on the integration. | Data Team | Active | 2026-10-26 |
| R-04 | The Vice Provost's request for multi-institution support may expand project scope and delay existing milestones. | Scope | 3 (High) | 3 (High) | 9 | Control | Validate requirements, estimate effort, document the CCB decision, and do not commit unapproved work. | Project Team | Active | 2026-10-26 |
| R-05 | Institution identification or incomplete app mappings may cause students to see incorrect or missing app information. | Technical | 2 (Medium) | 3 (High) | 6 | Mitigate | Confirm supported institutions, validate institution identity, maintain approved mappings, and define fallback behavior. | Technical Team | Active | 2026-10-26 |
| R-06 | Institution-specific display rules may fail to enforce appropriate data authorization. | Security | 1 (Low) | 3 (High) | 3 | Mitigate | Enforce authorization at the appropriate backend or data layer and test access controls independently of the interface. | Technical Team | Active | 2026-10-26 |
| R-07 | Integration defects or insufficient regression testing may break existing functionality. | Quality | 2 (Medium) | 3 (High) | 6 | Mitigate | Define acceptance criteria, run available automated checks, and test integrations and existing features before release. | QA / Technical Team | Active | 2026-10-26 |
| R-08 | Limited team capacity or underestimated effort may delay the November 19 milestone. | Schedule | 2 (Medium) | 3 (High) | 6 | Mitigate | Review sprint progress, prioritize high-value work, track blockers, and reassess scope and schedule before Sprint 3. | Project Team | Active | 2026-10-26 |


## AI Use Note

ChatGPT (OpenAI) was used to assist in drafting the risk register, including identifying potential technical and operational risks, organizing the risk register table, and suggesting mitigation strategies. The team is responsible for reviewing the identified risks, verifying their relevance to the WVU-Nexus project, and updating likelihood, impact, ownership, and status to reflect the team's actual assessment.

# RACI Matrix: WVU Nexus

Who does what on each major deliverable. Internal team working document.

**R = Responsible** (does the work) · **A = Accountable** (owns the outcome, one per row) · **C = Consulted** (input before) · **I = Informed** (told after)

## Who's who

| Code | Role | Person |
|---|---|---|
| ES | Executive Sponsor | Katherine Kopp, instructor |
| PM | Project Manager | Ethan W |
| BA | Lead Business Analyst | MJ F |
| SM | Scrum Master, also owns quality assurance | Carter S |
| SA | Systems Architect | Rodney E |
| DEV | Developers / Engineers | Full team |
| EU | End Users | WVU student pilot group |

The team carries four roles rather than five, so quality assurance duties sit with the Scrum Master.

## Matrix

| Deliverable | ES | PM | BA | SM | SA | DEV | EU |
|---|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| Project charter | C | A | R | C | C | I | I |
| Requirements and user stories | I | C | A | I | C | I | R |
| Project schedule and sprint plan | I | A | C | R | C | C | — |
| Risk register | C | A | C | R | C | I | I |
| System architecture and design | I | C | I | I | A | R | — |
| Development | I | I | C | C | A | R | — |
| Testing and quality assurance | I | I | I | A | C | R | — |
| Accessibility audit | I | I | C | A | C | R | C |
| Privacy and security design | C | C | C | R | A | C | I |
| Deployment | I | I | I | C | A | R | — |
| Pilot recruitment and user feedback | I | A | R | I | I | C | R |
| Status reporting | A | R | C | C | I | I | I |
| Team presentation | C | A | R | C | R | C | I |
| Final delivery and closeout | C | A | C | R | R | R | I |

## Rules we follow

1. **One A per row.** If two people think they own something, the PM settles it before work starts.
2. **Accountable still has to check.** Delegating the work does not mean skipping the review.
3. **Consulted means before, informed means after.** If someone marked C first sees the work at final review, we did it wrong.
4. **Watch the single R rows.** Architecture, development, and deployment all run through Rodney. If he is unavailable, the build stops. We write architecture decisions down and have a second person review integration work.
5. **Quality is not one person's job.** Carter is accountable for testing and accessibility, but each of us tests our own work before marking it done.

## AI Use Note

Claude (Anthropic) was used to draft this matrix structure and an initial set of assignments. The team assigned the roles, reviewed every row, and decided how to cover quality assurance with four roles instead of five.

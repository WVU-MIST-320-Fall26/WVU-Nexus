# WVU Nexus: Metrics and Earned Value Report

**Reporting period:** Sprint 1 and Sprint 2 (Oct 12 to Nov 8, 2026)
**Prepared by:** Ethan W, Project Manager
**Date:** November 9, 2026
**Status:** Baseline measurement through Sprint 2 close

---

## 1. Measurement basis and assumptions

These assumptions are stated up front because every figure below depends on them.

| Assumption | Value | Note |
|---|---|---|
| Unit of measure | Story points | Agile EVM convention. No labor dollars are tracked on this project. |
| Budget at Completion (BAC) | 121 points | 116 points of active backlog plus the 5-point CCB-approved architectural provision |
| Project length | 3 sprints | Sprint 1 Oct 12-25, Sprint 2 Oct 26-Nov 8, Sprint 3 Nov 9-22 |
| Planned Value basis | 2/3 of BAC at Sprint 2 close | Two of three sprints elapsed, linear planned distribution |
| Actual Cost basis | 2/3 of BAC at Sprint 2 close | Two of three sprints of team capacity consumed |

**Excluded from BAC:** issues #7 and #8 (8 points), cancelled under the Sprint 2 backlog grooming decision with the reason recorded on each issue.

**A note on AC equaling PV.** Because this project's only resource is fixed team capacity and no labor cost is tracked separately, consumed capacity equals planned capacity at any point in time. This makes CPI numerically identical to SPI. That is a property of the measurement basis, not a coincidence in the data, and it means CPI here reads as efficiency of capacity use rather than cost control in the financial sense.

---

## 2. Velocity analysis

| Sprint | Committed | Completed | Variance |
|---|:--:|:--:|:--:|
| Sprint 1 | 24 | 24 | 0 |
| Sprint 2 | 26 | 26 | 0 |
| **Average** | **25** | **25** | **0** |

**Trend:** velocity rose from 24 to 26, an 8 percent increase. Both sprints delivered exactly what was committed.

**Interpretation.** Two data points do not establish a trend, and the apparent improvement is within normal sprint-to-sprint variation. The defensible planning figure for Sprint 3 is the two-sprint average of **25 points**, not the Sprint 2 result of 26. Planning against the most recent sprint rather than the average is a common forecasting error that builds optimism bias into the schedule.

The useful signal here is commitment accuracy. Hitting committed scope exactly in both sprints suggests sprint-level planning is sound. The project's problem is not sprint execution. It is total scope against total capacity, which section 4 quantifies.

### Burn-up chart

> **[INSERT BURN-UP CHART IMAGE HERE]**
>
> From the project board: Insights, then the burn-up chart, filtered to the Status field. Export or screenshot and commit the image to `docs/images/`, then reference it here.

**What the chart shows:** the scope line sits flat at 121 points while the completed line rises from 0 to 24 to 50. The gap between the two lines at Sprint 2 close is 71 points, and only one sprint remains to close it.

---

## 3. Earned Value Management through Sprint 2

### 3.1 Core metrics

| Metric | Formula | Value |
|---|---|---:|
| Budget at Completion (BAC) | Total planned scope | 121.0 pts |
| Planned Value (PV) | 2/3 × BAC | 80.7 pts |
| Earned Value (EV) | Points actually completed | 50.0 pts |
| Actual Cost (AC) | 2/3 × BAC | 80.7 pts |

### 3.2 Variances

| Metric | Formula | Value | Reading |
|---|---|---:|---|
| Schedule Variance (SV) | EV − PV | −30.7 pts | Behind schedule |
| Cost Variance (CV) | EV − AC | −30.7 pts | Over budget |

### 3.3 Performance indices

| Index | Formula | Value | Reading |
|---|---|---:|---|
| Schedule Performance Index (SPI) | EV ÷ PV | **0.62** | Earning 62 cents of planned progress per unit of schedule consumed |
| Cost Performance Index (CPI) | EV ÷ AC | **0.62** | Earning 62 cents of value per unit of capacity spent |

Both indices sit well below 1.0. The project has consumed two thirds of its capacity and delivered 41 percent of its scope.

**Why the indices are low.** Sprint execution was not the cause. Both sprints delivered exactly what was committed. The gap is that the baseline scope of 121 points was never achievable at a demonstrated velocity of 25 points per sprint across three sprints, which supports at most 75 points. The plan was over-committed from the start, and the capacity analysis in Deliverable 3 flagged this at the time.

---

## 4. Sprint 3 forecast

### 4.1 EVM forecast

| Metric | Formula | Value |
|---|---|---:|
| Estimate at Completion (EAC) | BAC ÷ CPI | 195.2 pts |
| Estimate to Complete (ETC) | EAC − AC | 114.5 pts |
| Variance at Completion (VAC) | BAC − EAC | −74.2 pts |

**Reading.** At current efficiency, completing the full 121-point scope would require 195 points of total capacity, which is 74 points more than the project has. The ETC of 114.5 points would require roughly 4.6 additional sprints beyond Sprint 2 at a velocity of 25.

### 4.2 Capacity forecast, the practical view

The EVM forecast assumes the schedule could extend. It cannot. December 4 is fixed.

| | Points |
|---|---:|
| Scope remaining after Sprint 2 | 71 |
| Sprint 3 capacity at average velocity | 25 |
| **Projected shortfall** | **46** |

**Projected delivery at project close: 75 of 121 points, or 62 percent of baseline scope.**

Approximately 46 points of committed scope will not be delivered within the schedule.

### 4.3 What this means for Sprint 3 planning

Sprint 3 is loaded with all 71 remaining points, per the Deliverable 6 requirement that only deferred scope remains in the backlog. The board therefore shows a sprint committed to roughly 2.8 times the team's demonstrated velocity.

This is deliberate and it is visible on purpose. The board now displays the same shortfall the EVM metrics predict, rather than hiding it behind a backlog nobody reads. The required decision is which 46 points come out, and that decision belongs to the Product Owner and the team before Sprint 3 planning closes.

---

## 5. Recommendations

1. **Re-baseline the scope rather than the schedule.** The December 4 date is fixed and the team cannot add capacity, so scope is the only variable. Reduce committed Sprint 3 scope to approximately 25 points and move the remainder to a documented post-project backlog.
2. **Prioritize by what the final deliverable and presentation require.** Work that produces demonstrable outcomes should outrank work that does not.
3. **Report the variance rather than absorb it.** An SPI of 0.62 disclosed in week 9 with a recovery plan is a managed project. The same number discovered at the final presentation is a failed one.
4. **Plan Sprint 3 against 25 points, not 26.** Use the two-sprint average. Planning against the better sprint builds optimism bias into the last forecast the project will make.

---

## AI Use Note

Claude (Anthropic) was used to structure this report, perform the EVM calculations from the team's story point data, and draft the interpretation sections. The team supplied the velocity figures and scope totals from the project board, reviewed the calculations, and verified the velocity figures against the project board.

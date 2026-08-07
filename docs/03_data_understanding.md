# Phase 3: Data Understanding

**Status: Complete**

## Dataset Structure

The project combines two related synthetic tables with different grains.

| Table | Grain | Records | Business use |
|---|---|---:|---|
| Employee | One row per employee | 1,000 | Department, compensation, work, commute, and location context |
| Satisfaction | One row per survey response | 3,711 | Satisfaction, concern, bonus, and time analysis |

The satisfaction table contains responses from 984 employees between January 2021 and December 2023. Sixteen employee records have no satisfaction response.

## Keys and Relationships

- `Employee.EmployeeID` uniquely identifies an employee profile.
- `Satisfaction.Employee ID` links each response to an employee.
- `SurveyID` uniquely identifies a survey response.
- One employee can have multiple survey responses.

## Connection to Business Questions

| Business question | Required fields | Measure | Interpretation limit |
|---|---|---|---|
| Which departments differ? | Department, satisfaction score | Average response score and count | Repeated responses are possible |
| Which concerns are most common? | Department, least-satisfied category | Within-department response share | Categories do not explain root cause |
| How do bonuses relate to satisfaction? | Bonus percentage, bonus satisfaction | Pearson correlation and trend | Relationship is not causal |
| Where are low scores concentrated? | ZIP code, satisfaction score | Geographic average | Location overlaps with other workforce factors |
| How has satisfaction changed? | Survey date, satisfaction score | Monthly average | Workforce composition may change |

## Validated Baseline

- All 3,711 satisfaction responses match an employee profile.
- Employee IDs, survey IDs, dates, departments, and satisfaction fields used in the dashboard contain no missing values.
- Department response counts vary substantially.
- Research and Development has the highest average satisfaction at 74.99; Finance has the lowest at 35.80.
- Bonus percentage and satisfaction with bonus have a Pearson correlation of approximately 0.92.

## Data-Use Guardrails

- Use normalized concern percentages instead of raw counts for department comparisons.
- Show response counts when filters create small groups.
- Treat ZIP-code patterns as exploratory.
- Do not treat survey relationships as evidence that a policy caused an outcome.
- Keep the synthetic-data disclosure visible.

## Analytical Readiness

The data supports descriptive department, concern, compensation, location, work-arrangement, and time analysis. It is not sufficient for causal policy evaluation, individual employment decisions, or conclusions about a real employer.

## Related Documentation

- [Methodology](methodology.md)
- [Data dictionary](data-dictionary.md)
- [Phase 2 Business Understanding](02_business_understanding.md)


# Methodology

## Data Model

The analysis combines an employee-level table with a survey-response table.

- `Employee.EmployeeID` is the employee-table key.
- `Satisfaction.Employee ID` links each response to an employee profile.
- The employee table contains 1,000 records.
- The satisfaction table contains 3,711 responses from 984 unique employees.
- Survey dates range from January 1, 2021, through December 31, 2023.

Because employees can submit more than one survey, most satisfaction analyses use survey responses as the unit of analysis.

## Validation

The following checks were completed before interpreting the dashboard:

- Confirmed that employee IDs, survey IDs, dates, department values, and satisfaction fields contained no missing values.
- Confirmed that all satisfaction responses matched an employee profile.
- Reviewed department-level response counts to identify differences in group size.
- Compared dashboard findings with independently calculated summary statistics.

## Calculations

### Average Satisfaction by Department

Average satisfaction was calculated over all survey responses associated with each department.

| Department | Average satisfaction | Responses |
|---|---:|---:|
| Research and Development | 74.99 | 925 |
| Innovation | 73.84 | 478 |
| HR | 69.41 | 160 |
| Branding and marketing | 58.71 | 247 |
| Manufacturing | 45.51 | 1,550 |
| Finance | 35.80 | 351 |

### Department Concern Percentages

The original heatmap used raw response counts, which overstated concerns in larger departments. It was revised to show:

`Responses naming a concern within a department ÷ all responses from that department`

This makes each department column total 100% and supports comparisons across departments of different sizes.

### Bonus Relationship

The Pearson correlation between bonus percentage and satisfaction with bonus was approximately 0.92. A curved trend line was retained because average gains in bonus satisfaction became smaller at higher bonus percentages. This relationship is descriptive and should not be interpreted as causal.

### Time Trend

Survey responses were aggregated by month using average satisfaction score. The view contains a long-term trend line and monthly values from January 2021 through December 2023.

### Geographic View

Responses were associated with employee ZIP codes and displayed using average satisfaction score. ZIP-code patterns were treated as exploratory because location overlaps with department and work-arrangement differences.

## Dashboard Interactivity

The dashboard includes filters for:

- Department
- Satisfaction category
- Work arrangement
- Employment level
- Full-time/part-time status

Users should interpret filtered results cautiously when a selection creates a small subgroup.


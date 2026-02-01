---
name: nia-calendar-planning
description: Create annual work calendars for NIA's Administrative (256-day) and Office Professional (250-day) staff. Use when user asks to create calendars for a new fiscal year, plan AA/OP calendars, or work on annual calendar planning.
---

# NIA Annual Calendar Planning Skill

Create 256-day (Administrative) and 250-day (Office Professional) calendars for a fiscal year.

## Workflow

1. **Gather inputs** from user:
   - Fiscal year (e.g., FY27 = July 1, 2026 - June 30, 2027)
   - Election Day status: Is it a legal holiday this year? (determines 10 vs 11 legal holidays)
   - Spring Break week for OP calendar (5 NR days)

2. **Calculate**:
   - Available work days (weekdays in fiscal year)
   - Legal holiday dates with weekend observance adjustments
   - NR days for each calendar type

3. **Generate outputs**:
   - Calendar Planning Tool spreadsheet (calculations summary)
   - Visual calendar spreadsheet (AA and OP sheets with color-coded days)

4. **Review with user** before finalizing

## Core Calculation

```
Available Work Days (weekdays July 1 - June 30)
- Legal Holidays (10 or 11)
- Director's Holidays (4 or 5)
- NR Days (calculated to balance)
= Work Days
```

| Calendar | Contract Days | Work Days | NR Days |
|----------|---------------|-----------|---------|
| AA (256) | 256 | 241-242 | 4-5 |
| OP (250) | 250 | 235-236 | 10-11 |

## Legal Holidays (10 Standard)

| Holiday | Date Rule | Weekend Observance |
|---------|-----------|-------------------|
| Independence Day | July 4 | Nearest weekday |
| Labor Day | First Monday in September | N/A |
| Columbus Day | Second Monday in October | N/A |
| Thanksgiving | Fourth Thursday in November | N/A |
| Christmas | December 25 | Nearest weekday |
| New Year's Day | January 1 | Nearest weekday |
| MLK Day | Third Monday in January | N/A |
| Presidents' Day | Third Monday in February | N/A |
| Memorial Day | Last Monday in May | N/A |
| Juneteenth | June 19 | Nearest weekday |

**Election Day (11th, Variable):**
- Legal holiday when designated by Illinois law
- When NOT legal holiday: employees get 5th Director's Holiday (Wednesday before Thanksgiving)
- Date: First Tuesday after first Monday in November

## Director's Holidays (4 Standard)

1. Day after Thanksgiving (Friday)
2. Christmas Eve (December 24)
3. New Year's Eve (December 31)
4. Day before Thanksgiving (Wednesday, tradeable for religious/other holiday)
5. Wednesday before Thanksgiving (ONLY when Election Day is NOT a legal holiday)

## Weekend Observance Rules

- Saturday holiday → observe Friday
- Sunday holiday → observe Monday

## NR Day Assignment Rules

**256-Day (AA)**:
- All NR days clustered in Christmas week
- **Guiding principle**: Start break as early as possible, return on a Monday in January
- Typical pattern: Dec 22, 23, 28, 29, 30 (5 NR days)

**250-Day (OP)**:
- 5 days to Spring Break (user-selected week)
- 6 days to Winter Break (Dec 21, 22, 23, 28, 29, 30)

## Calendar Output Format

Each calendar sheet includes:
- Monthly calendar grids (2 columns x 6 rows)
- Color coding: Red (Legal Holiday), Teal (Director's Holiday), Yellow (NR Day), Gray (Weekend)
- Event listing beside each month with day number and holiday/NR name
- Work day count per month (e.g., "July - 22 Work Days")
- Summary table at bottom:

| Days | Category |
|------|----------|
| 241 | Work Days |
| 11 | Legal Holidays |
| 4 | Director's Holidays |
| 5 | NR Days |
| **261** | **Total Contract Days** |

## Historical Data

| FY | Available Days | Election Day Legal? | Legal Holidays | Director's Holidays |
|----|----------------|---------------------|----------------|---------------------|
| FY22 | 261 | No | 10 | 5 |
| FY23 | 261 | No | 10 | 5 |
| FY24 | 260 | Yes | 11 | 4 |
| FY25 | 261 | Yes | 11 | 4 |
| FY26 | 261 | No | 10 | 5 |
| FY27 | 261 | Yes | 11 | 4 |

## Usage Example

User: "Create the FY28 calendars"

1. Ask: Is Election Day 2027 a legal holiday?
2. Ask: Which week for Spring Break?
3. Calculate available work days (weekdays July 1, 2027 - June 30, 2028)
4. Determine holiday dates with weekend adjustments
5. Calculate NR days for each calendar
6. Generate spreadsheets with monthly event listings and summary
7. Review with user

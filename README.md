# NIA Calendar Planning Skill

A Claude skill for creating annual work calendars for NIA's Administrative (256-day) and Office Professional (250-day) staff.

## Overview

This skill automates the annual calendar planning process for NIA, calculating work days, holidays, and non-responsibility (NR) days for two employee calendar types.

| Calendar Type | Contract Days | Work Days | Description |
|---------------|---------------|-----------|-------------|
| Administrative (AA) | 256 | 241-242 | Central office and administrative staff |
| Office Professional (OP) | 250 | 235-236 | Building-based office professionals |

## Installation

### For Claude.ai Projects
Upload `SKILL-standalone.md` to your Claude Project's custom instructions or project knowledge.

### For Claude Code / Cowork
Place the `nia-calendar-planning` folder in your skills directory.

## Usage

Trigger the skill by asking Claude to create calendars for a fiscal year:

```
"Create the FY28 calendars"
"Help me plan the AA and OP calendars for next year"
"Build the 256 and 250 day calendars for FY27"
```

Claude will:
1. Ask if Election Day is a legal holiday that year
2. Ask which week to designate as Spring Break (for OP calendar)
3. Calculate available work days and holiday dates
4. Generate color-coded calendar spreadsheets
5. Review the output with you
6. Ask where you want to save the final calendar files

## Files

| File | Purpose |
|------|---------|
| `SKILL.md` | Main skill instructions (for environments with file access) |
| `SKILL-standalone.md` | Self-contained version with all reference data (for Claude.ai upload) |
| `references/holidays.md` | Holiday rules, dates, and historical data |
| `scripts/calculate_calendar.py` | Python calculation engine |
| `README.md` | This file |

## Core Calculation

```
Available Work Days (weekdays July 1 - June 30)
- Legal Holidays (10 or 11)
- Director's Holidays (4 or 5)
- NR Days (calculated to balance)
= Work Days
```

## Holiday Structure

### Legal Holidays (10 standard)
Independence Day, Labor Day, Columbus Day, Thanksgiving, Christmas, New Year's Day, MLK Day, Presidents' Day, Memorial Day, Juneteenth

### Election Day (11th, variable)
Legal holiday when designated by Illinois law. When not a legal holiday, employees receive a 5th Director's Holiday instead.

### Director's Holidays (4 standard)
Day after Thanksgiving, Christmas Eve, New Year's Eve, Day before Thanksgiving (tradeable)

## NR Day Assignment Rules

**256-Day (AA):**
- All NR days clustered in Christmas week
- Guiding principle: Start break early, return on a Monday in January
- Typical pattern: Dec 22, 23, 28, 29, 30

**250-Day (OP):**
- 5 days to Spring Break (user-selected week)
- 6 days to Winter Break (Dec 21, 22, 23, 28, 29, 30)

## Output Format

Generated calendars include:
- Monthly calendar grids with color-coded days
- Event listing beside each month
- Work day count per month
- Summary table:

| Days | Category |
|------|----------|
| 241 | Work Days |
| 11 | Legal Holidays |
| 4 | Director's Holidays |
| 5 | NR Days |
| **261** | **Total Contract Days** |

## Historical Data

| FY | Available Days | Election Day Legal? |
|----|----------------|---------------------|
| FY22 | 261 | No |
| FY23 | 261 | No |
| FY24 | 260 | Yes |
| FY25 | 261 | Yes |
| FY26 | 261 | No |
| FY27 | 261 | Yes |

## Related Process Documentation

This skill implements the Annual Calendar Planning Process documented in NIA's Baldrige Excellence framework (Category 5: Workforce, Item 5.1).

## License

Internal use only. Northwestern Illinois Association.

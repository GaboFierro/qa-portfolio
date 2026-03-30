# Sprint 1 — Functional Testing & Bug Reporting
**App:** Urban Routes (Google Maps-style web app)  
**Tools:** Jira · Spreadsheet  

---

## About this project

This was my first sprint at the TripleTen QA Bootcamp. The goal was to test the core functionality of **Urban Routes**, a web application for route planning and transportation booking — similar to Google Maps.

My job was to design test cases based on the app's requirements, execute them, and document any defects found using structured bug reports.

---

## What I tested

I focused on the map interaction layer of the application:

- **Map scrolling** — verifying the map moves correctly and all objects render as expected
- **Map zoom** — confirming the zoom buttons work and the view updates properly
- **City area headers** — validating that clicking on area labels (like "Hollywood") does not trigger any unintended interaction

---

## ( some Test Cases )

| ID | Title | Result |
|---|---|---|
| CASO-1 | Map scrolling behavior | ✅ Passed |
| CASO-2 | Map zoom functionality | ✅ Passed |
| CASO-3 | City headers should not be clickable | ❌ Failed → ERR-001 |

---

## ( some Bugs Found )

**ERR-001 — City area headers are interactive** `Severity: Minor`
- **Expected:** Clicking a city header on the map does nothing
- **Actual:** Clicking it opens location information — an unintended interaction not defined in requirements

**ERR-002 — "To" field does not show subway station list** `Severity: Critical`
- **Expected:** Typing "Subway" in the destination field displays a list of metro stations
- **Actual:** No list appears — the field returns no results, breaking a core search feature

---

## What I learned

This sprint helped me understand how to translate requirements into structured test cases, think critically about expected vs actual behavior, and write bug reports that are clear enough for a developer to reproduce and fix the issue without needing additional context.

---

## Files
- `sprint1_test_cases.xlsx` — Full test cases and bug reports

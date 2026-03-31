# Sprint 2 — Test Design & Documentation
**App:** Urban Routes — Driver's license form & trip time/cost calculator  
**Tools:** Spreadsheet · Flow Diagram · Mind Map  

---

## About this project

In this sprint the focus shifted from executing tests to **designing them**. I worked on two areas of Urban Routes: the driver's license registration form and the trip calculator, which determines travel time and cost based on departure time.

I applied equivalence class partitioning and boundary value analysis to build efficient, risk-focused test cases without needing to test every possible input.

---

## Artifacts created

**Mind Map — Driver's License Form**
Mapped out all fields, validations, UI behavior, button logic, and edge cases of the "Add Driver's License" modal. This helped visualize the full scope of what needed to be tested before writing a single test case.

**Equivalence Classes & Boundary Values**
Identified valid and invalid input classes for the license form fields (name, last name, date of birth, license number) and for the trip calculator's time-based speed logic.

**Flow Diagram — Speed Logic**
Created a decision flow diagram showing how the app selects travel speed based on the user's departure time across 5 time windows.

**Test Cases — Trip Calculator**
Designed test cases validating that the app correctly calculates trip duration and price for each speed scenario.

---

## Equivalence Classes — Speed by Time of Day

| Time Range | Speed | Boundary Values Tested |
|---|---|---|
| 00:01 – 08:00 | 45 km/h | 00:00, 00:01, 08:00, 08:01 |
| 08:01 – 12:00 | 30 km/h | 08:00, 08:01, 12:00, 12:01 |
| 12:01 – 18:00 | 40 km/h | 12:00, 12:01, 18:00, 18:01 |
| 18:01 – 22:00 | 25 km/h | 18:00, 18:01, 22:00, 22:01 |
| 22:01 – 00:00 | 45 km/h | 22:00, 22:01, 23:59, 00:00 |

---

## Test Cases — Trip Calculator

| ID | Departure Time | Speed | Distance | Expected Duration | Expected Price |
|---|---|---|---|---|---|
| p-1 | 19:00 | 25 km/h | 1.4 km | 3.36 min | $0.34 |
| p-2 | 10:00 | 30 km/h | 1.4 km | 2.80 min | $0.28 |

---

## What I learned

This sprint taught me that good testing is not about testing everything — it is about testing the right things. Equivalence class partitioning and boundary value analysis help maximize defect detection while keeping test suites manageable. I also learned how to translate business logic into visual artifacts like mind maps and flow diagrams that make testing more structured and easier to communicate to a team.

---

## Files
- `sprint2_equivalence_classes.xlsx` — Equivalence classes and boundary values
- `sprint2_test_cases.xlsx` — Test cases for the trip calculator
- `flow_diagram_speed.pdf` — Decision flow diagram for speed logic
- `mind_map_license.pdf` — Mind map of driver's license form validations

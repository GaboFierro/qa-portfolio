# Sprint 2 — Test Design & Documentation
**App:** Urban Routes — Driver's license form & trip time/cost calculator  
**Tools:** Spreadsheet · Flow Diagrams · Mind Maps  

---

## About this project

In this sprint the focus shifted from executing tests to **designing them**. I worked on two areas of Urban Routes: the driver's license registration form and the trip calculator engine, which determines travel time and cost based on distance and departure time.

The goal was to apply formal test design techniques — equivalence class partitioning and boundary value analysis — to build efficient, risk-focused test cases without testing every possible input.

---

## What I tested

**Driver's License Form**
Analyzed the validation rules for each required field: first name, last name, date of birth, and license number. I identified valid and invalid equivalence classes and their boundary values to ensure the form correctly accepts and rejects input.

**Trip Time & Cost Calculator**
The calculator changes travel speed depending on the time of day, which directly affects the trip duration and price. I mapped out all 5 time windows and designed test cases covering both the typical values and the exact boundary points where speed changes occur.

---

## Test Design: Equivalence Classes

### Driver's License — Name Field
| Class | Range | Valid? |
|---|---|---|
| Valid length | 2–14 characters | ✅ |
| Too short | Less than 2 characters | ❌ |
| Too long | More than 14 characters | ❌ |

### Trip Calculator — Speed by Time of Day
| Time Range | Speed | Boundary Values Tested |
|---|---|---|
| 00:01 – 08:00 | 45 km/h | 00:00, 00:01, 08:00, 08:01 |
| 08:01 – 12:00 | 30 km/h | 08:00, 08:01, 12:00, 12:01 |
| 12:01 – 18:00 | 40 km/h | 12:00, 12:01, 18:00, 18:01 |
| 18:01 – 22:00 | 25 km/h | 18:00, 18:01, 22:00, 22:01 |
| 22:01 – 00:00 | 45 km/h | 22:00, 22:01, 23:59, 00:00 |

---

## Test Cases

| ID | Scenario | Expected Result |
|---|---|---|
| p-1 | Trip at 19:00 (25 km/h), 1.4 km | Duration: 3.36 min · Price: $0.34 |
| p-2 | Trip at 10:00 (30 km/h), 1.4 km | Duration: 2.8 min · Price: $0.28 |

---

## What I learned

This sprint taught me that good testing is not about testing everything — it is about testing the right things. Equivalence class partitioning and boundary value analysis are powerful tools that help you maximize defect detection while keeping the test suite manageable. I also learned how to read business requirements and translate them into structured, traceable test scenarios.

---

## Files
- `sprint2_equivalence_classes.xlsx` — Equivalence classes and boundary values
- `sprint2_test_cases.xlsx` — Test cases for the trip calculator
- `flow_diagram_speed.pdf` — Decision flow diagram for speed logic
- `mind_map_license.pdf` — Mind map of driver's license form validations

# Sprint 3 — UI Testing, Bug Hunting & Jira
**App:** Urban Routes — Car booking flow  
**Tools:** Jira · Spreadsheet · Firefox · Chrome  

---

## About this project

This sprint focused on **UI testing and bug hunting** for the car booking flow in Urban Routes. I tested the reservation form design, the payment method window, the "Add Card" feature, and the logic of the "Reserve" button.

All defects found were logged and tracked in **Jira** with full reproduction steps, severity, and priority.

🔗 [View bug reports in Jira](https://gabofierro.atlassian.net/jira/software/c/projects/PPETSPGF/list)

---

## What I tested

- **Reservation form design** — verified layout, rates display, and visual state across Firefox and Chrome
- **Payment method window** — validated that clicking the payment field opens the correct modal
- **Add Card form** — tested that the card form opens and accepts valid input
- **Reserve button logic** — verified button behavior with and without a driver's license added

---

## Results Summary

### Design Checklist
| # | Check | Firefox | Chrome |
|---|---|---|---|
| 1 | Initial form state is correct | ✅ | ✅ |
| 2 | Three rates are available (Casual, Camping, Luxury) | ❌ | ✅ |
| 3 | Each rate shows icon, name and price | ❌ | ❌ |
| 4 | A rate is always selected | ✅ | ✅ |
| 5 | Selected rate is visually highlighted | ✅ | ✅ |

### Payment Window Checklist
| # | Check | Result |
|---|---|---|
| 1 | Clicking payment field opens Payment window | ✅ |
| 2 | Clicking "Add Card" opens the Add Card form | ❌ Bug found |
| 3 | Bank card payment option is displayed | ✅ |

---

## Bugs Found

**PPETSPGF-1 — Rates do not display icon, name and price correctly** `Severity: High`
- **Expected:** Each rate shows its icon, name and price
- **Actual:** The information is missing or incorrectly displayed

**PPETSPGF-9 — Reserve button does not update when license is missing** `Severity: High`
- **Expected:** Button shows "Add driver's license and reserve" when no license is added
- **Actual:** Button text does not change — the missing license state is not communicated to the user

---

## What I learned

This sprint reinforced how important attention to detail is in UI testing. Small visual inconsistencies can affect user trust and experience just as much as functional bugs. I also got comfortable with the full Jira defect lifecycle — from creating a ticket with all required fields to tracking it through resolution.

---

## Files
- `sprint3_test_cases.xlsx` — Checklists and test cases for the booking flow

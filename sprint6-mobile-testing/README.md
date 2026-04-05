# Sprint 6 — Mobile App Testing (Urban.Lunch)

## Description
Manual testing of the **Urban.Lunch** mobile application, an app designed 
to customize business lunches by combining dishes from different restaurants 
into a single order.

Tests were executed on an Android emulator (Android Studio) covering 
100% of the documented requirements.

## Test Environment
- **Device:** Honor-tripleten1 (Virtual Emulator – Android Studio)
- **Operating System:** Android 9.0 "Pie" – API Level 28
- **Resolution:** 1080 × 1920 px | 360 × 640 dp | 480 dpi
- **Architecture:** arm64-v8a
- **App Version:** Test version (15 s timer)

## Test Scope
- Pickup point selection
- Dish selection (list and details)
- Order confirmation
- Order tracking
- Order dispatched screen
- Time and cost calculation
- Error notifications

## Results
| Total Cases | Passed | Failed |
|---|---|---|
| 50 | 39 (78%) | 11 (22%) |

## Bugs Found
**11 formal bugs** were reported in Jira plus **1 additional exploratory bug**.

| Ticket | Bug | Priority |
|---|---|---|
| PPES6E-1 | Map does not show the user's current location | Medium |
| PPES6E-2 | Next button not shown as inactive when no pickup point selected | Low |
| PPES6E-3 | Next button not shown as inactive when no dishes in order | Low |
| PPES6E-4 | Next button active in dish details screen + validation message in English | Medium |
| PPES6E-5 | Restaurant marker and route remain on map after delivery completes | Medium |
| PPES6E-6 | Green checkmark does not appear next to delivered dishes | Medium |
| PPES6E-7 | Delivery time does not show real preparation + delivery time | High |
| PPES6E-8 | Delivery time does not take the maximum when two dishes from same restaurant | High |
| PPES6E-9 | Total order time incorrect with a single restaurant | High |
| PPES6E-10 | Total order time with multiple restaurants does not show the maximum | High |
| PPES6E-11 | App shows no error when geolocation permission is denied | Medium |
| Exploratory | Dish counter resets to 0 after scrolling the list | High |

## Files
- `checklist.xlsx` — Test checklist with 50 test cases and results
- `informe-de-pruebas.docx` — Full test report with findings and recommendations

## Tools Used
- Android Studio (emulator)
- Jira (bug reporting)
- TripleTen QA Bootcamp — Group 69

# Sprint 4 — API Testing with Postman
**App:** Urban Grocers REST API  
**Tools:** Postman · Jira · Spreadsheet  

---

## About this project

This sprint focused on **REST API testing** for Urban Grocers, a grocery delivery backend. I tested two core endpoints: one for managing product kits and one for validating delivery availability based on time windows.

All requests were built and executed in **Postman**, validating status codes, response bodies, and business logic. Defects were reported in **Jira**.

---

## Endpoints Tested

**POST** `/api/v1/kits/:id/products`
Validates that products can be added to a kit using a valid kit ID and product ID.

**POST** `/order-and-go/v1/delivery`
Validates delivery availability based on a time window of 08:00–22:00.

---

## Results — Kits Endpoint

| # | Test Case | Expected | Result |
|---|---|---|---|
| 1 | Add existing product to valid kit | 200 OK | ✅ Passed |
| 2 | Add product to valid kit id=7 | 200 OK | ✅ Passed |
| 3 | Kit ID does not exist (id=999999) | 404 Not Found | ✅ Passed |
| 4 | Kit ID = 0 | 404 Not Found | ✅ Passed |
| 5 | Kit ID negative (id=-1) | 404 Not Found | ✅ Passed |
| 6 | Add existing product (id=7) | 200 OK | ✅ Passed |
| 7 | Product ID does not exist (id=999999) | 400 Bad Request | ❌ Failed → [UG-1](https://gabofierro.atlassian.net/browse/UG-1) |

---

## Results — Delivery Endpoint

| # | deliveryTime | Expected | Result |
|---|---|---|---|
| 1 | 8 (valid) | 200 + true | ✅ Passed |
| 2 | 22 (valid boundary) | 200 + true | ✅ Passed |
| 3 | 15 (mid-range) | 200 + true | ✅ Passed |
| 4 | 7 (below range) | 200 + false | ❌ Failed → [UG-8](https://gabofierro.atlassian.net/browse/UG-8) |
| 5 | 23 (above range) | 200 + false | ❌ Failed → [UG-9](https://gabofierro.atlassian.net/browse/UG-9) |
| 6 | -1 (negative value) | 400 Bad Request | ❌ Failed → [UG-10](https://gabofierro.atlassian.net/browse/UG-10) |

---

## Bugs Found

**UG-1 — API accepts non-existent product ID** `Severity: High`
- **Expected:** 400 Bad Request
- **Actual:** 200 OK — system adds the product without data

**UG-8 — deliveryTime=7 returns true instead of false** `Severity: High`
- **Expected:** isItPossibleToDeliver: false (outside 08–22 window)
- **Actual:** isItPossibleToDeliver: true

**UG-9 — deliveryTime=23 returns true instead of false** `Severity: High`
- **Expected:** isItPossibleToDeliver: false
- **Actual:** isItPossibleToDeliver: true

**UG-10 — Negative deliveryTime returns 200 OK** `Severity: Critical`
- **Expected:** 400 Bad Request
- **Actual:** 200 OK — system accepts an invalid value

---

## What I learned

This sprint showed me how much logic lives behind the UI that users never see. API testing revealed defects that would be impossible to catch through the interface alone. I learned how to structure requests in Postman, interpret response bodies and status codes, and think critically about edge cases like negative values and out-of-range inputs.

---

## Files
- `sprint4_test_cases.xlsx` — Full test cases with results and bug links
- `Urban Grocers.postman_collection.json` — Postman collection export (Req1 Kits + Req2 Servicio de entrega)

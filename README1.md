# Lab: Test Planning and Defect Management

## Step 1: Test Plan

### Test Objectives
Verify that the Counter application correctly increments, decrements, and resets the counter.

### Scope

**In Scope**
- Initial counter value
- Increment functionality
- Decrement functionality
- Reset functionality
- Multiple button interactions

**Out of Scope**
- User authentication
- Database functionality
- Security and performance testing

### Testing Approach
Manual functional testing will be performed by clicking each button and comparing actual results with expected results.

### Test Environment
- **Operating System:** macOS
- **Code Editor:** Visual Studio Code
- **Browser:** Chrome
- **Runtime:** Node.js
- **Application:** React and Vite

### Product Risks
The Decrement button may perform the wrong operation, resulting in inaccurate counter values.

### Entry Criteria
- Application is running.
- All buttons are visible.
- Testing environment is ready.

### Exit Criteria
- At least four test cases are executed.
- Failed tests are repeated.
- Defects are documented.

---

## Step 2: Test Case Design

### TC-001: Verify Initial Counter Value
- **Starting State:** Application just opened.
- **Actions:** Open the application.
- **Expected Result:** Counter displays 0.

### TC-002: Verify Increment Function
- **Starting State:** Counter displays 0.
- **Actions:** Click Increment once.
- **Expected Result:** Counter increases to 1.

### TC-003: Verify Decrement Function
- **Starting State:** Counter displays 1.
- **Actions:** Click Decrement once.
- **Expected Result:** Counter decreases to 0.

### TC-004: Verify Multiple Actions and Reset
- **Starting State:** Counter displays 0.
- **Actions:**
  1. Click Increment twice.
  2. Click Reset once.
- **Expected Result:** Counter reaches 2 and then returns to 0.

---

## Step 3: Test Execution

| Test ID | Actual Result | Status |
|---|---|---|
| TC-001 | Counter displays 0. | PASS |
| TC-002 | Counter increases to 1. | PASS |
| TC-003 | Counter increases instead of decreasing. | FAIL |
| TC-004 | Counter reaches 2 and resets to 0. | PASS |

### Failed Test Repetition
TC-003 was repeated using the same starting value of 1. The Decrement button continued increasing the counter instead of decreasing it.

**Result:** Defect successfully reproduced.

---

## Step 4: Defect Report

### DEF-001: Decrement Button Increases Counter Instead of Decreasing

- **Related Test Case:** TC-003
- **Environment:** macOS, Chrome, React, Vite
- **Severity:** Medium
- **Priority:** High
- **Status:** Open

**Steps to Reproduce**
1. Open the Counter application.
2. Click Increment once.
3. Click Decrement once.

**Expected Result:** Counter decreases from 1 to 0.

**Actual Result:** Counter increases instead of decreasing.

**Impact:** Users cannot correctly decrease the counter value, affecting the application's functionality.

**Reproducibility:** The issue occurred again when TC-003 was repeated.
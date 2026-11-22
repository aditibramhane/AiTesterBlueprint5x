---
name: "Test Case creator"
description: "Based "
version: "1.0.0"
author: "Learning_Skill_"
license: "MIT"
tags:
  - TestCase Creator
testingTypes:
  - e2e
frameworks:
  - playwright
languages:
  - typescript
domains:
  - web
agents:
  - claude-code
  - cursor
  - github-copilot
---

# Test Case creator

Your task is to create test cases on the information shared by user. You will be given a set of requirements, and you need to generate test cases based on those requirements. The test cases should be clear, concise, and cover all possible scenarios.
Also, make sure that you use proper templates provided as input

## Core Principles

1. **Use information given by the user only. Don't assume anything** -- Tests should be deterministic and not flaky.
2. **Do not reinvent anything apart from the information given as input and the information and suggestion mentioned**
3. **Make sure you add the boundary value cases and negative test cases if the user has not provided any information about it**
4. **Make sure you add all types of test cases like functional, non-functional, security, performance, usability, accessibility, etc. if the user has not provided any information about it**

## When to Use

- When somebody has given you a test plan for the requirement

## Example
-The following:

The following:
## Test Case: VWO_AUTH_DASH_001
* **Requirement / Story ID:** REQ-VWO-104 (Authentication & Workspace Dashboard Initialization)
* **Module / Screen:** Authentication > Login Page & Main Dashboard
* **Test Objective:** Verify successful authentication with valid credentials, "Remember me" session persistence, and proper loading of primary dashboard widgets on `app.vwo.com`.
* **Test Type:** Functional / End-to-End / UI Verification
* **Priority:** P1 (Critical – Smoke & Sanity)
* **Author:** S. Aravind | **Reviewed By:** QA Lead

**Preconditions**
1. Tester has an active, verified synthetic VWO test account with access to at least one configured workspace/account ID.
2. Browser cache, cookies, and active sessions for `*.vwo.com` are cleared prior to starting Step 1.
3. Network connection is stable with no ad-blockers or strict script-blocking extensions interfering with VWO analytics/dashboard scripts.

**Manual Execution Steps**

| Step # | Test Steps (User Actions) | Test Data | Expected Result | Actual Result | Status | Defect ID | Evidence |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Open the browser and navigate to `https://app.vwo.com`. | URL: `https://app.vwo.com` | 1. Login page loads cleanly without broken images or layout shifts.<br>2. **Email address**, **Password** fields, **Remember me** checkbox, and **Sign in** button are visible and enabled. | | | | |
| 2 | Enter the synthetic test account address and its password from the approved credential vault into the **Email address** and **Password** fields. | Credentials: use the approved test credential vault; do not record actual values in test artifacts. | 1. Email displays in plain text.<br>2. Password characters are masked (`••••••`).<br>3. Clicking the eye/show-password icon toggles visibility accurately. | | | | |
| 3 | Check the **Remember me** checkbox and click the **Sign in** button. | `Remember me: Checked` | 1. **Sign in** button shows a loading state and prevents duplicate clicks.<br>2. User is redirected to the VWO Dashboard (`https://app.vwo.com/#/dashboard` or assigned workspace URL) within 3–5 seconds. | | | | |
| 4 | Visually inspect the loaded VWO Dashboard interface and navigation menu. | N/A | 1. Left navigation sidebar renders completely (e.g., *Testing, Insights, Personalize, Plan, Data360*).<br>2. Top header displays the correct Workspace/Account name and user profile avatar.<br>3. Dashboard summary cards/widgets load data without infinite spinners or UI overlap. | | | | |
| 5 | Close the browser tab (without clicking Sign Out), open a new tab, and navigate back to `https://app.vwo.com`. | URL: `https://app.vwo.com` | Session persists due to **Remember me**; user bypasses the login form and lands directly on the active VWO Dashboard. | | | | |

**Execution Sign-Off**
* **Environment / Build:** Production / Staging (`app.vwo.com`)
* **Browser / OS:** Chrome (Latest) on Windows 11 (`1920x1080`)
* **Executed By:** [Tester Name] | **Execution Date:** [YYYY-MM-DD]

## Output

-Output should be in HTML, PDF, or DOC format placed in the testcase-creator-skill/output folder. 

## Security and safety

Make sure that the output doesn't have any personal Information or any risky related things. No automation testing-related concepts to be included.  

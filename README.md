# 🛒 Project: "Paychi" - Shopping & Expenses App – manual tests

This repository contains the manual test documentation for the “Paychi” web application, which helps users to plan shopping lists and to calculate expenses within groups of friends.

Link to the application: https://www.paychi.ovh

---

## 🎯 1. Project goal:

The main objective of the tests was to verify key functionalities accessible in the frontend layers of the application.

---

## 📏 2. Testing scope:

The following types of tests were carried out as part of the testing process:

1. Functional
2. Regression
3. Visual testing (responsiveness and UI consistency)

The application was tested manually across the following areas:

- Registration and log in,
- Friends – inviting and declining,
- Group management — creating groups, adding and removing members, changing roles of members, permissions of group members,
- Shopping lists — creating and deleting, adding items, removing items,
- Expenses - creating and deleting, cost sharing calculating,
- Responsiveness on resolutions: 360 x 640 px, 768×1024px, 1920×1080px.

The full testing approach is described in the Test Plan:

📝 **Link to full Test Plan:** [Test-Plan](https://github.com/joannabrodowicz/Paychi-manual-testing/blob/main/docs/Test_Plan.pdf)

---

## 🛠️ 3. Tools used

- **Jira** – bug reporting and management,

- **Google Sheets** – test cases design,

- **DevTools** – bug analysis, responsiveness testing,

- **ShareX** – screenshots for bug reports.

---

## ⚙️ 4. Executed Test Cases

All functional test cases were maintained and tracked in the Google Sheets:
🔗 **Link to Test Cases:** [Test-Cases](https://docs.google.com/spreadsheets/d/1gIiOzly2Rahn41_cDV1mjvlk-lbAHTWLOZv8Ez4J1sw/edit?usp=sharing)

I created 32 test cases - 26 of them passed and 6 failed.

Bugs most often involved missing or technical error messages.

Some test cases have been updated because the registration form has changed.

To test permissions of group member's roles, I created roles and permissions matrix:

📝 **Link to the matrix with test results**: [Permissions-Tests](https://github.com/joannabrodowicz/Paychi-manual-testing/blob/main/docs/Permissions_Tests.md)

Visual tests (UI consistency and responsiveness) I conducted using an exploratory method and documented with bug reports.

---

## 🐞 5. Most interesting bugs

Below is a table with examples of bugs I found during the testing process - more bugs are available at repository:

| #   | Name                                                                    | Priority   | Impact                                                                                                                                           | Bug report                                                                                                                                              | Evidences                                                                                                                             |
| --- | ----------------------------------------------------------------------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Registration is blocked when the Name already exist in DB               | **High**   | Block new users with the same name from creating an account (already fixed)                                                                      | [Jira-PAYC-03](https://raw.githubusercontent.com/joannabrodowicz/Paychi-manual-testing/main/Bug-Reports/Functional/PAYC-3/Bug-report-Jira-PAYC-03.png)  | [Evidence](https://raw.githubusercontent.com/joannabrodowicz/Paychi-manual-testing/main/Bug-Reports/Functional/PAYC-3/evidence.png)   |
| 2   | Items are overwritten when two users edit the same shopping list        | **High**   | This bug negatively impacts the usability of the group shopping list feature.                                                                    | [Jira-PAYC-33](https://raw.githubusercontent.com/joannabrodowicz/Paychi-manual-testing/main/Bug-Reports/Functional/PAYC-33/Bug-report-Jira-PAYC-33.png) | [Evidence](https://www.loom.com/share/494e7aa5a2f84fd288dac4521c55ca02)                                                               |
| 3   | SQL exception error when amount field exceeds max value                 | **High**   | Exposes internal database error details to the user\*. It happens only with very large numbers exceeding 9 999 999 999,99                        | [Jira-PAYC-15](https://raw.githubusercontent.com/joannabrodowicz/Paychi-manual-testing/main/Bug-Reports/Functional/PAYC-15/Bug-report-Jira-PAYC-15.png) | [Evidence](https://raw.githubusercontent.com/joannabrodowicz/Paychi-manual-testing/main/Bug-Reports/Functional/PAYC-15/evidence1.png) |
| 4   | Sidebar is not scrollable when shopping lists and expenses are expanded | **Medium** | Users on small screens can't access all navigation elements                                                                                      | [Jira-PAYC-26](https://raw.githubusercontent.com/joannabrodowicz/Paychi-manual-testing/main/Bug-Reports/Visual/PAYC-26/Bug-report-Jira-PAYC-26.png)     | [Evidence](https://raw.githubusercontent.com/joannabrodowicz/Paychi-manual-testing/main/Bug-Reports/Visual/PAYC-26/evidence1.png)     |
| 5   | The date of the shopping list is changing after adding an item          | **Medium** | The bug negatively impacts the usability of the date setting feature and affects the display of the list in appropriate calendar day and filter. | [Jira-PAYC-30](https://raw.githubusercontent.com/joannabrodowicz/Paychi-manual-testing/main/Bug-Reports/Functional/PAYC-30/Bug-report-Jira-PAYC-30.png) | [Evidence](https://www.loom.com/share/be98ecb7aaea4289ad8cb32c1950b1ad)                                                               |

### Notes

Some evidence (such as payloads or full API responses) has been intentionally omitted because it contained sensitive or restricted technical data.

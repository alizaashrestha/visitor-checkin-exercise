# Defect Report – Visitor Check-in Application

## Confirmed Defects

### Defect 1: Visitors are registered with an incomplete name
- **Summary:** Visitors are registered with an incomplete name.
- **Type:** Functional
- **Description:** The feature states that the visitors are registered with their full name. However, there is no validation to ensure that. The visitors get registered even when only their first name, or just their last name, or just a word is entered instead of their full name.
- **Steps to Reproduce:**
  1. Launch the app on the browser.
  2. Navigate to the Visitor Registration form.
  3. Click on the "Full Name" field.
  4. Enter only a first name or last name.
  5. Enter the company name.
  6. Choose the host.
  7. Enter the purpose for the visit.
  8. Click Submit.
- **Expected Result:** The form should require a full name through validation blocking the submission or a clear error prompt.
- **Actual Result:** The visitor gets registered successfully and can be viewed on the "Active Visitors" list.

### Defect 2: Visitors are successfully registered even without their "purpose"
- **Summary:** Visitors are successfully registered even without their "purpose."
- **Type:** Functional
- **Description:** The feature states that the visitors are registered with their visit purpose. But the visitors are getting registered and shown in the active list even when their purpose is not specified.
- **Steps to Reproduce:**
  1. Launch the app on the browser.
  2. Navigate to the Visitor Registration form.
  3. Enter the full name.
  4. Enter the company name.
  5. Choose the host.
  6. Leave the "Purpose" field empty.
  7. Click on the "Submit" button.
- **Expected Result:** The form should be stopped from getting submitted and an error prompt should be shown.
- **Actual Result:** The visitor gets registered successfully and can be viewed on the "Active Visitors" list.

### Defect 3: Visitors are successfully registered when they enter random numbers in the "Full Name" field
- **Summary:** Visitors are successfully registered when they enter random numbers in the "Full Name" field.
- **Type:** Functional
- **Description:** In the "Full Name" field, when random numbers are entered instead of words, the visitors get successfully registered when the "Submit" button is clicked.
- **Steps to Reproduce:**
  1. Launch the app on the browser.
  2. Navigate to the Visitor Registration form.
  3. Enter random numbers in the "Full Name" field. For eg: "1234".
  4. Enter the company name.
  5. Choose the host.
  6. Enter the purpose.
  7. Click on the "Submit" button.
- **Expected Result:** The form should be stopped from getting submitted and an error prompt should be shown when numbers are entered in a text field.
- **Actual Result:** The visitor gets registered successfully and can be viewed on the "Active Visitors" list.

### Defect 4: Visitors are successfully registered when they enter special characters in the "Full Name" field
- **Summary:** Visitors are successfully registered when they enter special characters in the "Full Name" field.
- **Type:** Functional
- **Description:** When special characters like "@#$%^&" are entered in the "Full Name" field instead of an actual name, the visitor gets successfully registered when the "Submit" button is clicked.
- **Steps to Reproduce:**
  1. Launch the app on the browser.
  2. Navigate to the Visitor Registration form.
  3. Enter special characters in the "Full Name" field. For eg: "&*()#$".
  4. Enter the company name.
  5. Choose the host.
  6. Enter the purpose.
  7. Click on the "Submit" button.
- **Expected Result:** The form should be stopped from getting submitted and an error prompt should be shown when special characters are entered in a text field.
- **Actual Result:** The visitor gets registered successfully and can be viewed on the "Active Visitors" list.

### Defect 5: Visitors are successfully registered when they leave the "Company Name" field empty
- **Summary:** Visitors are successfully registered when they leave the "Company Name" field empty.
- **Type:** Functional
- **Description:** The feature states that the visitors are registered with their company name. But the visitor gets successfully registered and shown in the active list even when their company name is not entered.
- **Steps to Reproduce:**
  1. Launch the app on the browser.
  2. Navigate to the Visitor Registration form.
  3. Enter Full Name.
  4. Leave the "Company Name" field empty.
  5. Choose the host.
  6. Enter the purpose.
  7. Click on the "Submit" button.
- **Expected Result:** The form should be stopped from getting submitted and an error prompt should be shown when the "Company Name" field is left empty.
- **Actual Result:** The visitor gets registered successfully and can be viewed on the "Active Visitors" list.

### Defect 6: "Next" page appears whenever the current page is full (20 records), even when no further records actually exist
- **Summary:** "Next" page appears whenever the current page is full (20 records), even when no further records actually exist.
- **Type:** Functional
- **Description:** The active visitor list is paginated at 20 records per page. The app determines whether a "Next" page should be shown based solely on whether the current page contains exactly 20 records, rather than checking whether any visitor records actually exist beyond the current page. As a result, whenever a page has exactly 20 records, a "Next" page becomes accessible and displays as empty, even if no additional visitors exist beyond it. Conversely, whenever a page has fewer than 20 records, "Next" correctly disappears — and reappears again if the page count returns to exactly 20.
- **Steps to Reproduce:**
  1. Register visitors until a page (e.g., page 1) contains exactly 20 records.
  2. Observe that a "Next" page becomes accessible.
  3. Navigate to the "Next" page and confirm it displays an empty table with no visitor records.
  4. Reduce the count on the original page below 20 (e.g., check out one visitor), and confirm "Next" disappears.
  5. Register a new visitor to bring the page count back to exactly 20, and confirm "Next" reappears.
- **Expected Result:** A "Next" page should only be accessible when visitor records actually exist beyond the current page — not simply because the current page happens to contain exactly 20 records.
- **Actual Result:** The "Next" page is shown or hidden based solely on whether the current page has exactly 20 records, regardless of whether any records actually exist beyond it.

### Defect 7: No button for deactivation of the visitors
- **Summary:** No button for deactivation of the visitors.
- **Type:** Functional
- **Description:** The feature states that administrators can deactivate visitor records. However, no button, admin panel, or any UI element was found in the application that allows an administrator to perform this action.
- **Steps to Reproduce:**
  1. Launch the app on the browser.
  2. Look through the Active Visitors list, navigation menu, and any available pages for a way to deactivate a visitor.
  3. Confirm that no such button or option exists anywhere in the UI.
- **Expected Result:** Administrators should have a way, within the application UI, to deactivate a visitor record.
- **Actual Result:** No UI element exists anywhere in the application for deactivating a visitor.

### Defect 8: Check-in time displayed in UTC instead of local (Asia/Kathmandu) timezone
- **Summary:** Check-in time displayed in UTC instead of local (Asia/Kathmandu) timezone.
- **Type:** Functional
- **Description:** The spec states all times should be displayed in the receptionist's local timezone (Asia/Kathmandu). However, the "Checked In" time shown in the Active Visitors list reflects UTC time rather than local time, consistently off by approximately 5 hours 45 minutes — the UTC offset for Asia/Kathmandu. This is especially misleading near local midnight: a visitor checked in just after midnight local time can display a "Checked In" time from the previous evening, making it appear as though they





Assumptions/Open Questions?

Concern A: Can the same visitor register multiple times? (duplicate detection)

This is about one real person registering twice.

1. The feature does not specify how the application should distinguish between two different individuals who share the same full name, company, and visit purpose (e.g., two employees from the same company named "Aliza Shrestha," both visiting for a "meeting" on the same day). A visitor with identical details can be registered multiple times, with no way to confirm whether this represents the same person or two different people visiting at the same time. Since no unique identifier (such as an ID number or email) is captured during registration, there is no way to reliably tell these visitors apart in the system. Should the application capture an additional identifying field, or is name-based identification considered sufficient for this use case?

2. The spec does not specify whether pagination state should be preserved across a page refresh. Currently, refreshing the application while viewing a later page (e.g., page 4) resets the view back to page 1, regardless of which page was previously being viewed. Is this the intended behavior, or should the application preserve the current page across a refresh for a better user experience?







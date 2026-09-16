# QA Test Suite — Visitor Check-in Application

## Happy Path

### TC-001: Verify a visitor can be registered with all valid fields
**Preconditions:** Application is running on the browser and registration form is accessible to the user.
**Steps:**
1. Confirm the registration form is open.
2. Confirm full name, company name, host, and purpose are filled with valid input data.
3. Confirm the "Submit" button is clicked.
Expected Result:The visitor is registered successfully and appears in the Active Visitors list with all the details that were entered.
Status: [pass]


### TC-002: Verify a registered visitor appears on the "Active Visitor" list.
**Preconditions:** Application is running on the browser and registration form is accessible to the user.
**Steps:**
1. Confirm full name, company name, host, and purpose are filled with valid input data.
2. Confirm the visitor is registered.
3. Check the "Active Visitor"list.
4. Confirm that the registered visitors are shown on the list.
Expected Result: The registered visitors should be shown on the "Active Visitors" list after they have been successfully registered with all the input data if they are not checkout.
Status: [pass]

### TC-003: Verify a registered visitor's check-in time reflects local time
**Preconditions:** Application is running on the browser and registration form is accessible to the user.
**Steps:**
1. Check the current local time before registering.
2. Confirm full name, company name, host, and purpose are filled with valid input data.
3. Confirm the visitor is registered.
4. Check the "Checked In" time shown for that visitor.
Expected Result: The displayed check-in time should match the actual local time of registration.
Status: [fail]

### TC-004: Verify a visitor can be checked out
**Preconditions:** At least one visitor is currently active.
**Steps:**
1. Confirm the "Check Out" button is clicked for a specific visitor.
**Expected Result:** The visitor is removed from the Active Visitors list.
**Status:** [pass]

### TC-005: Verify a checked out visitor is removed from the active list
**Preconditions:** At least one visitor is currently checked in.
**Steps:**
1. Confirm a visitor is checked out.
2. Check the Active Visitors list.
**Expected Result:** The cjecked out visitor no longer appears in the Active Visitors list.
**Status:** [pass]

### TC-006: Verify a deactivated visitor is removed from the active list
**Preconditions:** At least one visitor is currently active and deactivation is triggered via the available mechanism.
**Steps:**
1. Confirm a visitor is deactivated.
2. Check the Active Visitors list.
**Expected Result:** The deactivated visitor no longer appears in the Active Visitors list.
**Status:** [fail]


### TC-007: Verify the active visitor list paginates at 20 records per page
**Preconditions:** At least 21 active visitors exist.
**Steps:**
1. Confirm page 1 displays exactly 20 records.
2. Confirm page 2 displays the remaining record(s).
**Expected Result:** Each page shows a maximum of 20 records, with additional records on the next pages.
**Status:** [pass]

---

## Negative

### TC-008: Verify registration is blocked when only a first or last name is entered
**Preconditions:** Registration form is open.
**Steps:**
1. Confirm only a first name (or only a last name) is entered in the Full Name field.
2. Confirm the "Company Name" field is filled.
3. Confirm the "Purpose" field is filled.
4. COnfirm that tha "Host" is chosen.
5. Confirm "Submit" button is clicked.
**Expected Result:** The user registration is blocked with a clear error promt to enter the Full Name.
**Status:** [fail]

### TC-009: Verify registration is blocked when Purpose is left empty
**Preconditions:** Registration form is open.
**Steps:**
1. Confirm a valid full name is entered.
2. Confirm the company name is entered.
3. Confirm that a host is chosen.
4. Confirm that the "Purpose" field is left empty.
4. Confirm "Submit" button is clicked.
**Expected Result:** The registration is blocked with a clear error prompt.
**Status:** [fail]

### TC-010: Verify registration is blocked when Company Name is left empty
**Preconditions:** Registration form is open.
**Steps:**
1. Confirm a valid full name is entered.
2. Confirm that the "Company Name" field is left empty.
3. Confirm that a host is chosen.
4. Confirm that the "Purpose" is entered.
4. Confirm "Submit" button is clicked.
**Expected Result:** The registration is blocked with a clear error prompt.
**Status:** [fail]

### TC-011: Verify registration is blocked when the Full Name field contains numbers
**Preconditions:** Registration form is open.
**Steps:**
1. Confirm "1234" (or similar numeric-only value) is entered in the Full Name field.
2. Confirm full name, company name, host, and purpose are filled with valid input data.
3. Confirm "Submit" is clicked.
**Expected Result:** Submission is blocked with a clear error prompt.
**Status:** [fail]

### TC-012: Verify registration is blocked when the Full Name field contains only special characters
**Preconditions:** Registration form is open.
**Steps:**
1. Confirm "&*()#$" (or similar special-character-only text) is entered in the Full Name field.
2. Confirm full name, company name, host, and purpose are filled with valid input data.
3. Confirm "Submit" is clicked.
**Expected Result:** Submission is blocked with a clear error prompt.
**Status:** [fail]




---

## Boundary

### TC-013: Verify pagination correctly shows no "Next" page at exactly 20 records
**Preconditions:** Exactly 20 active visitors exist.
**Steps:**
1. Confirm all 20 visitors are visible on page 1.
2. Check whether a "Next" page button is accessible.
**Expected Result:** No "Next" page is accessible, since no records exist beyond page 1.
**Status:** [fail]

### TC-014: Verify pagination correctly shows a "Next" page at 21 records
**Preconditions:** Exactly 21 active visitors exist.
**Steps:**
1. Confirm page 1 displays 20 records.
2. Confirm a "Next" page is accessible and displays the 21st record.
**Expected Result:** Page 2 is accessible and shows exactly 1 record.
**Status:** [pass]

### TC-015: Verify the active visitor list displays correctly with zero visitors when their are no visitors
**Preconditions:** No active visitors exist.
**Steps:**
1. Check the Active Visitors list.
**Expected Result:** An empty state is shown, with no errors and no broken layout.
**Status:** [pass]


### TC-016: Verify that the "Previous" button is disabled when there is exactly 1 page
**Preconditions:** At least one visitor exists.
**Steps:**
1. Check the Active Visitors list.
**Expected Result:** The "Previous" button on the page is not clickable.
**Status:** [pass]

### TC-017: Verify registration is blocked when the Full Name field contains only a single character
**Preconditions:** Registration form is open.
**Steps:**
1. Confirm a single character (e.g., "A") is entered in the Full Name field.
2. Confirm the remaining fields are filled with valid data.
3. Confirm "Submit" is clicked.
**Expected Result:** Submission should be blocked, since a single character does not constitute a valid full name.
**Status:** [fail]









# Regression Subset — Minor Registration Form Update

## Scenario

A new "Email Address" field is added to the registration form so that visitors can be uniquely identified and duplicate registration can be prevented.

## Regression Test Selection

### Included Test Cases

#### TC-001: Verify a visitor can be registered with all valid fields
**Reason for inclusion:** The registration form has been modified by adding a new Email Address field. This test is included to confirm that the existing visitor registration flow continues to work after the form update.

#### TC-002: Verify a registered visitor appears on the "Active Visitor" list
**Reason for inclusion:** The registration form creates the visitor record. This test is included to confirm that adding the Email Address field does not prevent a successfully registered visitor from appearing in the Active Visitors list, and that the email address is also shown on the list alongside other information.

#### TC-003: Verify a registered visitor's check-in time reflects local time
**Reason for inclusion:** The check-in time is created during visitor registration. This test is included to confirm that the registration form update does not affect the visitor's check-in time.

#### TC-008: Verify registration is blocked when only a first or last name is entered
**Reason for inclusion:** This test covers registration input validation. It is included to confirm that existing validation behavior is not affected by adding the Email Address field.

#### TC-009: Verify registration is blocked when Purpose is left empty
**Reason for inclusion:** This test covers registration input validation. It is included to confirm that existing required-field validation continues to work after the Email Address field is added.

#### TC-010: Verify registration is blocked when Company Name is left empty
**Reason for inclusion:** This test covers registration input validation. It is included to confirm that existing required-field validation continues to work after the Email Address field is added.

#### TC-011: Verify registration is blocked when the Full Name field contains numbers
**Reason for inclusion:** This test covers registration input validation. It is included to confirm that existing required-field validation continues to work after the Email Address field is added.

#### TC-012: Verify registration is blocked when the Full Name field contains only special characters
**Reason for inclusion:** This test covers registration input validation. It is included to confirm that existing required-field validation continues to work after the Email Address field is added.



#### TC-017: Verify registration is blocked when the Full Name field contains only a single character
**Reason for inclusion:** This test covers registration input validation on the same form being modified. It is included to confirm that existing length-boundary validation behavior is unaffected by the addition of the Email Address field.

---

### Excluded Test Cases

#### TC-004: Verify a visitor can be checked out
**Reason for exclusion:** The checkout functionality is separate from the registration form and is not directly affected by adding an Email Address field.

#### TC-005: Verify a checked out visitor is removed from the active list
**Reason for exclusion:** This tests checkout/list-filtering behavior, which is unrelated to how a visitor is registered and is not affected by adding an Email Address field.

#### TC-006: Verify a deactivated visitor is removed from the active list
**Reason for exclusion:** Visitor deactivation is separate from the registration form change and is not directly affected by adding an Email Address field.

#### TC-007: Verify the active visitor list paginates at 20 records per page
**Reason for exclusion:** Pagination functionality is independent of the registration form and is not directly affected by adding an Email Address field.


#### TC-013: Verify pagination correctly shows no "Next" page at exactly 20 records
**Reason for exclusion:** Pagination functionality is not affected by the addition of an Email Address field.

#### TC-014: Verify pagination correctly shows a "Next" page at 21 records
**Reason for exclusion:** Pagination functionality is not affected by the addition of an Email Address field.

#### TC-015: Verify the active visitor list displays correctly with zero visitors
**Reason for exclusion:** The empty Active Visitors list is not directly affected by the registration form update.

#### TC-016: Verify that the "Previous" button is disabled when there is exactly 1 page
**Reason for exclusion:** Pagination controls are not directly affected by adding an Email Address field.
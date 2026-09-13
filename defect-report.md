


Defect ID: 1
Summary: Visitors are registered with an incomplete names
Type: Functional
Description: The feature states that the visitors are registered with their full name. However, there is no validation to ensure that. The visitors get registered even when only their first name, or just their last name or just a word is entered instead of their full name.
Steps to Reproduce:
i. Launch the app on the browser.
ii. Navigate towards the Visitor Registration form.
iii. Click on the "Full Name" field.
iv. Enter only First name/ Last name.
v. Enter the company name.
vi. Choose the host.
vii. Enter the Purpose for the visit.
viii. Click Submit

Expected Result: The form should require a full name through validation blocking the submission or a clear error prompt.

Actual Result: The visitor gets registered successfully and can be viewd on the "Active Visitors"list.


Defect ID: 2
Summary: Visitors are successfully registered even without their "purpose".
Type: Functional
Description: The feature states that the visitors are registered with their visit purpose. But the visitor are getting registered and shown in the active list even when their purpose is not specified.
Steps to Reproduce:
i. Launch the app on the browser.
ii. Navigate towards the Visitor Registration form.
iii. Enter the full name.
iv. Enter the company name.
v. Choose the host.
vi. Leave the "Purpose" field empty.
viii. Click on the "Submit" button.

Expected Result: The form should be stopped from getting submitted and error prompt should be shown.

Actual Result: The visitor gets registered successfully and can be viewd on the "Active Visitors"list.



Defect ID: 3
Summary: Visitors are successfully registered when they enter random numbers in the "Full Name" field.
Type: Functional
Description: In the "Full Name" field, when random numbers are entered instead of words, the visitors get successfully registered when the "Submit" button is clicked.
Steps to Reproduce:
i. Launch the app on the browser.
ii. Navigate towards the Visitor Registration form.
iii. Enter random numbers in the "Full Name" field.For eg: "1234"
iv. Enter the company name.
v. Choose the host.
vi. Enter the purpose.
viii. Click on the "Submit" button.

Expected Result: The form should be stopped from getting submitted and error prompt should be shown when numbers are getting entered in a text field.

Actual Result: The visitor gets registered successfully and can be viewd on the "Active Visitors"list.

Defect ID: 4
Summary: Visitors are successfully registered when they enter special characters in the "Full Name" field.
Type: Functional
Description: When special characteristics like "@#$%^&" are entered in the "Full Name" field instead of their actual names, the visitors get successfully registered when the "Submit" button is clicked.
Steps to Reproduce:
i. Launch the app on the browser.
ii. Navigate towards the Visitor Registration form.
iii. Enter special characteristics in the "Full Name" field.For eg: "&*()#$"
iv. Enter the company name.
v. Choose the host.
vi. Enter the purpose.
viii. Click on the "Submit" button.

Expected Result: The form should be stopped from getting submitted and error prompt should be shown when special characteristics are getting entered in a text field.

Actual Result: The visitor gets registered successfully and can be viewd on the "Active Visitors"list.


Defect ID: 5
Summary: Visitors are successfully registered when they leave the "Company Name" field empty.
Type: Functional
Description: The feature states that the visitors are registered with their company name. But the visitor are getting successfully registered and shown in the active list even when their company name is not entered.
Steps to Reproduce:
i. Launch the app on the browser.
ii. Navigate towards the Visitor Registration form.
iii. Enter Full Name.
iv. Leave the "Company Name" field empty.
v. Choose the host.
vi. Enter the purpose.
viii. Click on the "Submit" button.

Expected Result: The form should be stopped from getting submitted and error prompt should be shown when the "Company Name" field is left empty.

Actual Result: The visitor gets registered successfully and can be viewd on the "Active Visitors"list.




Defect ID: 6
Summary: "Next" page appears whenever the current page is full (20 records), even when no further records actually exist.
Type: Functional
Description: The active visitor list is paginated at 20 records per page. The app determines whether a "Next" page should be shown based solely on whether the current page contains exactly 20 records, rather than checking whether any visitor records actually exist beyond the current page. As a result, whenever a page has exactly 20 records, a "Next" page becomes accessible and displays as empty, even if no additional visitors exist beyond it. Conversely, whenever a page has fewer than 20 records, "Next" correctly disappears — and reappears again if the page count returns to exactly 20.

Steps to Reproduce:
i. Register visitors until a page (e.g., page 1) contains exactly 20 records.
ii. Observe that a "Next" page becomes accessible.
iii. Navigate to the "Next" page and confirm it displays an empty table with no visitor records.
iv. Reduce the count on the original page below 20 (e.g., check out one visitor), and confirm "Next" disappears.
v. Register a new visitor to bring the page count back to exactly 20, and confirm "Next" reappears.

Expected Result: A "Next" page should only be accessible when visitor records actually exist beyond the current page — not simply because the current page happens to contain exactly 20 records.

Actual Result: The "Next" page is shown or hidden based solely on whether the current page has exactly 20 records, regardless of whether any records actually exist beyond it.



Defect ID: 7
Summary: No button for deactivation of the visitors
Type: Functional

Description: The feature states that administrators can deactivate visitor records. However there is no button, admin panel, or any UI element that was found in the application that allows an administrator to perform this action.

Steps to Reproduce:
i. Launch the app on the browser.
ii. Look through the Active Visitors list, navigation menu, and any available pages for a way to deactivate a visitor.
iii. Confirm that no such button or option exists anywhere in the UI.

Expected Result: Administrators should have a way, within the application UI, to deactivate a visitor record.

Actual Result: No UI element exists anywhere in the application for deactivating a visitor.


Defect ID: 8
Summary: Check-in time displayed in UTC instead of local (Asia/Kathmandu) timezone
Type: Functional
Description: The spec states all times should be displayed in the receptionist's local timezone (Asia/Kathmandu). However, the "Checked In" time shown in the Active Visitors list reflects UTC time rather than local time — consistently off by approximately 5 hours 45 minutes, the UTC offset for Asia/Kathmandu. This is especially misleading near local midnight: a visitor checked in just after midnight local time can display a "Checked In" time from the previous evening (e.g., 18:19), making it appear as though they checked in the day before.

Steps to Reproduce:
i. Note the current local time on your device.
ii. Register a new visitor via the registration form.
iii. Observe the "Checked In" time shown for that visitor in the Active Visitors list.
iv. Compare the displayed time to your actual local check-in time.


Expected Result: The "Checked In" time should match the actual local time of check-in (Asia/Kathmandu), including correctly reflecting the current calendar day.

Actual Result: The displayed time is approximately 5 hours 45 minutes earlier than actual local time, consistent with an unconverted UTC timestamp being shown. Near local midnight, this causes the displayed time to appear to belong to the previous day.






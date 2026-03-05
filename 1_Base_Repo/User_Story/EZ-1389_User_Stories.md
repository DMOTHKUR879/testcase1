# User Stories - EZ-1389: Validate Received Liability Information Screen - Logic - FormType

**JIRA Issue:** [EZ-1389](https://jira-zurichna.atlassian.net/browse/EZ-1389)  
**Project:** eZdocs  
**Sprint:** IPS/eZdocs Sprint 8  
**Status:** QA in Progress  
**Priority:** TBD  
**Reporter:** Sujitha Sujitha (Contractor)  
**Assignee:** Mothkuri Divya  
**Created:** 02/10/26 | **Updated:** 03/04/26  

---

## 📋 Overview

The QA team will perform functional, UI, and validation checks on the Received Liability Information screen. All fields, controls, and behaviors must match the specifications outlined in the requirements. Any deviations, defects, or usability issues must be documented.

**Scope:** Validation of Logic - FormType behavior on the Liability Information screen in the IPS/eZdocs integration workflow.

---

## 👤 User Stories

### User Story 1: Navigate to Received Liability Submission

**As a** QA tester validating the IPS integration  
**I want to** navigate to the Received Liability LOB in EzDocs application  
**So that** I can access and validate the Liability Information screen

#### Acceptance Criteria

**AC 1.1: Login to EzDocs Application**
- [ ] User successfully logs into eZdocs application with valid credentials
- [ ] User interface loads without errors
- [ ] Navigation menu is accessible and functional

**AC 1.2: Navigate to Received Liability LOB**
- [ ] "Received Liability" option is visible in the LOB selection menu
- [ ] Clicking "Received Liability" navigates to the correct department/LOB
- [ ] The system displays available submissions for Received Liability LOB

**AC 1.3: Search Submission by IPS Contract ID**
- [ ] Search functionality accepts IPS Contract ID input
- [ ] System returns correct submission records matching the search criteria
- [ ] Search results display submission details clearly
- [ ] User can click on a submission to proceed to the next screen

#### Test Scenarios

| Scenario | Test Data | Expected Outcome | Priority |
|----------|-----------|-----------------|----------|
| Valid IPS Contract ID Search | IPS Contract ID: Valid existing ID | Submission found and accessible | P1 |
| Invalid IPS Contract ID Search | IPS Contract ID: Non-existent ID | "No results found" message displayed | P2 |
| Empty Search Field | Empty search input | Error message: "Contract ID is required" | P2 |

#### Related Test Cases
- TC-EZ-1389-001: Verify successful login to eZdocs application
- TC-EZ-1389-002: Verify navigation to Received Liability LOB
- TC-EZ-1389-003: Verify IPS Contract ID search functionality

---

### User Story 2: Access IPS Admin Screen via CIIM

**As a** QA tester validating the IPS-CIIM integration  
**I want to** click "Show CIIM" button to access the IPS Admin screen  
**So that** I can enter and verify data in the CIIM interface

#### Acceptance Criteria

**AC 2.1: CIIM Button Availability**
- [ ] "Show CIIM" button is visible on the Liability Information screen
- [ ] Button is enabled and clickable
- [ ] Button label is clear and descriptive

**AC 2.2: Navigation to IPS Admin Screen**
- [ ] Clicking "Show CIIM" navigates to the IPS Admin screen
- [ ] Navigation occurs without errors or page refresh delays
- [ ] The IPS Admin screen loads with all required tabs visible
- [ ] No data is lost during navigation

**AC 2.3: Screen State and Data Persistence**
- [ ] User can return to the original Information screen from IPS Admin
- [ ] Previously entered data remains intact if navigation occurs
- [ ] Session maintains continuity throughout the workflow

#### Test Scenarios

| Scenario | Test Data | Expected Outcome | Priority |
|----------|-----------|-----------------|----------|
| Initial CIIM Access | Fresh submission loaded | IPS Admin screen loads successfully | P1 |
| CIIM Access with Partial Data | Submission with some fields filled | All previously entered data visible in CIIM | P1 |
| CIIM Navigation from Different Submissions | Multiple submissions | Correct submission data displayed in CIIM | P2 |
| Network Lag Simulation | Slow network conditions | Navigation completes without errors | P2 |

#### Related Test Cases
- TC-EZ-1389-004: Verify "Show CIIM" button visibility and state
- TC-EZ-1389-005: Verify successful navigation to IPS Admin screen
- TC-EZ-1389-006: Verify data persistence during CIIM navigation

---

### User Story 3: Configure Logic - FormType in Information Tab

**As a** QA tester validating form type logic  
**I want to** configure the "Logic - FormType" field in the Information tab  
**So that** the system correctly determines the form type based on claims trigger scenarios

#### Acceptance Criteria

**AC 3.1: FormType Field Visibility**
- [ ] "Logic - FormType" field is visible in the Information tab of CIIM
- [ ] Field label is clearly displayed with descriptive text
- [ ] Field is located in the "Employee Benefits Retroactive Date" section
- [ ] Field status (required/optional) is indicated

**AC 3.2: FormType Logic - Occurrence Scenario**
- [ ] When Claims Trigger = "Occurrence", FormType value populates as "Occurrence"
- [ ] This behavior matches IPS system expectations
- [ ] The value is correctly synced to eZdocs
- [ ] No manual override is needed for this scenario

**AC 3.3: FormType Logic - Claims-made Scenario**
- [ ] When Claims Trigger = "Claims-made", FormType value populates as "Claims-made"
- [ ] This behavior matches IPS system expectations
- [ ] The value is correctly synced to eZdocs
- [ ] No manual override is needed for this scenario

**AC 3.4: FormType Logic - Others Scenario**
- [ ] When Claims Trigger contains other/unknown values, FormType field displays as empty
- [ ] System does not default invalid values
- [ ] User is prompted to review or manually configure if needed

**AC 3.5: Field Validation**
- [ ] FormType field cannot be manually edited if auto-populated by logic
- [ ] If allowed to edit, system validates entries against allowed values
- [ ] Invalid entries trigger clear error messages

#### Test Scenarios

| Scenario | Claims Trigger Value | Expected FormType | Tab Location | Status | Priority |
|----------|-------------------|-------------------|--------------|--------|----------|
| Occurrence Claims Trigger | "Occurrence" | "Occurrence" | Information | Auto-populated | P1 |
| Claims-made Claims Trigger | "Claims-made" | "Claims-made" | Information | Auto-populated | P1 |
| Unknown Claims Trigger | "Unknown" or empty | Empty/blank | Information | Requires manual input | P2 |
| Multiple Form Submissions | IPS and ezDocs | Consistent values across both systems | Information | Synced | P1 |

#### Screenshot/Field Reference
**Page:** LiabilityCoverage  
**Tab:** Information  
**Section:** Employee Benefits Retroactive Date  
**Field Name:** Form Type  
**Action:** IPS Check  
**Actual Value:** Logic - FormType

#### Related Test Cases
- TC-EZ-1389-007: Verify FormType field visibility and location
- TC-EZ-1389-008: Verify FormType populates "Occurrence" correctly
- TC-EZ-1389-009: Verify FormType populates "Claims-made" correctly
- TC-EZ-1389-010: Verify FormType handles other/empty scenarios

---

### User Story 4: Save Data in IPS Admin Screen

**As a** QA tester validating the save functionality  
**I want to** save data entered in the CIIM/IPS Admin screen  
**So that** the changes are persisted and I can proceed to sync with eZdocs

#### Acceptance Criteria

**AC 4.1: Save Button Functionality**
- [ ] "Save" button is visible and enabled after data entry
- [ ] Clicking "Save" processes the data without errors
- [ ] System validates all required fields before allowing save
- [ ] User receives confirmation that save was successful

**AC 4.2: Redirect to eZdocs Screen**
- [ ] After successful save, user is redirected back to the eZdocs Information screen
- [ ] Redirect occurs promptly without excessive delay
- [ ] No data is lost during the redirect process
- [ ] The correct submission record is displayed

**AC 4.3: Data Persistence After Save**
- [ ] All entered data is retained in the CIIM system
- [ ] Data is available for subsequent sync operation
- [ ] User can navigate away and return to find saved data intact
- [ ] Saved data is locked from unintended modification

**AC 4.4: Error Handling During Save**
- [ ] If validation fails, clear error messages identify missing/invalid fields
- [ ] System highlights problematic fields for user correction
- [ ] User is not redirected until save is successful
- [ ] User can correct errors and retry save

#### Test Scenarios

| Scenario | Data State | Expected Outcome | Priority |
|----------|-----------|-----------------|----------|
| Valid Complete Data | All required fields filled correctly | Save successful, redirect to eZdocs | P1 |
| Missing Required Fields | One or more required fields empty | Save fails with specific field error | P1 |
| Invalid Data Format | Field contains invalid format | Save fails with format error | P2 |
| Partial Data Entry | Some optional fields empty | Save succeeds (required fields complete) | P2 |
| Network Interruption | Connection lost during save | Graceful error handling, rollback data | P2 |
| Large Data Set | Multiple records in various fields | Save completes successfully with no timeouts | P3 |

#### Related Test Cases
- TC-EZ-1389-011: Verify Save button visibility and state
- TC-EZ-1389-012: Verify save validation for required fields
- TC-EZ-1389-013: Verify redirect to eZdocs after successful save
- TC-EZ-1389-014: Verify error handling for invalid data

---

### User Story 5: Sync CIIM Data with eZdocs

**As a** QA tester validating the sync functionality  
**I want to** click "Sync CIIM" on the eZdocs screen to synchronize data  
**So that** the data entered in CIIM is correctly populated and reflected in eZdocs

#### Acceptance Criteria

**AC 5.1: Sync CIIM Button Availability**
- [ ] "Sync CIIM" button is visible on the eZdocs Information screen
- [ ] Button is enabled and clickable
- [ ] Button is positioned logically near other action buttons
- [ ] Button label is clear: "Sync CIIM" or "Sync Data"

**AC 5.2: Data Synchronization Process**
- [ ] Clicking "Sync CIIM" initiates the synchronization process
- [ ] System connects to the CIIM/IPS system without errors
- [ ] All saved data from CIIM is retrieved successfully
- [ ] Synchronization completes in a reasonable timeframe (< 5 seconds)

**AC 5.3: Data Population in eZdocs**
- [ ] FormType field correctly displays the synchronized value
- [ ] All other fields synced from CIIM display correctly
- [ ] Numeric fields maintain precision and format
- [ ] Date fields display in the correct format (MM/DD/YYYY or per requirements)
- [ ] Selected values (dropdowns, radio buttons) are correctly populated

**AC 5.4: Sync Confirmation and Feedback**
- [ ] User receives confirmation message: "Data synced successfully"
- [ ] Confirmation message displays long enough for user to read
- [ ] System indicates which fields were updated during sync
- [ ] Status indicator shows sync completion (checkmark, success message, etc.)

**AC 5.5: Error Handling During Sync**
- [ ] If sync fails, clear error message explains the issue
- [ ] Error message suggests remediation steps if applicable
- [ ] Failed sync does not overwrite existing eZdocs data
- [ ] User can retry sync operation

**AC 5.6: Data Validation After Sync**
- [ ] Synced data passes all validation rules in eZdocs
- [ ] FormType value is recognized as valid by eZdocs system
- [ ] No data transformation or corruption occurs during sync
- [ ] Synced data is immediately usable for further processing

#### Test Scenarios

| Scenario | CIIM Data | Expected Result | Sync Status | Priority |
|----------|-----------|-----------------|------------|----------|
| Complete Valid Data Sync | All fields valid in CIIM | All fields populated correctly in eZdocs | Success | P1 |
| FormType Occurrence Sync | FormType = "Occurrence" | eZdocs displays "Occurrence" | Success | P1 |
| FormType ClaimsMade Sync | FormType = "Claims-made" | eZdocs displays "Claims-made" | Success | P1 |
| Partial Data Sync | Some optional fields empty in CIIM | eZdocs shows empty fields, required fields populated | Success | P2 |
| No New Data to Sync | CIIM data unchanged since last sync | eZdocs shows current data, no unnecessary changes | Success | P3 |
| CIIM Connection Failure | Cannot reach CIIM/IPS server | "Connection failed" error, retry option provided | Failed | P1 |
| Data Type Mismatch | CIIM sends incompatible data type | Data conversion or error message | Partial | P2 |
| Empty CIIM Response | CIIM returns no data | "No data available to sync" message | Failed | P2 |

#### Related Test Cases
- TC-EZ-1389-015: Verify "Sync CIIM" button visibility and state
- TC-EZ-1389-016: Verify successful data synchronization process
- TC-EZ-1389-017: Verify FormType displays correctly after sync
- TC-EZ-1389-018: Verify data validation after sync
- TC-EZ-1389-019: Verify error handling during sync failure
- TC-EZ-1389-020: Verify sync confirmation feedback to user

---

### User Story 6: Validate Logic - FormType Field UI and Behavior

**As a** a QA tester validating UI compliance  
**I want to** verify that the Logic - FormType field meets UI and usability standards  
**So that** the feature provides a consistent, professional user experience

#### Acceptance Criteria

**AC 6.1: Field Display**
- [ ] FormType field displays with proper spacing and alignment
- [ ] Field label "Form Type" or "Logic - FormType" is clearly visible
- [ ] Field label is properly associated with the input control (accessibility)
- [ ] Field width accommodates all expected values without truncation

**AC 6.2: Field State Indicators**
- [ ] Required field indicator (*) is displayed if applicable
- [ ] Read-only or disabled state is visually distinct from editable fields
- [ ] Field background color matches design standards
- [ ] Field border/focus state provides clear visual feedback

**AC 6.3: Value Display**
- [ ] Auto-populated values display in correct format
- [ ] Values are legible with appropriate font size and color
- [ ] Dropdown/select controls (if applicable) display cleanly
- [ ] No overlapping text or visual glitches

**AC 6.4: Help Text and Tooltips**
- [ ] Help text or tooltip explains FormType purpose if provided
- [ ] Help text is accessible to screen readers
- [ ] Tooltip appears on hover without blocking other content
- [ ] If no help text exists, consider adding: "Determined by Claims Trigger value"

**AC 6.5: Responsive Design**
- [ ] Field displays correctly on desktop browsers (Chrome, Firefox, Safari, Edge)
- [ ] Field displays correctly on tablet devices
- [ ] Field displays correctly on mobile devices (if applicable)
- [ ] No horizontal scrolling required in normal viewport sizes

**AC 6.6: Error Display (if applicable)**
- [ ] Validation errors display near the field with clear message
- [ ] Error message text is red or uses standard error styling
- [ ] Error does not persist after user corrects the issue
- [ ] Error messages are accessible to assistive technology

#### Test Scenarios

| Scenario | Browser/Device | Expected Outcome | Priority |
|----------|----------------|-----------------|----------|
| Desktop Display - Chrome | Chrome latest | Field displays correctly with proper spacing | P2 |
| Desktop Display - Firefox | Firefox latest | Field displays correctly with proper spacing | P2 |
| Desktop Display - Safari | Safari latest | Field displays correctly with proper spacing | P2 |
| Desktop Display - Edge | Edge latest | Field displays correctly with proper spacing | P2 |
| Tablet Display | iPad/Android tablet | Field and label responsive, readable text | P2 |
| Mobile Display | iPhone/Android phone | Field responsive, appropriately sized for touch | P3 |
| High Contrast Mode | Windows High Contrast | Text and field clearly visible | P3 |
| Screen Reader | NVDA/JAWS | Field label announced, value readable | P3 |

#### Related Test Cases
- TC-EZ-1389-021: Verify FormType field displays correctly on desktop
- TC-EZ-1389-022: Verify FormType field displays correctly on mobile
- TC-EZ-1389-023: Verify FormType field is accessible to screen readers
- TC-EZ-1389-024: Verify FormType field error display styling

---

## 📋 Test Case Summary

### Test Case Mapping

| User Story | Test Case ID | Test Case Name | Test Type | Priority | Status |
|------------|-------------|----------------|-----------|----------|--------|
| US-1 | TC-EZ-1389-001 | Verify successful login to eZdocs application | Functional | P1 | Todo |
| US-1 | TC-EZ-1389-002 | Verify navigation to Received Liability LOB | Functional | P1 | Todo |
| US-1 | TC-EZ-1389-003 | Verify IPS Contract ID search functionality | Functional | P1 | Todo |
| US-2 | TC-EZ-1389-004 | Verify "Show CIIM" button visibility and state | Functional | P1 | Todo |
| US-2 | TC-EZ-1389-005 | Verify successful navigation to IPS Admin screen | Functional | P1 | Todo |
| US-2 | TC-EZ-1389-006 | Verify data persistence during CIIM navigation | Functional | P2 | Todo |
| US-3 | TC-EZ-1389-007 | Verify FormType field visibility and location | Functional | P1 | Todo |
| US-3 | TC-EZ-1389-008 | Verify FormType populates "Occurrence" correctly | Functional | P1 | Todo |
| US-3 | TC-EZ-1389-009 | Verify FormType populates "Claims-made" correctly | Functional | P1 | Todo |
| US-3 | TC-EZ-1389-010 | Verify FormType handles other/empty scenarios | Functional | P2 | Todo |
| US-4 | TC-EZ-1389-011 | Verify Save button visibility and state | Functional | P1 | Todo |
| US-4 | TC-EZ-1389-012 | Verify save validation for required fields | Functional | P1 | Todo |
| US-4 | TC-EZ-1389-013 | Verify redirect to eZdocs after successful save | Functional | P1 | Todo |
| US-4 | TC-EZ-1389-014 | Verify error handling for invalid data | Functional | P2 | Todo |
| US-5 | TC-EZ-1389-015 | Verify "Sync CIIM" button visibility and state | Functional | P1 | Todo |
| US-5 | TC-EZ-1389-016 | Verify successful data synchronization process | Functional | P1 | Todo |
| US-5 | TC-EZ-1389-017 | Verify FormType displays correctly after sync | Functional | P1 | Todo |
| US-5 | TC-EZ-1389-018 | Verify data validation after sync | Functional | P1 | Todo |
| US-5 | TC-EZ-1389-019 | Verify error handling during sync failure | Functional | P1 | Todo |
| US-5 | TC-EZ-1389-020 | Verify sync confirmation feedback to user | Functional | P2 | Todo |
| US-6 | TC-EZ-1389-021 | Verify FormType field displays correctly on desktop | UI/UX | P2 | Todo |
| US-6 | TC-EZ-1389-022 | Verify FormType field displays correctly on mobile | UI/UX | P2 | Todo |
| US-6 | TC-EZ-1389-023 | Verify FormType field is accessible to screen readers | Accessibility | P3 | Todo |
| US-6 | TC-EZ-1389-024 | Verify FormType field error display styling | UI/UX | P2 | Todo |

---

## 🔄 Navigation Workflow

### Complete User Journey

```
1. Login to eZdocs Application
   ↓
2. Navigate to Received Liability LOB
   ↓
3. Search for Submission (using IPS Contract ID)
   ↓
4. Select Submission from Results
   ↓
5. Navigate to Information Screen
   ↓
6. Click "Show CIIM" Button
   ↓
7. → Access IPS Admin Screen
   ↓
8. Configure Form Fields (including Logic - FormType)
   ↓
9. Click "Save" Button
   ↓
10. Redirect to eZdocs Information Screen
    ↓
11. Click "Sync CIIM" Button
    ↓
12. System Synchronizes Data from IPS to eZdocs
    ↓
13. FormType Field Displays Synchronized Value
    ↓
14. Confirmation Message: "Data synced successfully"
    ↓
15. [Submission Ready for Further Processing]
```

### Key Navigation Points

- **eZdocs Screen → IPS Admin Screen:** Click "Show CIIM" button
- **IPS Admin Screen → eZdocs Screen:** Click "Save" button
- **Data Sync on eZdocs Screen:** Click "Sync CIIM" button

---

## 📊 Business Logic Reference

### Logic - FormType Field Behavior

Based on the requirement specifications and test templates:

**Field Location:**
- Page: LiabilityCoverage
- Tab: Information  
- Section: Employee Benefits Retroactive Date
- Field Name: Form Type

**Logic Rules:**

| Claims Trigger | Form Type Value | IPS Check | Behavior |
|---|---|---|---|
| Occurrence | "Occurrence" | Logic - FormType | Auto-populated from IPS |
| Claims-made | "Claims-made" | Logic - FormType | Auto-populated from IPS |
| Other/Unknown | Empty | Logic - FormType | Manual entry or system prompt |

**Data Flow:**
1. User selects Claims Trigger value in CIIM
2. System evaluates Logic - FormType rules
3. FormType field defaults to matching value or remains empty
4. User saves data in CIIM
5. "Sync CIIM" on eZdocs retrieves and populates all fields
6. FormType value displays correctly in eZdocs Information screen

---

## ✅ Definition of Done

### For Developers

- [ ] Logic - FormType field implementation complete
- [ ] FormType correctly defaults based on Claims Trigger value
- [ ] Data synchronization between IPS and eZdocs functional
- [ ] All fields persist correctly through save/sync operations
- [ ] Error handling implemented for sync failures
- [ ] Code reviewed and approved
- [ ] Unit tests written and passing
- [ ] Integration tests with eZdocs backend completed

### For QA

- [ ] All 24 test cases executed and passing (P1: 15/24, P2: 6/24, P3: 3/24)
- [ ] Functional verification on all supported browsers
- [ ] UI/UX validation complete
- [ ] Accessibility testing completed
- [ ] Error scenarios tested and documented
- [ ] Data integrity verified through full workflow
- [ ] Performance acceptable (sync < 5 seconds)
- [ ] Documentation/screenshots captured

### For Product/Business

- [ ] Meets all requirements from Received Liability Master spreadsheet
- [ ] Business logic validated by stakeholders
- [ ] No data loss in sync operations
- [ ] Compliant with IPS integration specifications
- [ ] Ready for production deployment

---

## 📎 Reference Materials

- **Received Liability Master.xlsx:** [Sharepoint Link - Business Requirements](https://zurichinsurancecan.sharepoint.com/:x:/r/sites/FMZTCSpreSOWspace/Shared%20Documents/General/IPS_CIIM_ezDocs%20Integration/IPS%20Integration%20-%20Master%20Sheets/Received%20Liability%20Master.xlsx)
- **Original JIRA Story:** EZ-1389
- **Cloned from:** EZ-1231 (Map IPS data with Liability Received)
- **Related Documentation:** Navigation Steps, Test Templates

---

## 📝 Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 03/05/2026 | QA Team | Initial comprehensive user stories generated from EZ-1389 JIRA ticket, CSV logic specifications, navigation workflow, and test templates |

---

**Generated from:**
- 1_Base_Repo/User_Story/EZ-1389.doc
- 1_Base_Repo/User_Story/EZ-1389 logic.csv
- 1_Base_Repo/Reference/navigation_steps.md
- 1_Base_Repo/Template/template.md

**Status:** Ready for Development/QA Execution

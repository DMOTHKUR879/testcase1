# EZ-1395: Detailed User Stories - Received Liability Forms Screen Logic Validation

**JIRA Issue:** EZ-1395  
**Title:** QA - IPSIntegration - Validate Received Liability Forms Screen - Logic - Default  
**Status:** QA in progress  
**Priority:** TBD  
**Sprint:** IPS/eZdocs Sprint 9  
**Created:** 02/10/26 | **Updated:** 03/09/26  
**Assignee:** Mothkuri Divya  
**Project:** eZdocs  

---

## Overview

The QA team will perform functional, UI, and validation checks on the Liability Forms screen. All fields, controls, and behaviors must match the specifications outlined in the provided requirements. Any deviations, defects, or usability issues must be documented. The focus is on verifying the Action Values Scenarios in the Logic tab.

---

## US-001: Verify Commercial General Liability Policy Declarations Form - Logic Default

**User Story ID:** EZ-1395-US-001  
**Form Type:** Mandatory  
**Form Name:** Commercial General Liability Policy Declarations  
**Form ID:** ZC-RC-20321 U  
**Language:** English  
**Edition Number:** 0623b  
**Action:** Logic - Default  

### Description
As a QA Engineer, I want to verify that the Commercial General Liability Policy Declarations form correctly applies the Logic - Default action and synchronizes data from the IPS Admin screen back to the EzDocs application so that business users can rely on accurate and consistent data across both systems.

### Navigation Steps
1. Log in to the EzDocs application and navigate to the "Received Liability" LOB
2. Search for a new submission under Received Liability by using IPS Contract ID and click on the submission to proceed to the next information screen
3. Click on "Show CIIM" to navigate to the IPS Admin screen
4. Enter the required data in the appropriate tabs for the Commercial General Liability Policy Declarations form (Form ID: ZC-RC-20321 U)
5. Click on "Save" and verify you are redirected back to the EzDocs screen
6. On the EzDocs screen, click on "Sync CIIM" to ensure the data is synced and populated correctly

### Acceptance Criteria
- [ ] User is able to successfully navigate to the Received Liability LOB
- [ ] User can search and select a submission using IPS Contract ID
- [ ] "Show CIIM" button opens the IPS Admin screen without errors
- [ ] User can input data for the Commercial General Liability Policy Declarations form with Edition 0623b
- [ ] "Save" button successfully saves data and redirects to EzDocs screen
- [ ] "Sync CIIM" button triggers synchronization without errors
- [ ] Form data (ZC-RC-20321 U) populates correctly on EzDocs under mandatory forms section
- [ ] Logic - Default action is applied and data matches between IPS Admin and EzDocs
- [ ] No validation errors or data corruption occurs during the sync process

### Test Scenarios
| Scenario | Expected Result | Status |
|----------|-----------------|--------|
| Default values load in Logic tab for form ZC-RC-20321 U | Correct default values populate | Todo |
| User modifies default values and saves | Changes persist on EzDocs screen | Todo |
| Sync CIIM executes without data loss | All data from IPS Admin appears on EzDocs | Todo |
| Form displays in correct language (English) | UI text and labels appear in English | Todo |
| Edition 0623b is correctly referenced | Correct form version is used | Todo |

---

## US-002: Verify Statutory Conditions, General Conditions and Other Conditions Form - Logic Default

**User Story ID:** EZ-1395-US-002  
**Form Type:** Mandatory  
**Form Name:** Statutory Conditions, General Conditions and Other Conditions  
**Form ID:** ZC 6300 U  
**Language:** English  
**Edition Number:** 122  
**Action:** Logic - Default  

### Description
As a QA Engineer, I want to verify that the Statutory Conditions, General Conditions and Other Conditions form correctly applies the Logic - Default action and ensures seamless data synchronization between IPS Admin and EzDocs so that compliance requirements are met without manual intervention.

### Navigation Steps
1. Log in to the EzDocs application and navigate to the "Received Liability" LOB
2. Search for a submission under Received Liability using IPS Contract ID and proceed to the next screen
3. Click on "Show CIIM" to open the IPS Admin screen
4. Access the Statutory Conditions, General Conditions and Other Conditions form data entry area (Form ID: ZC 6300 U, Edition 122)
5. Enter all required data fields as specified in the system requirements
6. Click "Save" to persist changes and return to the EzDocs screen
7. Execute "Sync CIIM" to verify data synchronization and population

### Acceptance Criteria
- [ ] Form ZC 6300 U (Edition 122) is accessible in the IPS Admin screen
- [ ] All mandatory fields for Statutory Conditions, General Conditions, and Other Conditions are editable
- [ ] Default values for Logic - Default action populate correctly
- [ ] Save operation completes without errors
- [ ] User is redirected to EzDocs after save
- [ ] Sync CIIM operation successfully synchronizes the form data
- [ ] Form data appears under mandatory forms section on EzDocs
- [ ] No data loss or validation failures occur during synchronization
- [ ] Edition 122 is consistently referenced throughout the process

### Test Scenarios
| Scenario | Expected Result | Status |
|----------|-----------------|--------|
| Load form ZC 6300 U in IPS Admin | Form loads with Edition 122 and default values | Todo |
| Enter custom data and save | Data persists and sync is triggered | Todo |
| Verify sync completion | All data appears on EzDocs mandatory forms | Todo |
| Check edition number reference | Edition 122 is correctly displayed | Todo |
| Validate required field enforcement | System prevents save without required fields | Todo |

---

## US-003: Verify Commercial General Liability Policy Form - Logic Default

**User Story ID:** EZ-1395-US-003  
**Form Type:** Mandatory  
**Form Name:** Commercial General Liability Policy  
**Form ID:** ZC 20041 U  
**Language:** English  
**Edition Number:** 0522b  
**Action:** Logic - Default  

### Description
As a QA Engineer, I want to ensure the Commercial General Liability Policy form applies the Logic - Default action correctly and maintains data integrity during synchronization from IPS Admin to EzDocs so that liability policies are accurately reflected in the system.

### Navigation Steps
1. Log in to the EzDocs application and navigate to the "Received Liability" LOB
2. Search and open a submission using the IPS Contract ID
3. Navigate to the next information screen and click "Show CIIM"
4. In the IPS Admin screen, locate the Commercial General Liability Policy form (Form ID: ZC 20041 U)
5. Complete all required data fields for the policy (Edition 0522b)
6. Click "Save" to confirm all entries and return to EzDocs
7. Click "Sync CIIM" to synchronize the policy data with the EzDocs system

### Acceptance Criteria
- [ ] Commercial General Liability Policy form (ZC 20041 U) loads in IPS Admin screen
- [ ] Edition 0522b is correctly associated with the form
- [ ] Logic - Default action populates appropriate default values
- [ ] All form fields are accessible and editable
- [ ] Save operation executes successfully without validation errors
- [ ] User is returned to the EzDocs screen after save
- [ ] Sync CIIM retrieves and displays the policy data on EzDocs
- [ ] Form data appears in the mandatory forms section
- [ ] Policy details remain accurate and unaltered after synchronization

### Test Scenarios
| Scenario | Expected Result | Status |
|----------|-----------------|--------|
| Form ZC 20041 U loads with defaults | Form displays with Logic - Default values applied | Todo |
| User completes the policy form | All fields accept input without errors | Todo |
| Save and sync completes | Data appears on EzDocs mandatory forms | Todo |
| Verify edition 0522b reference | Correct form version is consistently used | Todo |
| Check data integrity post-sync | No data corruption or missing values | Todo |

---

## US-004: Verify International Program - Local Policy Conditions Endorsement - Logic Default

**User Story ID:** EZ-1395-US-004  
**Form Type:** Endorsements  
**Form Name:** International Program – Local Policy Conditions  
**Form ID:** ZC-RC-20324 U  
**Language:** English  
**Edition Number:** 623  
**Action:** Logic - Default  

### Description
As a QA Engineer, I want to verify that the International Program – Local Policy Conditions endorsement correctly applies the Logic - Default action and synchronizes with EzDocs so that international policy conditions are properly managed and reflected in endorsement records.

### Navigation Steps
1. Log in to the EzDocs application and navigate to the "Received Liability" LOB
2. Search for and select a submission using the IPS Contract ID
3. Proceed to the next information screen and click "Show CIIM"
4. In the IPS Admin screen, navigate to the endorsements section
5. Locate the International Program – Local Policy Conditions form (Form ID: ZC-RC-20324 U, Edition 623)
6. Enter the required endorsement data in the appropriate fields
7. Click "Save" to confirm and return to EzDocs
8. Click "Sync CIIM" to synchronize the endorsement data

### Acceptance Criteria
- [ ] International Program – Local Policy Conditions form (ZC-RC-20324 U) is accessible in endorsements section
- [ ] Edition 623 is correctly associated with the form
- [ ] Logic - Default action applies appropriate default values for international policies
- [ ] All endorsement fields are editable and accept input
- [ ] Save operation completes without errors
- [ ] User is redirected to EzDocs after save
- [ ] Sync CIIM successfully synchronizes the endorsement data
- [ ] Endorsement data appears in the endorsements section on EzDocs
- [ ] International policy conditions are accurately reflected in the system

### Test Scenarios
| Scenario | Expected Result | Status |
|----------|-----------------|--------|
| Load endorsement form ZC-RC-20324 U | Form displays with Edition 623 selected | Todo |
| Apply Logic - Default action | Default values for international programs load | Todo |
| Enter endorsement data | All fields accept input without validation issues | Todo |
| Save and return to EzDocs | Redirect confirms successful save | Todo |
| Sync and verify on EzDocs | Endorsement appears in endorsements section | Todo |

---

## US-005: Verify Canadian Forest or Prairie Firefighting Expenses Endorsement - Logic Default

**User Story ID:** EZ-1395-US-005  
**Form Type:** Endorsements  
**Form Name:** Canadian Forest or Prairie Firefighting Expenses Endorsement  
**Form ID:** ZC 20157 U  
**Language:** English  
**Edition Number:** 321  
**Action:** Logic - Default  

### Description
As a QA Engineer, I want to ensure the Canadian Forest or Prairie Firefighting Expenses Endorsement correctly applies the Logic - Default action and maintains accurate synchronization between the IPS Admin and EzDocs systems so that firefighting expense endorsements are properly documented and accessible.

### Navigation Steps
1. Log in to the EzDocs application and navigate to the "Received Liability" LOB
2. Search and select a submission using the IPS Contract ID
3. Click on the next information screen and select "Show CIIM"
4. In the IPS Admin screen, navigate to the endorsements section
5. Locate the Canadian Forest or Prairie Firefighting Expenses Endorsement (Form ID: ZC 20157 U, Edition 321)
6. Enter all required firefighting expense endorsement data
7. Click "Save" to persist changes and return to EzDocs
8. Click "Sync CIIM" to synchronize the endorsement with EzDocs

### Acceptance Criteria
- [ ] Canadian Forest or Prairie Firefighting Expenses Endorsement form (ZC 20157 U) is available in the endorsements section
- [ ] Edition 321 is correctly associated with the endorsement form
- [ ] Logic - Default action applies correct default values for firefighting expenses
- [ ] All endorsement fields are accessible and editable
- [ ] Save operation completes successfully
- [ ] Redirect to EzDocs confirms successful save
- [ ] Sync CIIM synchronizes the endorsement data without errors
- [ ] Endorsement appears in the endorsements section on EzDocs
- [ ] Firefighting expense data is accurate and complete after synchronization

### Test Scenarios
| Scenario | Expected Result | Status |
|----------|-----------------|--------|
| Load endorsement form ZC 20157 U | Form displays with Edition 321 and defaults | Todo |
| Logic - Default populates firefighting defaults | Appropriate default values apply | Todo |
| Complete endorsement data entry | All fields accept input correctly | Todo |
| Save and return to EzDocs | User is successfully redirected | Todo |
| Sync and verify on EzDocs | Endorsement data appears in endorsements section | Todo |

---

## Summary of Test Coverage

| User Story | Form ID | Form Type | Edition | Status |
|-----------|---------|-----------|---------|--------|
| US-001 | ZC-RC-20321 U | Mandatory | 0623b | Todo |
| US-002 | ZC 6300 U | Mandatory | 122 | Todo |
| US-003 | ZC 20041 U | Mandatory | 0522b | Todo |
| US-004 | ZC-RC-20324 U | Endorsements | 623 | Todo |
| US-005 | ZC 20157 U | Endorsements | 321 | Todo |

**Total User Stories:** 5  
**Total Test Scenarios:** 25  
**Language:** English  
**Action Type:** Logic - Default  

---

## Key Testing Considerations

1. **Data Synchronization:** Verify that all data entered in IPS Admin screen appears correctly on EzDocs after Sync CIIM
2. **Default Values:** Confirm that Logic - Default action applies appropriate default values for each form
3. **Data Integrity:** Ensure no data loss or corruption occurs during synchronization
4. **Navigation Flow:** Verify the complete navigation path from EzDocs to IPS Admin and back
5. **Form Identification:** Confirm each form loads with the correct Form ID and Edition number
6. **Language Consistency:** Ensure all forms display in English as specified
7. **Validation Rules:** Test that required fields are enforced and validation errors are handled correctly

---

## Notes for QA Team

- All mandatory forms must be tested in the same submission lifecycle
- Endorsement forms should be tested separately to ensure proper categorization
- Document any deviations from the expected behavior
- Log timestamps for synchronization operations
- Verify data at both IPS Admin and EzDocs ends for each test case
- Test with various data types and values to ensure robustness
- Validate that the system handles concurrent sync operations correctly

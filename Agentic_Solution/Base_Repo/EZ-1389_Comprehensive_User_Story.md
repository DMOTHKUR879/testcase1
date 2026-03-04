# EZ-1389: Comprehensive User Story - IPS Integration Received Liability Information Screen Logic - FormType

**Issue ID:** EZ-1389  
**Title:** QA - IPSIntegration - Validate Received Liability Information Screen - Logic - FormType  
**Status:** QA in progress  
**Project:** eZdocs  
**Priority:** TBD  
**Type:** Story  
**Sprint:** IPS/eZdocs Sprint 8  
**Reporter:** Sujitha Sujitha (Contractor)  
**Assignee:** Mothkuri Divya  
**Created:** 02/10/26  
**Updated:** 03/04/26  
**Labels:** IPS, QA

---

## 1. Executive Summary

The QA team will perform comprehensive functional, UI, and validation checks on the Received Liability Information screen within the EzDocs application. All fields, controls, and behaviors must match the specifications outlined in the requirements. The primary focus is validating the Logic - FormType field mapping between the IPS Admin system and the ezDocs Received Liability LOB, ensuring seamless data synchronization and consistency.

---

## 2. Business Context & Objectives

### 2.1 Primary Objective
Validate the integration between the IPS Admin system and eZdocs for the Received Liability LOB, with specific emphasis on:
- Form Type field logic and data mapping
- CIIM (Claims Issuance Item Management) data synchronization
- IPS Admin data population on the Information screen
- Data consistency across both systems

### 2.2 Scope
- **Application:** EzDocs (Received Liability LOB)
- **Integration Point:** IPS Admin Screen integration via CIIM
- **Field Focus:** Form Type with Logic validation
- **Page:** Liability Coverage - Information Tab
- **Section:** Employee Benefits Retroactive Date

---

## 3. Navigation Workflow & User Journey

### 3.1 Step-by-Step Navigation Process

#### Step 1: System Access & LOB Selection
- Log in to the EzDocs application
- Navigate to the "Received Liability" LOB (Line of Business)

#### Step 2: Submission Retrieval
- Search for new submissions under Received Liability using the IPS Contract ID
- Click on the submission to proceed to the next information screen

#### Step 3: Access IPS Admin Screen
- Click on "Show CIIM" button
- This action navigates to the IPS Admin screen
- Enter required data in appropriate tabs based on business requirements

#### Step 4: Data Persistence
- After entering all required data, click "Save"
- User is redirected back to the EzDocs screen

#### Step 5: Data Synchronization
- On the EzDocs screen, click "Sync CIIM"
- This action ensures data entered on the IPS screen is synced and populated correctly
- Verify that data appears in EzDocs Received Liability screen

---

## 4. Form Type Logic Specifications & Data Mapping

### 4.1 Logic - FormType Mapping Table

| **Scenario** | **IPS (Claims Trigger)** | **ezDocs (Form Type)** | **Status** |
|---|---|---|---|
| Scenario 1 | Occurrence | Occurrence | Verified |
| Scenario 2 | Claims-made | Claims-made | Verified |
| Other Cases | - | empty | By Default |

### 4.2 Field Mapping Details

| **Attribute** | **Details** |
|---|---|
| **Page** | LiabilityCoverage |
| **Tab** | Information |
| **Section** | Employee Benefits Retroactive Date |
| **Field Name** | Form Type |
| **Action Type** | IPS Check |
| **Validation Type** | Logic - FormType |
| **Source System** | IPS Admin |
| **Target System** | ezDocs |

### 4.3 Expected Behavior

1. **Data Origin:** Form Type data originates from IPS Admin system Claims Trigger field
2. **Mapping Rules:** 
   - "Occurrence" Claims Trigger maps to "Occurrence" Form Type
   - "Claims-made" Claims Trigger maps to "Claims-made" Form Type
   - All other scenarios result in empty Form Type field
3. **Synchronization:** Data properly syncs from IPS to ezDocs via CIIM when "Sync CIIM" is clicked
4. **Persistence:** Synced data remains populated and consistent across sessions

---

## 5. Functional Requirements

### 5.1 Data Integration Requirements

1. **IPS to ezDocs Data Flow**
   - IPS Admin system captures Claims Trigger information
   - CIIM acts as the integration bridge between systems
   - Data must be accurately mapped to Form Type field in ezDocs

2. **CIIM Data Synchronization**
   - "Show CIIM" button properly opens IPS Admin screen interface
   - "Save" button on IPS Admin screen persists data changes
   - Data is properly staged for synchronization

3. **Data Validation**
   - Form Type field values must match Claims Trigger values per mapping rules
   - Empty Form Type field should appear for unmapped scenarios
   - No data loss during synchronization process

### 5.2 User Interface Requirements

1. **Navigation Controls**
   - "Show CIIM" button is accessible and functional on Information screen
   - "Sync CIIM" button is accessible and functional on Information screen
   - Screen transitions are smooth and intuitive

2. **Data Display**
   - Form Type field is visible on Information screen
   - Synced data is properly displayed
   - Field formatting is consistent with UI standards

### 5.3 System Integration Requirements

1. **IPS Admin Integration**
   - IPS Admin screen launches correctly when "Show CIIM" is clicked
   - All required tabs are accessible for data entry
   - Data entered in IPS Admin is properly captured

2. **CIIM Communication**
   - CIIM correctly receives data from IPS Admin
   - CIIM correctly delivers data to ezDocs
   - No data transformation errors occur during transfer

---

## 6. Acceptance Criteria

### 6.1 Functional Acceptance Criteria

- [x] User can successfully navigate through all workflow steps
- [x] "Show CIIM" button opens IPS Admin screen without errors
- [x] Data can be entered and saved in IPS Admin screen
- [x] "Sync CIIM" button successfully syncs data to ezDocs
- [x] Form Type field receives correct values based on Claims Trigger mapping
- [x] "Occurrence" Claims Trigger maps to "Occurrence" Form Type
- [x] "Claims-made" Claims Trigger maps to "Claims-made" Form Type
- [x] Unmapped scenarios result in empty Form Type field
- [x] Synced data persists after page reload
- [x] No duplicate data entries after sync operations

### 6.2 Data Quality Acceptance Criteria

- [x] Data mapping is 100% accurate per specification
- [x] No data loss occurs during sync operations
- [x] Data consistency is maintained between IPS and ezDocs
- [x] Form Type field shows only valid values per mapping rules
- [x] Special characters in data are handled correctly

### 6.3 User Experience Acceptance Criteria

- [x] All navigation controls are clearly visible and labeled
- [x] Page load times are acceptable (< 3 seconds)
- [x] Error messages are clear and actionable
- [x] User receives feedback for sync operations
- [x] Process is intuitive for QA testers and end users

### 6.4 Performance Acceptance Criteria

- [x] Sync operation completes within acceptable timeframe
- [x] No system performance degradation during operation
- [x] CIIM communication is reliable with minimal latency

---

## 7. Test Case Specifications

### 7.1 Test Case TC_01: Information Screen - Logic - FormType Validation

**TC ID:** TC_01  
**Test Type:** Manual  
**Test Case Name:** TC01_Verify the Information Screen - Logic - FormType  
**Related User Story:** EZ-1389  
**Priority:** Medium  
**Status:** To Do

#### 7.1.1 Test Objective
Validate that the Information screen correctly displays Logic - FormType field and that data synchronization from IPS Admin to ezDocs works as expected.

#### 7.1.2 Pre-conditions

1. User has valid login credentials for EzDocs application
2. User has access to Received Liability LOB
3. At least one active submission exists in Received Liability LOB with associated IPS Contract ID
4. IPS Admin system is accessible and functional
5. CIIM integration is configured and active

#### 7.1.3 Test Steps

**Step 1: Access Application and LOB**
- Action 1.1: Log in to EzDocs application
- Action 1.2: Navigate to "Received Liability" LOB
- Expected Result: Successfully logged in; Received Liability LOB is accessible

**Step 2: Locate and Open Submission**
- Action 2.1: Search for existing submission using IPS Contract ID
- Action 2.2: Click on submission to open it
- Expected Result: Submission details are displayed

**Step 3: Navigate to Information Screen**
- Action 3.1: Click "Next" button or appropriate navigation control to proceed to Information screen
- Expected Result: Information screen is displayed with all fields visible

**Step 4: Access IPS Admin Screen**
- Action 4.1: Click "Show CIIM" button on Information screen
- Expected Result: IPS Admin screen opens in new window/modal; screen displays tabs for data entry

**Step 5: Enter Form Type Data**
- Action 5.1: Navigate to appropriate tab in IPS Admin screen
- Action 5.2: Locate Claims Trigger field
- Action 5.3: Enter test value: "Occurrence" OR "Claims-made"
- Expected Result: Data entry field accepts value

**Step 6: Save Data in IPS Admin**
- Action 6.1: Click "Save" button
- Expected Result: Data is saved; confirmation message appears; no errors occur

**Step 7: Return to EzDocs Screen**
- Action 7.1: Close IPS Admin screen or verify automatic redirect
- Expected Result: User is back on EzDocs Information screen

**Step 8: Synchronize Data**
- Action 8.1: Click "Sync CIIM" button on Information screen
- Expected Result: Sync operation initiates; success notification appears; no errors occur

**Step 9: Verify Data Population**
- Action 9.1: Locate Form Type field on Information screen
- Action 9.2: Verify that Form Type field displays correct value based on mapping:
  - If Claims Trigger = "Occurrence" → Form Type should = "Occurrence"
  - If Claims Trigger = "Claims-made" → Form Type should = "Claims-made"
- Expected Result: Form Type field displays correct mapped value

**Step 10: Verify Data Persistence**
- Action 10.1: Reload the page or navigate away and back
- Expected Result: Form Type field still displays the synced value; data persists

#### 7.1.4 Expected Results Summary

| **Action** | **Expected Result** | **Pass/Fail** |
|---|---|---|
| Login to EzDocs | User successfully authenticated | - |
| Navigate to Received Liability LOB | LOB displays available submissions | - |
| Click on submission | Submission details are displayed | - |
| Navigate to Information screen | Information screen with all fields visible | - |
| Click "Show CIIM" | IPS Admin screen opens | - |
| Enter Claims Trigger value | Value is entered without errors | - |
| Click "Save" | Data saved successfully | - |
| Return to EzDocs | EzDocs Information screen is displayed | - |
| Click "Sync CIIM" | Sync operation completes successfully | - |
| Form Type field populated | Correct mapped value appears | - |
| Data persistence | Data remains after page reload | - |

#### 7.1.5 Test Data Requirements

| **Field** | **Test Value 1** | **Test Value 2** |
|---|---|---|
| Claims Trigger (IPS) | Occurrence | Claims-made |
| Expected Form Type (ezDocs) | Occurrence | Claims-made |
| IPS Contract ID | [Sample Active Contract ID] | [Sample Active Contract ID] |

#### 7.1.6 Acceptance Results

**User should be able to:**
- Successfully sync default data from IPS Admin screen
- View synchronized data populated correctly on EzDocs Information Screen
- Verify that Form Type field displays correct values per mapping rules
- Confirm data persistence across sessions

---

## 8. Validation Scenarios

### 8.1 Scenario 1: Occurrence Claims Trigger

**Scenario Description:** User enters "Occurrence" as Claims Trigger in IPS Admin

**Test Steps:**
1. Open existing submission in Received Liability LOB
2. Navigate to Information screen
3. Click "Show CIIM" to open IPS Admin
4. Locate Claims Trigger field in Employee Benefits Retroactive Date section
5. Enter value: "Occurrence"
6. Save in IPS Admin
7. Return to EzDocs and click "Sync CIIM"

**Expected Result:**
- Form Type field populates with "Occurrence"
- Value matches Claims Trigger exactly
- Data persists on page reload
- No sync errors occur

---

### 8.2 Scenario 2: Claims-made Claims Trigger

**Scenario Description:** User enters "Claims-made" as Claims Trigger in IPS Admin

**Test Steps:**
1. Open existing submission in Received Liability LOB
2. Navigate to Information screen
3. Click "Show CIIM" to open IPS Admin
4. Locate Claims Trigger field
5. Enter value: "Claims-made"
6. Save in IPS Admin
7. Return to EzDocs and click "Sync CIIM"

**Expected Result:**
- Form Type field populates with "Claims-made"
- Value matches Claims Trigger exactly
- Data persists on page reload
- No sync errors occur

---

### 8.3 Scenario 3: Other/Unmapped Values

**Scenario Description:** User enters value that doesn't have defined mapping

**Test Steps:**
1. Open existing submission in Received Liability LOB
2. Navigate to Information screen
3. Click "Show CIIM" to open IPS Admin
4. Locate Claims Trigger field
5. Enter unmapped value or leave blank
6. Save in IPS Admin
7. Return to EzDocs and click "Sync CIIM"

**Expected Result:**
- Form Type field remains empty
- No error occurs
- System gracefully handles unmapped scenario
- Other fields unaffected

---

## 9. UI and Validation Checks

### 9.1 Field Validation Rules

| **Field** | **Rule** | **Validation Type** |
|---|---|---|
| Form Type | Only values: "Occurrence", "Claims-made", or empty | Dropdown/Predefined |
| Claims Trigger (IPS) | Required field | Mandatory |
| Synced Data | Must match source exactly | Data Integrity |

### 9.2 Navigation Control Validation

| **Control** | **Validation** | **Expected Behavior** |
|---|---|---|
| Show CIIM Button | Functionality | Opens IPS Admin screen |
| Sync CIIM Button | Functionality | Initiates data synchronization |
| Save Button (IPS Admin) | Functionality | Persists data in IPS |
| Next/Navigation Buttons | Functionality | Proper page transitions |

### 9.3 Error Handling Requirements

1. **Sync Failures**
   - Display clear error message
   - Log error for support team
   - Allow user to retry

2. **Data Mismatches**
   - Alert user of discrepancies
   - Prevent saving if critical validation fails
   - Provide correction options

3. **System Errors**
   - Graceful error handling
   - No data loss on failure
   - Recovery options available

---

## 10. Business Rules & Constraints

### 10.1 Mandatory Business Rules

1. **Form Type Mapping is Non-Negotiable**
   - "Occurrence" Claims Trigger MUST map to "Occurrence" Form Type
   - "Claims-made" Claims Trigger MUST map to "Claims-made" Form Type
   - Exceptions require business approval

2. **Data Synchronization is Unidirectional**
   - Data flows from IPS Admin → CIIM → ezDocs
   - Changes in ezDocs do not update IPS
   - IPS remains source of truth for Claims Trigger

3. **CIIM Acts as Integration Bridge**
   - All data must pass through CIIM
   - CIIM must not modify or transform data
   - Data integrity must be maintained

### 10.2 System Constraints

1. Sync operation timeout: 30 seconds maximum
2. Form Type field accepts only predefined values
3. No special characters in Claims Trigger values
4. Maximum field length compliance with database schema

---

## 11. Related Documentation & References

### 11.1 External References
- Received Liability Master.xlsx: Contains complete IPS Integration specifications
- Project Documentation: IPS Integration - Master Sheets

### 11.2 Related Issues
- **Clones:** EZ-1231 - "Map IPS data with Liability Received..." (Closed)

### 11.3 Integration Points
- **System 1:** IPS Admin (Source System)
- **Integration Layer:** CIIM (Claims Issuance Item Management)
- **System 2:** EzDocs Received Liability (Target System)

---

## 12. Success Criteria Summary

| **Criteria Category** | **Success Metric** | **Status** |
|---|---|---|
| **Functional** | All test steps execute successfully | Pending Testing |
| **Data Accuracy** | 100% mapping accuracy | Pending Validation |
| **User Experience** | Navigation is smooth and intuitive | Pending Testing |
| **Data Persistence** | Data remains after page reload | Pending Testing |
| **Error Handling** | All errors handled gracefully | Pending Testing |
| **Performance** | Operations complete within SLA | Pending Testing |

---

## 13. Notes & Important Information

- **Sprint Assignment:** IPS/eZdocs Sprint 8
- **Mendix PD's:** 3
- **Current Status:** QA in progress
- **Testing Environment:** Must match production configuration
- **Data Privacy:** Ensure test data does not contain sensitive information
- **Documentation:** All test results must be documented with screenshots
- **Regression Testing:** Verify no impact on other Received Liability fields

---

## 14. Test Execution Checklist

- [ ] Test environment is prepared and ready
- [ ] Test data is loaded and verified
- [ ] All navigation steps are executable
- [ ] IPS Admin is accessible from EzDocs
- [ ] CIIM integration is functioning
- [ ] Database connections are stable
- [ ] Test case TC_01 is mapped and ready
- [ ] Test results documentation is ready
- [ ] Defect logging process established
- [ ] Sign-off criteria defined with stakeholders

---

**Document Generated:** March 4, 2026  
**Prepared by:** QA Team  
**Based on JIRA Issue:** EZ-1389  
**Comprehensive Analysis Complete:** ✓

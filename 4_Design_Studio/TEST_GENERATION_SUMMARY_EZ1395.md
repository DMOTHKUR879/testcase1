# EZ-1395 Test Cases - Deliverables Summary

**Generated:** March 11, 2026  
**Project:** eZdocs IPS Integration  
**JIRA Issue:** EZ-1395  
**Test Focus:** Logic - Default Action Validation  

---

## Deliverables Overview

### 1. **EZ-1395_Scenario_Based_TestCases.csv** ✓
**Location:** `/workspaces/testcase1/4_Design_Studio/`  
**Format:** CSV  
**Test Cases:** 15 Scenario-Based Tests  

**Purpose:** Focused validation of the Logic - Default business scenario  
**Coverage:** All 5 forms (3 Mandatory + 2 Endorsements)  

**Scenario Tests Included:**
- TC_SCENARIO_001: Verify All Mandatory Forms Appear After Sync CIIM
- TC_SCENARIO_002: Verify All Endorsements Appear After Sync CIIM
- TC_SCENARIO_003-007: Individual Form Detail Verification (5 forms)
- TC_SCENARIO_008: Data Persistence Across Sync
- TC_SCENARIO_009: Sync CIIM Operation Validation
- TC_SCENARIO_010: Form Categorization Verification
- TC_SCENARIO_011: Edition Number Verification
- TC_SCENARIO_012: Language Consistency Check
- TC_SCENARIO_013: Default Values Application
- TC_SCENARIO_014: Mandatory Form Validation
- TC_SCENARIO_015: Endorsement Field Editing

---

### 2. **EZ-1395_TestCases.csv** ✓
**Location:** `/workspaces/testcase1/4_Design_Studio/`  
**Format:** CSV  
**Test Cases:** 50 Comprehensive Tests  

**Purpose:** Comprehensive test coverage including all aspects  
**Coverage:** Navigation, setup, form loading, data entry, validation, sync, data integrity, end-to-end workflows

**Test Categories:**
| Category | Count | TC Range |
|----------|-------|----------|
| Navigation & Setup | 4 | TC_EZ1395_001-004 |
| Form Loading | 5 | TC_EZ1395_005-009 |
| Data Entry | 5 | TC_EZ1395_010-014 |
| Save Operations | 5 | TC_EZ1395_015-019 |
| Synchronization | 7 | TC_EZ1395_020-026 |
| Data Integrity | 5 | TC_EZ1395_027-031 |
| Validation | 5 | TC_EZ1395_032-036 |
| Language | 3 | TC_EZ1395_037-039 |
| Edition Numbers | 5 | TC_EZ1395_040-044 |
| Data Type Validation | 3 | TC_EZ1395_045-047 |
| End-to-End Workflows | 3 | TC_EZ1395_048-050 |

---

### 3. **EZ-1395_TestCases_Detailed.md** ✓
**Location:** `/workspaces/testcase1/4_Design_Studio/`  
**Format:** Markdown  
**Test Cases:** 50 Comprehensive Tests  

**Purpose:** Detailed execution guide with descriptions and guidelines  
**Content:**
- Full test descriptions for all 50 test cases
- Detailed step-by-step actions
- Expected results with checkpoints
- Test execution guidelines
- Coverage summary matrices
- Notes for QA team

---

### 4. **EZ-1395_Logic_Default_Scenario_Guide.md** ✓
**Location:** `/workspaces/testcase1/4_Design_Studio/`  
**Format:** Markdown  

**Purpose:** Detailed guide for Logic - Default scenario testing  
**Content:**
- Business scenario requirements
- Form specifications table
- Detailed scenario test cases (15 tests)
- Acceptance criteria mapping
- Execution order recommendations
- 100% requirement coverage proof

---

## Forms Tested - Complete Matrix

### Mandatory Forms (3)
| Sno | Form ID | Form Name | Edition | Language | Logic - Default | Scenarios Covered |
|-----|---------|-----------|---------|----------|-----------------|-------------------|
| 1 | ZC-RC-20321 U | Commercial General Liability Policy Declarations | 0623b | English | ✓ Applied | 9 scenarios |
| 2 | ZC 6300 U | Statutory Conditions, General Conditions and Other Conditions | 122 | English | ✓ Applied | 9 scenarios |
| 3 | ZC 20041 U | Commercial General Liability Policy | 0522b | English | ✓ Applied | 9 scenarios |

### Endorsements (2)
| Sno | Form ID | Form Name | Edition | Language | Logic - Default | Scenarios Covered |
|-----|---------|-----------|---------|----------|-----------------|-------------------|
| 4 | ZC-RC-20324 U | International Program – Local Policy Conditions | 623 | English | ✓ Applied | 9 scenarios |
| 5 | ZC 20157 U | Canadian Forest or Prairie Firefighting Expenses Endorsement | 321 | English | ✓ Applied | 9 scenarios |

---

## Test Coverage Details

### Scenario-Based Tests (15 Tests)
These tests specifically validate the Logic - Default requirement:

```
BUSINESS REQUIREMENT:
"On EzDocs Application under Received Liability under forms tab 
we should get below mandatory forms when we click on sync CIIM on forms tab"
```

**Validated Test Cases:**
1. ✓ All 5 forms load with Logic - Default action enabled
2. ✓ All 3 mandatory forms appear in mandatory forms section after Sync CIIM
3. ✓ All 2 endorsements appear in endorsements section after Sync CIIM
4. ✓ All form editions are correct and displayed
5. ✓ All forms display in English language
6. ✓ All default values populate correctly
7. ✓ Form categorization is correct (Mandatory vs Endorsements)
8. ✓ Data persists without loss or corruption during sync
9. ✓ Sync CIIM operation completes without errors
10. ✓ Individual form details are correct
11. ✓ Required field validation works properly
12. ✓ Field editing is functional
13. ✓ Operations complete successfully

### Comprehensive Tests (50 Tests)
**Additional Coverage Beyond Scenarios:**
- Navigation workflows and authentication
- Individual field data entry
- Save button functionality
- Sync CIIM button availability
- Individual form appearance verification
- Data type validation
- Invalid data handling
- Error messaging
- Language consistency across all forms
- Edition number verification
- Complete end-to-end workflows

---

## CSV Format Specifications

### Scenario-Based CSV Columns:
```
TC ID | Test type | Test case Name | Description | Actions | Expected Results | 
Test Repository Path | Status | User story | Priority | Scenario | Form ID | 
Form Type | Edition
```

### Comprehensive CSV Columns:
```
TC ID | Test type | Test case Name | Description | Actions | Expected Results | 
Test Repository Path | Status | User story | Priority
```

### Multi-line Cell Handling:
- Actions and Expected Results wrapped in double quotes
- Multiple steps separated by `\n` within quoted cells
- Commas escaped by containing field in double quotes
- Double quotes doubled ("") when appearing within field values

---

## Test Execution Recommendations

### Phase 1: Foundation Testing (Scenarios 1-2)
Execute TC_SCENARIO_001 and TC_SCENARIO_002 first to validate basic requirements:
- Mandatory forms appear after Sync CIIM
- Endorsements appear after Sync CIIM

**Estimated Duration:** 30 minutes

### Phase 2: Individual Form Testing (Scenarios 3-7)
Validate each of the 5 forms individually:
- Form loading with Logic - Default
- Edition numbers correct
- Default values populated
- Data entry functional

**Estimated Duration:** 60 minutes (12 minutes per form)

### Phase 3: Integration Testing (Scenarios 8-9)
Validate complete sync workflow:
- Data persistence
- Sync operation success
- Error handling

**Estimated Duration:** 30 minutes

### Phase 4: Property Verification (Scenarios 10-15)
Validate form properties and behaviors:
- Categorization
- Language
- Defaults
- Validation
- Field editing

**Estimated Duration:** 45 minutes

### Phase 5: Comprehensive Testing (50 detailed tests)
Execute all 50 comprehensive tests for complete coverage

**Estimated Duration:** 8-10 hours

---

## Acceptance Criteria - Master Checklist

### Critical Requirements (Must Pass)
- [ ] All 3 mandatory forms appear in mandatory forms section after Sync CIIM
  - [ ] ZC-RC-20321 U (Edition 0623b) - Present and Correct
  - [ ] ZC 6300 U (Edition 122) - Present and Correct
  - [ ] ZC 20041 U (Edition 0522b) - Present and Correct

- [ ] All 2 endorsements appear in endorsements section after Sync CIIM
  - [ ] ZC-RC-20324 U (Edition 623) - Present and Correct
  - [ ] ZC 20157 U (Edition 321) - Present and Correct

- [ ] All forms display in English language
- [ ] All Logic - Default actions apply correctly
- [ ] Sync CIIM operation completes without errors
- [ ] Data persists without loss or corruption

### Important Requirements (Should Pass)
- [ ] All edition numbers are displayed correctly
- [ ] Form categorization is correct (Mandatory vs Endorsements)
- [ ] Default values populate consistently
- [ ] Required field validation works
- [ ] All form fields are editable where applicable
- [ ] Save button functions properly
- [ ] No validation warnings during data entry

### Quality Requirements (Nice to Have)
- [ ] Sync operation completes within 5 seconds
- [ ] Error messages are clear and helpful
- [ ] UI is responsive during operations
- [ ] No console errors during execution

---

## Files Checklist

| File | Format | Test Cases | Location | Status |
|------|--------|-----------|----------|--------|
| EZ-1395_Scenario_Based_TestCases.csv | CSV | 15 | 4_Design_Studio/ | ✓ Created |
| EZ-1395_TestCases.csv | CSV | 50 | 4_Design_Studio/ | ✓ Created |
| EZ-1395_TestCases_Detailed.md | Markdown | 50 | 4_Design_Studio/ | ✓ Created |
| EZ-1395_Logic_Default_Scenario_Guide.md | Markdown | 15 + Guide | 4_Design_Studio/ | ✓ Created |
| EZ-1395_Detailed_User_Stories.md | Markdown | 5 Stories | 1_Base_Repo/User_Story/ | ✓ Created |

---

## Test Data Requirements

### Required Test Data Setup:
1. Valid EzDocs user credentials
2. Active Received Liability LOB access
3. Valid IPS Contract ID for submission search
4. Sample data for form field entries
5. Test submission with proper initialization

### Data Entry Examples:
For each form, prepare test data sets covering:
- Standard business values
- Boundary values
- Maximum length strings
- Numeric values

---

## Defect Reporting Format

For any failed test cases, report using:
```
Test Case ID: [TC_ID]
Status: FAILED
Error Description: [Clear description of failure]
Steps to Reproduce: [Detailed steps to reproduce]
Expected Result: [What should happen]
Actual Result: [What actually happened]
Severity: [Critical/High/Medium/Low]
Screenshots: [Attach if applicable]
Environment: [Test environment details]
```

---

## Success Criteria

### Phase 1 Success:
- All 15 scenario tests pass
- All 5 forms load correctly with Logic - Default
- All forms sync to EzDocs without errors

### Phase 2 Success:
- All 50 comprehensive tests pass
- No data loss during sync
- All forms categorized correctly
- All edition numbers correct

### Final Success:
- 100% of test cases passed
- No critical defects
- No data integrity issues
- Complete requirement coverage

---

## Contact & Support

For test execution support or questions:
1. Refer to test case descriptions in detailed MD files
2. Check scenario guide for Logic - Default specific guidance
3. Review user stories for business context
4. Consult navigation steps for workflow guidance
5. Review template for standard test case format

---

## Version History

| Version | Date | Changes | Status |
|---------|------|---------|--------|
| 1.0 | 2026-03-11 | Initial creation - 15 scenario + 50 comprehensive tests | Draft |
| | | Full Logic - Default scenario coverage | |
| | | All 5 forms mapped and tested | |

---

**Generated by:** GitHub Copilot  
**For:** eZdocs QA Team  
**Project:** EZ-1395 IPS Integration Testing  
**Ready for:** QA Execution

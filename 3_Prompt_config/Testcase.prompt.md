
---
 
agent : agent
 
tools:
-search/codebase
 
- edit/editFiles
 
- search
 
description: Generate manual test cases in CSV format based on user story and acceptance criteria
 
---
 
 
 
# Manual Test Case Generation Prompt
 
 
 
## Execution Workflow
 
 
 
When this prompt is executed, follow these steps:
 
 
 
### Step 1: Prompt for User Story Path
 
Ask the user:
 
```
 
Please provide the User Story file path : 

Path for csv file should be same as user story file path with changes in folder and file name like below: C:\Users\SWETHA.DESHPANDE\Manual TestCases\Swetha-EZdocs\Optimus Core\1_Base_Repo\User_Story\Logic_1370.csv
 
```
 
 
 
### Step 2: Generate Test Cases and Save CSV File
 
- For each acceptance criterion/scenario in the user story, generate one test case
 
- Create a CSV file with proper structure and multi-line cell formatting (wrap in double quotes)
 
- Number actions sequentially (1., 2., 3., etc.) with line breaks between steps
 
- Write expected results as continuous text WITHOUT numbering
 
- Automatically save the CSV file to: `C:\Users\SWETHA.DESHPANDE\Manual TestCases\Swetha-EZdocs\Optimus Core\4_Design_Studio\{filename}_TestCases.csv`
 
- Confirm completion with message:
 
```
 
Test cases generated successfully!
 
Output file: C:\Users\SWETHA.DESHPANDE\Manual TestCases\Swetha-EZdocs\Optimus Core\4_Design_Studio\{filename}_TestCases.csv
Total test cases: {count}
 
```
 
 
 
---
 
 
 
## Input Requirements
 
 
 
**User Story File Path:** Provided by user at runtime
 
**Template Reference:** `C:\Users\SWETHA.DESHPANDE\Manual TestCases\Swetha-EZdocs\Optimus Core\1_Base_Repo\Template\Template_ips_1370.md`
 
**Navigation Reference:** `C:\Users\SWETHA.DESHPANDE\Manual TestCases\Swetha-EZdocs\Optimus Core\1_Base_Repo\Reference\navigation_steps_ips_1370.md`
 
**Logic Reference:** `C:\Users\SWETHA.DESHPANDE\Manual TestCases\Swetha-EZdocs\Optimus Core\1_Base_Repo\User_Story\Logic_1370.csv` (Contains detailed scenarios for Extension Cover Mapping, Time Limit, and Qualifying Period)
## Goal
 
 
Generate manual test cases in CSV format based on the user story and acceptance criteria. Each test case should follow the template structure and incorporate the ZED application navigation flow from navigation_steps_ips_1370.md. Include all scenarios defined in the Logic_1370.csv file to ensure comprehensive coverage of business logic variations.
 
---
 
## Scenario-Based Test Case Generation
 
**The Logic_1370.csv file defines the following scenarios that MUST be included in generated test cases:**
 
### 1. Logic - Extension Cover Mapping Scenarios:
- **Scenario 1:** NCP constraint selected - Limit of Liability should NOT be visible and empty
- **Scenario 2:** Not NCP constraint with Extension Limit Value - Limit of Liability should show Extension Limit Value
- **Scenario 3:** Not NCP constraint with empty limit and cover NOT Available - Limit of Liability should be visible and empty
- **Scenario 4:** Not NCP constraint with empty limit and cover Available with CoverProvided instruction - Limit of Liability should show General Limit Value
- **Scenario 5:** Not NCP constraint with empty limit and cover Available with CoverNotProvided instruction - Limit of Liability should be visible and empty
 
### 2. Logic - Time Limit Scenarios (for Civil or Military Authority coverage):
- **Scenario 1:** Time Limit basis KM - Number of days, Selection dropdown (KM), and Number of KM/Miles should be populated with Extension values
- **Scenario 2:** Time Limit basis Miles - Number of days, Selection dropdown (Miles), and Number of KM/Miles should be populated with Extension values
- **Scenario 3:** Time Limit basis Any Others - Number of days populated, Selection dropdown (No Selection), and Number of KM/Miles populated
 
### 3. Logic - Qualifying Period Scenarios (for Civil or Military Authority coverage):
- **Scenario 1:** Qualifying Period basis Hours - Fields populated with Hours selection, Qualifying Period NCP unselected
- **Scenario 2:** Qualifying Period basis Days - Fields populated with Days selection, Qualifying Period NCP unselected
- **Scenario 3:** Qualifying Period basis Any Others - Fields populated with No Selection, Qualifying Period NCP unselected
- **Scenario 4:** Empty Qualifying Period with NCP selected - Fields should NOT be visible and ignored
 
 
## Important Notes
 
1. Generate exactly one test case per acceptance criterion in the user story
 
2. **CRITICAL: Generate at least one dedicated test case for EACH scenario defined in Logic_1370.csv** (minimum 12 scenarios total: 5 Extension Cover Mapping + 3 Time Limit + 4 Qualifying Period)
 
3. For Extension Cover Mapping scenarios: Generate test cases for Accounts Receivable, Better Green Upgrade, Brands and Labels, and Civil or Military Order coverages covering all 5 scenarios
 
4. For Time Limit scenarios: Generate test cases for Civil or Military Authority coverage with all 3 time limit basis variations (KM, Miles, Any Others)
 
5. For Qualifying Period scenarios: Generate test cases for Civil or Military Authority coverage with all 4 qualifying period variations (Hours, Days, Any Others, Empty with NCP selected)
 
6. Include only relevant navigation steps based on the specific scenario scope  
 
7. Keep test cases atomic and focused on specific scenario validation
 
8. Ensure proper CSV escaping for special characters and multi-line cells (use double quotes)
 
9. Number actions sequentially (1., 2., 3., etc.) with line breaks between steps
 
10. Write expected results as continuous text WITHOUT numbering, separated by line breaks
 
11. Reference navigation_steps_ips_1370.md for accurate ZED workflow patterns
 
12. Use Template_ips_1370.md structure for field mapping and test case structure (reference only, not copy values)
 
13. Use forward slashes (/) consistently in all file paths
 
14. Extract filename from user story path correctly for output file naming (e.g., EZ-1370.doc → EZ-1370)
 
15. Just refer the Template_ips_1370.md file. Don't use the content or values present in the Template_ips_1370.md file.
 
16. Include positive and negative scenarios as defined in the Logic_1370.csv file based on business logic variations
 
 
 
## Output Format: CSV Structure
 
 
 
**CSV Headers:**
 
```
 
TC ID,Test type,Test case Name,Description,Actions,Expected Results,Test Repository Path,Status,User story,Priority
 
```
 
 
 
**CSV Format Rules:**
 
1. Each test case is a single row in the CSV
 
2. Wrap multi-line cells (Actions and Expected Results) in double quotes
 
3. Escape commas within fields using double quotes
 
4. Escape double quotes within fields by doubling them ("")
 
5. Number actions sequentially (1., 2., 3., etc.)
 
6. Expected results should NOT have numbering - keep as plain text
 
7. Use actual line breaks within quoted cells or \n for separating action steps
 
 
 
**Example CSV Output:**
 
```csv
 
TC ID,Test type,Test case Name,Description,Actions,Expected Results,Test Repository Path,Status,User story,Priority
 
 
```
 
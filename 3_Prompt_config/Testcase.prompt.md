
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
 
Please provide the User Story file path : C:\Users\DIVYA.MOTHKURI\Manual TestCases\Divya-EZdocs\Optimus Core\1_Base_Repo/User_Story/EZ-1367.doc

Path for csv file should be same as user story file path with changes in folder and file name like below: C:\Users\Divya.Mothkuri\Manual TestCases\Divya-EZdocs\Optimus Core\1_Base_Repo/User_Story/EZ-1367 Logic .csv
 
```
 
 
 
### Step 2: Generate Test Cases and Save CSV File
 
- For each acceptance criterion/scenario in the user story, generate one test case
 
- Create a CSV file with proper structure and multi-line cell formatting (wrap in double quotes)
 
- Number actions sequentially (1., 2., 3., etc.) with line breaks between steps
 
- Write expected results as continuous text WITHOUT numbering
 
- Automatically save the CSV file to: `C:\Users\DIVYA.MOTHKURI\Manual TestCases\Divya-EZdocs\Optimus Core\4_Design_Studio\{filename}_TestCases.csv`
 
- Confirm completion with message:
 
```
 
Test cases generated successfully!
 
Output file: C:\Users\DIVYA.MOTHKURI\Manual TestCases\Divya-EZdocs\Optimus Core\4_Design_Studio\{filename}_TestCases.csv
Total test cases: {count}
 
```
 
 
 
---
 
 
 
## Input Requirements
 
 
 
**User Story File Path:** Provided by user at runtime
 
**Template Reference:** `C:\Users\DIVYA.MOTHKURI\Manual TestCases\Divya-EZdocs\Optimus Core\1_Base_Repo\Template\Template_ips_1367.md`
 
**Navigation Reference:** `C:\Users\DIVYA.MOTHKURI\Manual TestCases\Divya-EZdocs\Optimus Core\1_Base_Repo\Reference\navigation_steps_ips_1367.md`
 
**Logic Reference:** `C:\Users\DIVYA.MOTHKURI\Manual TestCases\Divya-EZdocs\Optimus Core\1_Base_Repo\User_Story\Logic_1367.csv` (Contains detailed scenarios for Gross Earnings, Gross Earnings Limit (months),	
Gross Profit and Gross Profit Limit (months)
## Goal
 
 
Generate manual test cases in CSV format based on the user story and acceptance criteria. Each test case should follow the template structure and incorporate the ZED application navigation flow from navigation_steps_ips_1367.md. Include all scenarios defined in the Logic_1367.csv file to ensure comprehensive coverage of business logic variations.
 
---
 
## Scenario-Based Test Case Generation
 
**The Logic_1367.csv file defines the following scenarios that MUST be included in generated test cases:**
 
### 1. Logic - Gross Earnings :
- **Scenario 1:** On IPS Admin should select the General Tab and should give the value for Indemnity Period (in month). Then on EZdocs PD&TE screen under TE Tab, Gross Earnings should be unselected and Gross Earnings Limit (months) should populate the value of Indemnity Period (in month).

 
### 2. Logic - Gross Profit:
- **Scenario 1:** On IPS Admin should select the General Tab and should give the value for Indemnity Period (in month). Then on EZdocs PD&TE screen under TE Tab, Gross Profit should be unselected and Gross Profit Limit (months) should populate the value of Indemnity Period (in month).

 

 
 
## Important Notes
 
1. Generate exactly one test case per acceptance criterion in the user story
 
2. **CRITICAL: Generate at least one dedicated test case for EACH scenario defined in Logic_1367.csv** (minimum 1 scenarios total: Gross Earnings+ Gross Profit )
 
3. For Gross Earning: Generate test cases for Gross Earning 1 scenario

4. For Gross Profit: Generate test cases for Gross Profit 1 Scenario
 
5. Include only relevant navigation steps based on the specific scenario scope  
 
6. Keep test cases atomic and focused on specific scenario validation
 
7. Ensure proper CSV escaping for special characters and multi-line cells (use double quotes)

8. Number actions sequentially (1., 2., 3., etc.) with line breaks between steps
 
9. Write expected results as continuous text WITHOUT numbering, separated by line breaks
 
10. Reference navigation_steps_ips_1367.md for accurate ZED workflow patterns
 
11. Use Template_ips_1367.md structure for field mapping and test case structure (reference only, not copy values)
 
12. Use forward slashes (/) consistently in all file paths
 
13. Extract filename from user story path correctly for output file naming (e.g., EZ-1367.doc → EZ-1367)
 
14. Just refer the Template_ips_1367.md file. Don't use the content or values present in the Template_ips_1367.md file.
 
15. Include positive and negative scenarios as defined in the Logic_1367.csv file based on business logic variations
 
 
 
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
 
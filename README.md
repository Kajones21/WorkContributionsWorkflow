# Monitoring Staff Work Hours and Contributions
* Note: This project is still in active development. The most recent update added an overtime-logging function.
* Note: Due to the limitations of using SharePoint as a data source, the long-term plan is to migrate to Microsoft DaaVerse  when funding comes available.

## Project Background

Before the project's implementation, the organization relied on a manual, spreadsheet-driven process for tracking staff work hours and completed tasks, Employees recorded their time and contributions in personal spreadsheets or physical notebooks and  transferred the information into a supervisor-managed workbook. Supervisors would use formulas such as SUMIF to aggregate by employee and date, and managers manually created charts inside of excel for leadership reporting.

This workflow was slow, error-prone, and frequently disrupted by file-locking issues that prevented timely and smooth data submission. To streamline the process, I designed a power apps interfaced backed by SharePoint to collect the data, reducing repetivie entry, and enforeced a consistence data structure. I then created a Power BI dashboard to let staff view their submissions and provide leadership with a clean, standardized reporting template. 

## Initial Planning Stages

Planning stages included working with the administrative team to define the project's goal, identify data to collect, and ensure the solution would have a fast learning curve for staff based off their current workflow. A key focus was minimizing slow adoption by ensuring a pleasant and smooth user experience.

## Design Considerations

**Power App:**
* Pre-populate fields whenever possible to reduce manual data entry
* Allow staff to submit multiple job entries in one submission by concatenating unchanging information to those items.
* Include a filtering logic to retrieve records beyond SharePoint's delegation limit
* Include a visual indicator of the date range being displayed

**Power BI:**
* Implement Row-Level Security:
  *   Admin role: should be able to see ALL data submissions
  *   Specific users: should only be able to see their information
* Filter by employee, overtime, job/subjob, and time categories
* Include a trend chart to highlight seasonal workload patterns

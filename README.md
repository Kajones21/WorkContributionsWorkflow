# Monitoring Staff Work Hours and Contributions
* Note: This project is still in active development. The most recent update added an overtime-logging function.
* Note: Due to the limitations of using SharePoint as a data source, the long-term plan is to migrate to Microsoft DaaVerse  when funding comes available.

## Technology used
* SharePoint List
* Power Automate
* Power Apps

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

## Power Apps

### The Work Contributions Landing Screen
![Power App Landing Screen](https://github.com/Kajones21/WorkContributionsWorkflow/blob/main/HomeAppSearcherApp.png)

On opening the app, the data source is filtered to the current staff member's submissions and the time period is two months within range of the current date. Staff's Microsoft Profile information is collected as a prepopulated field. Staff are able to search and edit previous submissions. Staff members only see their submissions while administrative staff can see full list of submission. The new button will take them to the editing screen displayed in the following screenshot.

### The Work Contribution Editing Screen (Unfilled)
![Power App Edit Screen](https://github.com/Kajones21/WorkContributionsWorkflow/blob/main/InputScreenLandingSearcherApp.png)

Employee, Date Completed, and Work Week are pre-populated. Daily Work Hours needs to be filled in to begin adding completed jobs to the form. 

### The Work Contribution Editing Screen (Filled)
![Power App Edit Screen with Filled Form](https://github.com/Kajones21/WorkContributionsWorkflow/blob/main/InputScreenSubitSearcher.png)

Once the hours completed is entered in the Daily Hours Worked, then the new and delete button becomes available. The Job is a searchable dropdown list, eliminating manual entry and standardizing the field. The Amount Completed is a number input preventing non-numeric values from being inputted. The four fields above the top will be spliced onto each job and its respective amount completed and notes. Transformations to prevent the dudplicate addings of hours for the same day by employee are accounted for in Power BI.

## Power BI Dashboard
**Note:** The data inside the dashboard has been replaced with test data for viewing purposes.

### Schema
![Data Model Work Contributions](https://github.com/Kajones21/WorkContributionsWorkflow/blob/main/PBI_DataStructure_Contributions.png)

### Power BI Landing Screen
![Power BI Landing Screen](https://github.com/Kajones21/WorkContributionsWorkflow/blob/main/SearcherPBI_Landing.png)

### Power BI Overview Screen
![Power BI Overview Screen](https://github.com/Kajones21/WorkContributionsWorkflow/blob/main/SearcherPBI_Basics.png)

### Power BI Trends in Time
![Power BI Trends Screen](https://github.com/Kajones21/WorkContributionsWorkflow/blob/main/SearcherPBI_Trends.png)

### Power BI Tables
![Power BI Tables Screen](https://github.com/Kajones21/WorkContributionsWorkflow/blob/main/SearcherPBI_Tables.png)

### Conclusion

*The project is still in the implementation phase so conclusions and evaluations have not been conducted yet.*

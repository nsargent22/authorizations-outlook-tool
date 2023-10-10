# authorizations-outlook-tool
Parse a custom report from Athena and assign each procedure to the appropriate authorizations employee.

## Problem
Providers utilizing the athenahealth EHR have few options for managing prior authorizations. The first is to outsource the entire process to Athena itself, providing a streamlined workflow and one-stop-shop for managing authorizations and precertifications. Leaving the task up to Athena is straightforward: pay a monthly fee and leave the rest to an outsourced team. The debate on outsourced vs. in-house teams is beyond the scope of a GitHub repo, but I will say this: if my experiences trying to get information from Athena regarding billing processes or payment posting are anything like the experience one would have conversing with their authorizations team, then I know it would be difficult to speak with a representative who provides meaningful insight and isn't reading from a poorly cut, copy, and pasted script.

The provider's other option is to staff an in-house authorizations team and develop their own workflow. However, the technical problem of managing these authorizations then presents itself. The athenahealth EHR does not provide a straightforward way to organize authorizations or set reminders to follow up with the more involved cases. Each authorizations employee has a worklist which displays their current orders but the EHR does not allow the list to be sorted in any way. The employee can download an inbox report every day, but this system is inefficient; after just one month they would have dozens of spreadsheets to manage, leading to a different version of the same organization problem. The spreadsheet fiasco only gets worse when an employee is out of the office and another employee needs to review one of their urgent cases but is unable to locate the _right_ spreadsheet on their colleague's workstation.

## Solution
The prior authorizations team needs an efficient way to extract all assigned patient cases from the EHR and view them in an organized fashion which doesn't require managing countless spreadsheets. In fact, if we did away with spreadsheets entirely then we wouldn't have to spend time coaching our less technically-inclined colleagues on how to sort and filter columns. It would also be nice if any member of the team could update and view everyone's list in case an employee was out sick or on vacation. The solution, our team determined, was to utilize SharePoint lists. With SharePoint lists (SPL from here on), the authorizations team is presented with a simple GUI for managing all of their cases. The SPL can be customized to show only those relevant fields which would be important to the authorizations team while retaining the ability to keep track of more technical metrics in the background. The workflow is as follows:

  - Download the pre-built report from athenahealth
  - Use a Python script to clean the report, identify employee/provider assignments, and upload the data to the SPL

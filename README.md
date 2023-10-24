# authorizations-outlook-tool
Parse a custom report from Athena and assign each procedure to the appropriate authorizations employee.

## Problem
Providers utilizing the athenahealth EHR have few options for managing prior authorizations. One option is to an external tool such as SharePoint to manage prior authorizations. The downside to utilizing third-party reporting is that a procedure may fall through the cracks and go unworked until just days before the patient's appointment. In the worst case, this leads to a facility turning a frustrated and helpless patient away at surgery time.

It would be helpful to send the in-house authorizations team a list of all scheduled procedures the week before the procedure so the authorization status can be verified.

## Workflow

One solution for providers using athenahealth who want an efficient way of managing prior authorizations is to implement the following workflow: download a pre-built report from the EHR, process the report using a Python script, and send the filtered report to the authorizations team via email. Ideally this report would be sent to the appropriate employees Monday the week before surgery. For example, a report generated on Monday January 1st would show all procedures scheduled from Monday January 8th through Friday January 12th. This allows for enough time, in many cases, to get missed procedures authorized before the patient is to be seen.

![Raw GitHub Image](https://github.com/nsargent22/authorizations-outlook-tool/blob/main/Drawing2%20(1).png)

## Technologies Used

Athenahealth EHR
Python 3.10
Microsoft 365 SharePoint


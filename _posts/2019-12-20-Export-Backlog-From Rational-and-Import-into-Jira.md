## Roles Required
* Jira Administrator

## Tools Required
* Rational
* Jira

## Steps
To export the project backlog from Rational CM you will need to run a query. 
1. From the Work Items menu review the Shared Queries to see if an existing query exists. 

![Jira Active Sprints](/DevOps-Coms-Public/assets/images/jira/jira_backlog_export_1.png)

2. If an existing query does not exist, you can make a copy of the Open Stories query and select all the types you want to export. 
Note: You can export one type at a time or all, it depends on how you want to proceed.
 
![Jira Active Sprints](/DevOps-Coms-Public/assets/images/jira/jira_backlog_export_2.png)

3. Select the Column Display link to review what fields you want to export. By default, only a few columns are selected. 

![Jira Active Sprints](/DevOps-Coms-Public/assets/images/jira/jira_backlog_export_3.png)

4. Click on the Add Column link to add any additional fields you would like to export. 

5. Once you have selected all the fields, run the query to make sure you have what you are wanting. Save and Run the query. 

![Jira Active Sprints](/DevOps-Coms-Public/assets/images/jira/jira_backlog_export_4.png)

6. Click on the icon on the left to export the results to a spreadsheet CSV file.

7. Review the spreadsheet to ensure the data looks complete. 

8. To import the CSV file into Jira log into Jira at https://vajira.max.gov

9. From the home page. select Issues from the top, and select Import Issues from CSV.

![Jira Active Sprints](/DevOps-Coms-Public/assets/images/jira/jira_backlog_export_5.png)

10. Select the CSV file for import. Use the CSV file exported from Rational. 

![Jira Active Sprints](/DevOps-Coms-Public/assets/images/jira/jira_backlog_export_6.png)

11. Select the project to import into. Only the groups you have access too will be displayed.  The three other fields are populated by default.

![Jira Active Sprints](/DevOps-Coms-Public/assets/images/jira/jira_backlog_export_7.png)

Note: The fields from the CSV file will be mapped to fields in Jira. Errors can occur here, so the corresponding fields need to be identical. The “summary” field is the only required field that must be present within CSV file moving to Jira.
Custom fields can be added to Jira to accommodate a user’s csv import if their fields differ from Jira. The checkbox “Map field value” must be checked for all fields wanting to come into Jira and “don’t map this field” for any others.


12. The following Rational field to Jira field mappings can be used as a guide:

| Rational Field | Jira Field | 
| -------------- | ---------- |
| Type | Issue Type |
| Priority | Priority |
| Story Points | Estimate |
| Summary | Summary |
| Owned By | Assignee |
| Planned For | Fix Version/s |
| Description | Description |

![Jira Active Sprints](/DevOps-Coms-Public/assets/images/jira/jira_backlog_export_8.png)

13. Select Begin Import or Validate. Validate will search the CSV file for errors and prevent issues from being imported.

14. Once completed, verify the issues were loaded correctly into the Backlog. 

See Also
* [Backlog](/_posts/2019-12-19-Jira-Backlog.md)
* [Create an Issue](/_posts/2019-12-20-Jira-Create-an-Issue.md)

If you cannot find your project, contact your Jira project administrator. If you need additional help, contact the DevOpsTeam@va.gov


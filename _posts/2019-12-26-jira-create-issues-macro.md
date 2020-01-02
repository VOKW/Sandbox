## Roles Required
* Jira User

## Tools Required
* Jira
* Confluence

If your Confluence site is connected to a Jira application, you can create and display Jira issues on Confluence pages. You can connect Confluence to any Jira application, including Jira Software and Jira Service Desk. 
Using the Jira Issues macro, you can:

* Display a list of issues on your page, based on a JIRA Query Language (JQL) search, filter or URL.
* Display a single issue.
* Display a count of issues.
* Create new issues and display the issues on your page without leaving Confluence.

## Steps
1. From the editor toolbar within Confluence, choose Insert  > Other Macros.
2. Find and select the required macro.
3. Speed it up with autocomplete: Type { and the beginning of the macro name, to see a list of suggested macros. In this example we're inserting the cheese macro.

![Autocomplete](/DevOps-Coms-Public/assets/images/jira/jira_issues_macro_step3img.png)

4. To edit an existing macro: Click the macro placeholder and choose Edit. This will open the macro details, so you can edit the macro parameters.

## Displaying issues via a Jira Query Language (JQL) search
You can use the macro to display a table of issues on your page, based on the results of a search using JIRA Query Language (JQL). JQL is a simple query language that is similar to SQL. A basic JQL query consists of a field, followed by an operator (such as = or >), followed by one or more values or functions.

Examples:

The following query will find all issues in the 'TEST' project:

project = "TEST"
The following query will find all issues in the 'documentation' component of the  'CONF' project:

project = CONF and component = documentation
For more information about JQL syntax, see Advanced searching in the Jira Software documentation.

## Steps
1. To display a table of issues based on a JQL search, insert the Jira Issues macro onto your Confluence page, as described above. 
2. Choose a Jira server next to the Search button.
3. If prompted, log in to the Jira server.
4. Enter the JQL query into the Search box.
5. Choose Search.
6. If you want to customize the display, choose Display options and adjust the columns and number of issues that will appear in your table of issues.
7. Choose Insert.

![Display Options](/DevOps-Coms-Public/assets/images/jira/jira_issues_macro_step7img.png)

## Displaying issues via a Jira URL
You can paste any of the following Jira application URLs into the Jira Issues macro. Confluence will immediately convert the URL to a JQL search.

* Any URL for an issue search or filter.
* A URL for a single issue.
* The URL of the XML view of a search.
* Auto-convert: You can paste URLs directly into the Confluence editor (without calling up the macro browser). Confluence will automatically convert the URL into a Jira Issues macro.

## Displaying a single issue, or selected issues
To display a single Jira issue, choose one of the following methods:

* Paste the URL of the issue directly onto the Confluence page. (There is no need to use the macro browser.) Confluence will auto-convert the link to a Jira Issues macro.
* Or: Add the Jira issues macro to the page as described above, and choose Recently Viewed to see the issues you have visited recently. Select an issue and choose Insert.
* Or: Add the Jira issues macro to the page as described above, and paste the issue URL into the search box in the macro browser.
* Or: Add the Jira issues macro to the page, define your search criteria in the macro browser via JQL as described above, then select the check box next to the issue in the search results, within the macro browser.
* You can choose to show just the issue key, or the issue key and a summary. Select the macro placeholder and choose Show Summary or Hide Summary. 

To display a subset of Jira issues from your search results:

* Add the Jira issues macro to the page.
* Define your search criteria in the macro browser via JQL, as described above.
* Select the check boxes next to the required issues in the search results, within the macro browser.

![Insert Jira Issue](/DevOps-Coms-Public/assets/images/jira/jira_issues_macro_subsetimg.png)

## Displaying a count of issues
You can choose to display the number of issues returned by your search, rather than a table of issues. The Jira Issues macro will display a count of issues, linked to the search in your Jira application.

## Steps
1. To display an issue count, add the Jira Issues macro to the page.
2. Define your search criteria in the macro browser via JQL, as described above.
3. Choose Display options, then choose Total issue count next to 'Display options' in the macro browser.
4. Choose Insert.

## Creating a new issue 
While editing a Confluence page, you can create an issue in Jira and display it on your Confluence page, without leaving the Confluence editor.

## Steps 
1. To create an issue and add it to your page, add the Jira Issues macro to the page, as described above.
2. Choose Create New Issue.
3. Supply the information about your Jira server, project, and issue, as prompted.
4. Choose Insert.
5. Confluence will send a request to your Jira application, to create the issue, then display the newly created issue on your page.

Limitations

The Jira Issues macro will notify you if it is unable to create an issue in the selected project. This may be because the project has a required field, field configuration or other customization that is not supported by the Jira Issues macro. In this situation you will need to create the issue directly in your Jira application.

## Learn More
* [Jira Report Blueprint](https://confluence.atlassian.com/doc/jira-report-blueprint-427623492.html)

## See Also
* [Create an Issue](/_posts/2019-12-20-jira-create-issue.md)
* [Configure a Board](/_posts/2019-12-20-jira-boards.md)
* [Complete a Sprint](/_posts/2019-12-20-jira-complete-sprint.md)

If you cannot find your project, contact your Jira project administrator. If you need additional help, contact the DevOpsTeam@va.gov

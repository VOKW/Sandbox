---
layout: archive
---
## Roles Required
* Jira Administrator

## Tools Required
* Jira

## What are permissions?
Permissions are settings within Jira applications that control what users within those applications can see and do. All Jira applications allow a variety of permissions: from whether users can create new projects to whether a user can see a specific type of comment on an issue. These permissions can differ between applications.

## Types of permissions
There are three types of permissions in Jira applications, and they range from the high-level to granular: 
* Global permissions - These apply to applications as a whole, not individual projects (for example, whether users can see the other users in the application)

* Project permissions - Organized into permission schemes, these apply to projects (e.g. who can see the project's issues, create, edit and assign them). While project admins can assign users to a project, they can't customize the permission schemes for a project. There are lots of project-level permissions you can set to control what users can do within a proje

* Issue security permissions - Organized into security schemes, these allow the visibility of individual issues to be adjusted (within the bounds of the project's permissions). For example, issue security permissions can let you set up types of issues that can only be seen by project admins or users in specific groups.

Permissions can be assigned to groups or to project roles/and or issue roles. This diagram illustrates how permissions are assigned to users:

![Permissions Flowchart](/DevOps-Coms-Public/assets/images/jira/jira_permissions_img1.jpg)

## Who can set permissions?
Board permissions can be divided into two parts — board administration permissions and board usage permissions.
* Board administration permissions cover functionality for changing the configuration of a board. For example, changing columns, customizing cards, etc. Board administration can be assigned to groups or users. 
* Board usage permissions cover functionality for the usage of a board. For example, creating sprints, ranking issues, etc. Board usage permissions are derived from project permissions. This is described in more detail below.

## Jira Software functions by permission
In the Jira Software documentation, most configuration options are described as being restricted to either Jira administrators, project administrators, or board administrators.  
* A Jira administrator is a user with the Administer Jira global permission.  
* A project administrator is a user with the Administer projects project permission for a particular project. 
* By default, the 'Administer projects' permission is assigned to the 'administrators' group (via the Administrators role) for projects.
* Additionally, to perform sprint-related actions, users need the 'Manage sprints' permission for all projects in the origin board — the origin board being the board in which the sprint was originally created.
* A board administrator is a user that has been added to the Administrators for a particular board. By default, the administrator of a board includes the person who created it.

## Board usage
Board usage permissions are derived from project permissions.
Depending on the complexity of your board's filter query, you may need further consideration when configuring the 'Manage Sprints' permission for users. For more information on the impact of complex filters, and ways to simplify your filter query, see Using Manage Sprints permission for advanced cases

## Learn More
* [Permissions](https://confluence.atlassian.com/jirasoftwareserver/permissions-overview-939938996.html)

## See Also
* [Jira Training](/_posts/2019-12-20-jira-training.md)
* [Additional Resoures](/_posts/2019-12-20-jira-additional-resources.md)

If you cannot find your project, contact your Jira project administrator. If you need additional help, contact the [DevOpsTeam](mailto:DevOpsTeam@va.gov)

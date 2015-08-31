Title: Multiple teams | Visual Studio Online and TFS 
Description: Add another team or a hierarchy of teams to scale your Agile tools when working in Visual Studio Online or Team Foundation Server (TFS)
ms.TocTitle:  Multiple teams
ms.ContentId: 9F1D0A0F-02D5-4E06-A5EC-C220472A0F66

#Multiple teams 
As your organization grows, you'll want to make sure that you configure your Agile tools to support that growth. To enable each feature team the autonomy it needs to manage their backlog and plan their sprints, they need their own set of team tools. 

Adding a team is the #1 way in which Agile tools supports a growing organization. Once your team grows beyond its optimum size--typically anywhere from 6 to 9 members-–you might consider moving from a one team structure to a two team structure. For enterprises adopting Agile tools, setting up a hierarchical team structure provides several advantages to portfolio and program managers to track progress across several teams.  

Each team you create gets access to a suite of Agile tools and team assets. These tools provide teams the ability to work autonomously and collaborate with other teams across the enterprise. 

![Agile tool team assets](_img/agile-tools-team-assets.png)

##Move from one team to two teams 
As your team grows, you can easily move from one team to two. In this example, we add two feature teams, Email and Voice, and maintain the Fabrikam Fiber team with visibility across each of these two teams.  

###Add two feature teams 

Add and configure two teams, Email and Voice. Here we show you how to add and configure the Email team. 

1.	From the web portal, click the ![gear settings icon](../_img/icons/gear_icon.png) icon to open the administration page for the team project.  

	![Open team project admin page](../connect/_img/ALM_CAL_OpenAdminPage.png)  

	If you’re not a project administrator, [get added as one](https://msdn.microsoft.com/library/dd547204.aspx). Only project administrators can add teams.  

2.	Create a new team. Give the team a name, and make sure to select **Create an area path with the name of the team**.

	![Create a sub-team with its own area path](_img/scale-agile-add-new-team-co.png)

	If you do not select this option, you will have to set the default area path for the team once you create it. You can choose an existing area path or create a new one at that time. Team tools aren't available until the team's default area path is set.

3.	Select the team from the Overview tab to configure it. 

	![Select a sub-team to configure it](_img/scale-agile-select-team-to-configure-it-co.png)

5.	Next, open the Iterations tab to activate the set of sprints the team will use.  

	Here, the Email team activates Sprints 1 through 6.  

	![Activate sprints for the team](_img/scale-agile-set-team-sprints-co.png)  

	If your team isn’t listed in the navigation row, open the Overview tab, select your team, and then return to the Iterations tab.

4.	Add team administrators and team members to the new team.

	You can also add team members from the team home page. To learn more about adding people to your team, go here.  

<a id="add-team-members"> </a>  

###Add team members
If you're moving from one team to two teams, team members already have access to the team project. If you're setting up a team structure for the first time, adding user accounts as team members provides them access to the team project and team assets. Access to the team project is required to support sharing code and planning and tracking work. 

Several Agile tools, like capacity planning and team alerts, are team-aware. That is, they automatically reference the user accounts of team members to support planning activities or sending alerts. 

1.	From the Overview tab for your team, add a user account.  

	![Add a Windows user or group account](_img/scale-agile-add-team-account.png)

	<blockquote style="font-size: 13px">**Note:**  If you connect to your team project through Visual Studio Online, see [Add team members](https://www.visualstudio.com/en-us/get-started/setup/add-team-members-vs). The steps are similar but slightly different.</blockquote>  

2.	Enter the sign-in addresses or display name for each account you want to add. Add them one at a time or all at the same time.  

	The first time an account is added to TFS, you must enter the full domain name and the alias. Afterwards, you can browse for that name by display name as well as account name. To learn more, see [Set up groups for use in TFS deployments](https://msdn.microsoft.com/library/hh561430.aspx).  

	![Type the account aliases and check name](_img/scale-agile-add-team-members-user-accounts.png)  

	<blockquote style="font-size: 13px">**Tip:**  You must enter user and group names one at a time. However, after entering a name, the account is added to the list, and you can type another name in the Identities text box before choosing to save your changes.</blockquote>  

3.	Now these users are members of the Email team. You can always return to this page to add or remove members. 

	![Manage team members](_img/agile-scale-manage-team-members.png)

	See [Manage team assets](manage-team-assets.md) to add an account as a team administrator. 

4.	(On-premises TFS only) As a last step, send the team URL to newly added team members so they can start contributing to the team. For example:  
	
	Email team: ```http://fabrikamfiber:8080/tfs/DefaultCollection/Fabrikam%20Fiber/Email```   
	Voice team: ```http://fabrikamfiber:8080/tfs/DefaultCollection/Fabrikam%20Fiber/Voice```   


###Move work items under teams 
Now that your two feature teams are configured, you'll want to move existing work items from their current assignments to the team's default area path. This way, the work items will show up on each feature team's backlog. 

1.	The quickest way to do this, is to [create a query](../track/using-queries.md) of all work items you want to reassign, multi-select those items belonging to each team, and bulk edit the area path. 

	![Bulk modify select work items](_img/scale-agile-bulk-modify-area-path-co.png)

2.	After you bulk modify, do a bulk save. 
 
	![Bulk save selected work items](_img/scale-agile-bulk-save-area-path-co.png)

	See [Bulk modify work items](https://msdn.microsoft.com/library/hh409280.aspx) for more information.  

<a id="include-area-paths"> </a>  

###Configure the default team project  
One last step in moving from one team to two teams requires configuring the default team project to include sub-areas.  

1. Open the Areas tab administration page for the team project, and change the setting as shown.  

	![Bulk modify select work items](_img/agile-scale-include-default-area-paths-co.png) 

2.	Refresh the product backlog page for the team, and you'll see all work items for the two teams listed.  

	![Bulk modify select work items](_img/scale-agile-product-backlog-default-team.png)


##Grant team members additional permissions  

For teams to work autonomously, you may want to provide them with permissions that they don't have by default. Suggested tasks include providing team administrators or team leads permissions to:  

- [Create and edit child nodes under their default area path](../customize/modify-areas-iterations.md)  
- [Create and edit child nodes under an existing iteration node](../customize/modify-areas-iterations.md)  
- [Create shared queries and folders under the Shared Queries folder](https://msdn.microsoft.com/library/dd286628.aspx).  
 
By default, team members inherit the permissions afforded to members of the team project Contributors group. Members of this group can add and modify source code, create and delete test runs, and create and modify work items. They can collaborate with other team members and [check in work to the team's code base](https://msdn.microsoft.com/library/ms181407.aspx) or [collaborate on a Git team project](../../Code/git/get-started.md).  

![Default permissions assigned to team contributors](_img/default-permissions-assigned-to-team-contributors.png)  

If your on-premises TFS deployment includes reporting or SharePoint Products, add users to those resources as described [here](https://msdn.microsoft.com/library/bb558971.aspx). 


###Team group 
When you create a team, you automatically create a team group, which contains the accounts of all members you add to the team. You can manage permissions for team members by setting the permissions of the team group.   

You can use this group to filter queries. The name of team groups follows the pattern [Team Project Name]\Team Name. For example, the following query finds work assigned to members of the [Fabrikam Fiber]\Email team group.

![Query that uses In Group operator and team group name](_img/query-in-group-email-team-work-in-progress.png)

<a id="team-assets"> </a>

##Try this next 

Once you've created a team, you'll want to configure your Agile tools to support how your team works. Also, consider adding one or more accounts as team administrators. Team admins have the necessary permissions to add team members and [configure and manage team assets](manage-team-assets.md).  

If team members don't have access to all the features they want, check that they have [the access level needed for those features](../connect/change-access-levels.md).  

##Related notes

Here are a few other topics related to creating and working with teams: 
- [Link work items to track dependencies](https://msdn.microsoft.com/library/dd293534.aspx)  
- [Track work when contributing to several teams](capacity-planning.md)
- [Restrict access to select features and functions](https://msdn.microsoft.com/library/dn249791.aspx)  
- [Use team fields in place of team area paths](https://msdn.microsoft.com/library/dn144940.aspx)  



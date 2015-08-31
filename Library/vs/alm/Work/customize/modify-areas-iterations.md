Title: Add and modify area and iteration paths | Visual Studio Online
Description: Add and modify area and iteration paths
ms.TocTitle: Add and modify area and iteration paths
ms.ContentId: 23db24bb-e0ff-4bdc-82ab-5c21794296f8

#Add and modify area and iteration paths

Area paths allow you to group work items by team, product, or feature area. And iteration paths allow you to group work into sprints, milestones, or other event-specific or time-related period.

Newly created team projects contain a single, root area that corresponds to the team project name. Whereas, new team projects typically specific a predefined set of iterations to help you get started tracking your work.  

The iterations you see depend on the process you used to create your team project. Here we show the defaults defined for the Scrum process. No dates are set. You set dates to correspond to your sprint or release schedules.


<table>
<tbody valign="top">
<tr>
<td>
![Default areas](_img/ALM_AAI.AreaDefault.png)
</td>
<td>
![Default iterations, Scrum process](_img/ALM_AAI.IterationDefault.png)
</td>
</tr>
</tbody>
</table>
 

##Tools that rely on areas or iterations
Several Agile tools either reference the area, iteration, or both to automatically filter the list or cards they display. Here's a quick summary of these tools: 
<table>
<tbody valign="top">
<tr>
<th width="50%">Agile tool</th>
<th width="50%">References</th>
</tr>
<tr>
<td>
[Product backlog](../backlogs/create-your-backlog.md)
</td>
<td>
Default area path for the team<br/>
Default iteration path for the team
</td>
</tr>
<tr>
<td>
[Kanban board](../kanban/kanban-basics.md)
</td>
<td>
Default area path for the team<br/>
Default iteration path for the team
</td>
</tr>
<tr>
<td>
[Sprint backlogs](../scrum/sprint-planning.md) and [task boards](../scrum/task-board.md)<br/>
[Sprint burndown charts](../scrum/sprint-burndown.md)<br/>
<br/>
For a sprint or iteration backlog page to appear for a team, [you must first define and activate the sprint for the team](../scrum/define-sprints.md#activate).

</td>
<td>
Default area path for the team<br/>
Activated iteration paths for the team<br/>

</td>
</tr>
<tr>
<td>
[Velocity charts](../scrum/define-sprints.md#velocity-forecast) <br/>
[Forecast tool](../scrum/define-sprints.md#velocity-forecast) 
</td>
<td>
Default area path for the team<br/>
Activated iteration paths for the team
</td>
</tr>
<tr>
<td>
[Default shared queries](https://msdn.microsoft.com/library/dd380734.aspx)<br/>
[Queries that filter based on Area or Iteration](../track/using-queries.md)<br/>
[Queries that contain the @CurrentIteration variable](https://msdn.microsoft.com/library/dn947439.aspx)
</td>
<td>
Default area path for the team<br/>
A specified iteration or the team's current iteration
</td>
</tr>

</tbody>
</table>

Many of these tools are built from system queries that reference the team area path. For example, a team’s default area path filters the work items that appear on team’s backlog. Also, work items that you create using an Agile tool auto-assign the areas and iterations based on team defaults.  

You can view these queries by choosing the **Create query** link that appears on these tools’ pages. (Note that you can’t change the underlying query.)

You can quickly generate [queries](../track/using-queries.md) or [filter reports](https://msdn.microsoft.com/library/dd380714.aspx) to view the progress for those areas and iterations. As an example, you can [visualize progress of work items assigned to sprints](../../report/charts.md) as shown in the following stacked bar chart.  

![Stacked bar chart by area](_img/ALM_CW_StackedBarChart.png)

Lastly, you can set  security permissions to control who has access to create, modify, or manage test plans and test suites under an area.

##Add an area

0. Open the project administration page from the web portal.

	![Open the project administration page](_img/ALM_CW_OpenProjectAdmin.png)

	To manage areas and iterations you need to be a project administrator or have the **Create child nodes** permission for an area path. If you aren’t a project administrator, [get added as one](../scale/manage-team-assets.md#add-team-admin). 

0. Open the **Areas** tab.

	![Open the areas page](_img/ALM_CW_OpenAreas.png)
	
	From the areas page, you can set the default area path used to filter the backlog.  The default area path is also used when new work items a user creates new work items. 

0. Add a new child node to the area you have selected.
 
	![Create a new area node](_img/ALM_CW_CreateArea.png)
	
	Certain [restrictions](#name-restrictions) apply on names of areas.

##Add an iteration and set iteration dates
From the **Iterations** page, you can add and select the iterations that will be active for your team. You add iterations in the same way you add areas.

0. Teams can choose which iterations they work in by checking the check box next to each iteration.

	![Open the iterations page](_img/ALM_CW_OpenIterations.png) 

0. Each iteration can have a start and end date.  After you set the start and end dates for one iteration, the calendar tool automatically defaults the next set of dates, based on the same iteration length you specified for the first.

	**Example:** if you set a 3 week sprint for Sprint 1, then when you select the start date for Sprint 2, the calendar tool automatically determines the start and end dates based on the next three weeks.

	![Define start and end dates for a sprint](_img/ALM_CW_SetIterationDate.png)  

<a id="set-permissions" >  </a> 

##Set permissions on editing paths or accessing work items assigned to an area  

Permissions placed on an area paths allows you to permit or restrict access to edit or modify work items, test cases, or test plans assigned to those areas. You can restrict access to users or groups. You can also set permissions for who can add or modify areas or iterations for the team project.  

1. Open the **Security** dialog for the node you want to manage.  

	![Open the security dialog](_img/ALM_CW_OpenSecurityDialog.png)

2. Select the group or team member, and then change the permission settings. For example, for the Disallow Access Group, deny the ability to view, modify, or edit work items in the FabrikamFiber area path.

	![Permissions for an area node](_img/ALM_CW_PermisionsForArea.png)

	If the group or team member doesn’t appear in the list, you can [**Add** it](https://msdn.microsoft.com/library/bb558971.aspx).  
	
You can specify two explicit authorization states for permissions: **Deny** and **Allow**. In addition, permissions can exist in one of three additional states.  

| Permission 		| Authorization |
| ----------------- | ------------- |
| Allow 			| Explicitly grants users to perform the task associated with the specific permission. For users to access a task, the associated permission must be set to **Allow** or **Inherited allow**. |
| Deny 				| Explicitly prevents users from performing the task associated with the specific permission. **Deny** takes precedence over **Allow**. <br/>For exceptions to these rules, see [Permissions reference](https://msdn.microsoft.com/library/ms252587.aspx#perm_states)|
| Inherited allow/Inherited deny 	| Allows or denies a user to perform the task associated with the permission based on the permission set for a group to which the user belongs. |
| Not set         	| Implicitly prevents users from performing the action associated with the permission. <br/>Because the permission is neither explicitly set to **Deny** nor explicitly set to **Allow**, authorization for that permission can be inherited from other groups of which the user or group is a member. <br/>By default, most permissions are not set to either **Deny** or **Allow**, the permissions are left **Not set**.  |


For additional ways to restrict modifications to work items, see [Restrict who can create or modify a work item](https://msdn.microsoft.com/library/ms404857.aspx). 

###Test management permissions  

Area permissions for web-based test case management and test execution control access to the following actions. 
<table>
<tbody valign="top">
<tr>
<td>
<p>The **Manage test suites** permission enables users to:</p>
<ul>
<li>Create and modify test suites</li>
<li>Add or remove test cases to/from test suites</li>
<li>Change test configurations associated with test suites</li>
<li>Modify the suite hierarchy by moving a test suite</li>
</ul>
</td>
<td>
<p>The **Manage test plans** permission enables users to:</p>
<ul>
<li>Create and modify test plans </li>
<li>Add or remove test suites to or from test plans</li>
<li>Change test plan properties such as build and test settings</li>
</ul>
</td>
</tr>
</tbody>
</table>


Additional test management permissions are assigned at the team project level and include the ability to create, delete, and view test runs, and manage test configurations and environments. See [Project, object, and test-level permissions](https://msdn.microsoft.com/library/ms252587.aspx##project_plus).  


##Related notes 
As you can see, areas and iterations play a major role in supporting Agile tools and managing work items. You can learn more about working with these fields from these topics: 

*	[Add another team](../scale/multiple-teams.md)
*	[Agile tools and sprint definitions ](../scrum/define-sprints.md)
*	[Query by date or current iteration](https://msdn.microsoft.com/library/dn947439.aspx)
*	[Define the initial areas and iterations for a process](https://msdn.microsoft.com/library/ms243840.aspx)
*	[Areas and iterations field reference](https://msdn.microsoft.com/library/dd99[Use team fields instead of area paths to support teams](https://msdn.microsoft.com/library/dn144940%28v=vs.140%29.aspx)


##Q & A

<!-- BEGINSECTION class="md-qanda" -->

###Q: What permissions do I need to add or modify area and iteration paths?

**A: **To create or modify areas or iterations, you must either be a member of the **Project Administrators** group, or your **Create and order child nodes**, **Delete this node**, and **Edit this node** permissions must be set to **Allow** for the area or iteration node that you want to modify.


###Q: What happens when I rename or delete an area or iteration node?

**A: **When you rename an area or an iteration, or move the node within the tree hierarchy, you must manually update the work items that reference the existing path or paths. You can perform a bulk update using TWA or Excel. 

When you delete an area or an iteration node, the system automatically updates the existing work items with the node that you enter at the deletion prompt. 

###Q: How do I structure teams, areas, and iterations to support hierarchical teams or scale agility within an enterprise?

**A: **Although there is no concept of sub-teams, you can create teams whose area paths are under another team, which effectively creates a hierarchy of teams. To learn more, see [Add another team](../scale/multiple-teams.md).

Also, these two white papers can walk you through the steps for configuring teams, area paths, and iterations to support portfolio management or enterprise organizations: [Agile Portfolio Management: Using TFS to support backlogs across multiple teams](https://msdn.microsoft.com/library/dn306083.aspx) and [Scaled Agile Framework: Using TFS to support epics, release trains, and multiple backlogs](https://msdn.microsoft.com/library/dn798712.aspx).

###Q: Can I use a team field instead of the area path to support access to different teams?

**A: ** Yes. If your organization has several teams that work from a common backlog and across many product areas, you might want to change how teams are configured. By [adding a custom field to represent teams](https://msdn.microsoft.com/library/dn144940%28v=vs.140%29.aspx) in your organization, you can reconfigure the agile planning tools and pages to support your teams and decouple assignment to teams and area paths. 

###Q: What kind and how many areas should a team define?

**A: **You add areas to support your team's trace-ability and security requirements. Use areas to represent logical or physical components, and then create child areas to represent specific features.  

Add areas when you have these requirements: 
*	Filter queries based on a product or feature area 
*	Organize or group work items by team or sub-teams  
*	Restrict access to work items based on their area.  

Each team can create a hierarchy of areas under which the team can organize their backlog items, user stories, requirements, tasks, and bugs.

Avoid creating an area structure that is too complex. You can create areas to partition permissions on work items, but complex trees require significant overhead for permission management. You might find that it is too much work to duplicate the structure and permissions in other team projects.

###Q: What kind and how many iterations should a team define?

**A: **You define as many child iterations as you need to reflect your project lifecycle. These paths represent a series of events, such as sprints, pre-beta and beta deliverables, and other release milestones. Teams typically leave work items assigned to the team's default iteration if they are not yet scheduled for work or for a release.  

Add iterations to support these requirements:  
* Define sprints your Scrum teams use to [plan and execute their sprints](../scrum/sprint-planning.md)
* Set up more complex multi-release and sprint cycles
* Filter queries based on sprints, milestones, or cycle time for your project 
* Support future work that you’re not ready to assign to a target release cycle.  

In the following example, Backlog, Beta 1, Beta 2, Release 1.0, and Release 2.0 are defined for the MyApplication team project.  

![Flat iteration hierarchy](_img/ALM_CW_IterationHierarchy-Before.png) 

As you create the backlog of product features and tasks, you can start to assign them to the milestones by which you expect the team to finish the features and tasks.
As your needs change, you can add events under each major milestone that reflect how your team schedules and manages its work.  

As the following example shows, the Beta 1 iteration now contains three child nodes, one for each sprint in the Beta 1 time period.  

![Hierarchical Iteration Hierarchy](_img/ALM_CW_IterationHierarchy-After.png)

Iterations do not enforce any rules. For example, you can assign a task to an iteration but not close or complete it during that iteration. At the end of an iteration, you should find all work items that remain active or have not been closed for that iteration and take appropriate action. You can, for example, move them to a different iteration or return them to the backlog.  


<a name="name-restrictions"></a>

###Q: What restrictions do I need to follow when naming and structuring child nodes?

**A: **The **Area Path** and **Iteration Path** fields, [data type=TreePath](https://msdn.microsoft.com/library/dd997576.aspx), consist of multiple node items which are separated by the backslash (&#92;) character. We recommend that you minimize the names of nodes, and make sure that you conform to the following e restrictions when adding child nodes:

| Restriction type | Restriction |
| ---------------- | ----------- |
| Node length | Must not contain more than 255 characters |
| Special characters for nodes | Must not contain Unicode control characters<br/>Must not contain any of the following characters: \ / $ ? * : " & > < # % + ,<br/>Must not contain characters that the [local file system prohibits](https://msdn.microsoft.com/library/aa365247.aspx). |
| Reserved names | Must contain more than a period (.) or two periods (..)<br/>Must not be a [system-reserved name](https://msdn.microsoft.com/library/aa365247.aspx) such as PRN, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, COM10, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8, LPT9, NUL, CON, or AUX<br/>|
| Path length | Must contain fewer than 4,000 Unicode characters |
| Path hierarchy depth | Must be fewer than 14 levels deep |

###Q: What restrictions do I need to follow when setting a field rule on the Area Path and Iteration Path fields?

**A: **You can [specify only a small subset of rules](https://msdn.microsoft.com/library/ms404857.aspx#system), such as ```HELPTEXT``` and ```READONLY``` to System.XXX fields. 

###Q: Can I export the area and iteration paths?

**A: **No. You can’t export the structure of tree paths for one team project to use with another team project.  

<!-- ENDSECTION -->
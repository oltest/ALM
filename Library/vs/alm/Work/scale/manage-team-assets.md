Title: Manage team assets | Visual Studio Online and TFS 
Description: Manage team assets and Agile tools when working in Visual Studio Online or Team Foundation Server (TFS)
ms.TocTitle:  Manage team assets
ms.ContentId: 6BF2B72D-9160-4140-B8DE-B2C7C42AC338

#Manage team assets

As a team administrator, you can configure, customize, and manage all team-related activities for your team. These include being able to add team members, add team admins, and configure Agile tools and team assets. 

Team admin permissions are role-based, unlike project admin permissions which are set through the user interface. Also, because team administrators are members of the Contributor role they have permissions assigned to that role.  

The following table summarizes a subset of the default permissions assigned to the team project Readers, Contributors and Project Administrators groups and the Team Administrator role. Team admin permissions extend only to the team for which they're an administrator. Project administrator permissions extend across all teams defined for the team project.


###Manage team members and permissions
<table>
<tbody valign="top">
<tr>
<th>Permission</th>
<th>Readers</th>
<th>Contributors</th>
<th>Team Administrators</th>
<th>Project Administrators</th>
</tr>

<tr>
<td>
<p>[Add a team administrator](#add-team-admin) </p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>
<tr>
<td>
<p>
[Add team members](multiple-teams.md) </p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>
<tr>
<td>
<p>[View shared work item queries](../track/using-queries.md)</p>
</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>
<tr>
<td>
<p>
[Manage shared query and query folder permissions](https://msdn.microsoft.com/library/dd286628.aspx)<br/>(Contribute, Delete, Manage Permissions)
</p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>



</tbody>
</table>



###Configure and work with team assets
<table>
<tbody valign="top">
<tr>
<th>Permission</th>
<th>Readers</th>
<th>Contributors</th>
<th>Team Administrators</th>
<th>Project Administrators</th>
</tr>

<tr>
<td>
<p>
Manage the [Product backlog](../backlogs/create-your-backlog.md) </p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td><p>[Choose active team backlogs](../backlogs/organize-backlog.md) </p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td><p>[Show bugs on backlogs and boards](../customize/show-bugs-on-backlog.md) (Note 1)</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td><p>View team [Velocity](../scrum/velocity-and-forecasting.md)</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td><p>[Forecast](../scrum/velocity-and-forecasting.md)</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td>
<p>
Work with the [Kanban board](../kanban/kanban-basics.md) </p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td>
<p>
Customize the Kanban board: (Note 1)</p>
<ul>
<li>[Add columns](../kanban/add-columns.md) </li>
<li>[WIP limits](../kanban/wip-limits.md)   </li>
<li>[Split columns](../kanban/split-columns.md)  </li>
<li>[Expedite work](../kanban/expedite-work.md)</li>
<li>[Definition of Done](../kanban/definition-of-done.md)</li>
<li>[Customize cards](../customize/customize-cards.md) </li>
</ul>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td>
<p>Work with sprint team assets </p> 
<ul>
<li>[Manage sprint backlogs](../scrum/sprint-planning.md) </li>
<li>[Manage task boards](../scrum/task-board.md)</li>
<li>[Capacity planning](capacity-planning.md)  </li>
</ul>
</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td>
<p>Configure sprint team assets </p> 
<ul>
<li>[Activate team sprints](../scrum/define-sprints.md) </li>
<li>[Set working days off](capacity-planning.md)  </li>
</ul>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td>
<p>[View team dashboard(s)](../../Report/dashboards.md)</p>
</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td>
<p>
[Manage team dashboard(s)](../../Report/dashboards.md)<br/>
(add/remove widgets, pin/unpin items)
</p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>


<tr>
<td>
<p>
[Set personal alerts, get notified when changes occur](../track/alerts-and-notifications.md) </p>
</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td>
<p>
[Create and manage team alerts](../track/alerts-and-notifications.md) (Note 2)</p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>


<tr>
<td>
<p>
[Collaborate in a team room](https://msdn.microsoft.com/library/dn169471.aspx) </p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td>
<p>
[Create and manage team rooms](#teamrooms)<br/>Team administrators can manage their team rooms. Project Administrators groups can create and administer team rooms that they've created.</p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>



</tbody>
</table>


###Access shared team project resources
<table>
<tbody valign="top">
<tr>
<th>Permission</th>
<th>Readers</th>
<th>Contributors</th>
<th>Team Administrators</th>
<th>Project Administrators</th>
</tr>
<tr>
<td>
<p>
[Create and add tags](https://msdn.microsoft.com/library/dn132606.aspx)
</p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>


<tr>
<td>
<p>Area node: Edit work items under the node</p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>
<tr>
<td>
<p>
[Area nodes and Iteration nodes: Create, delete, edit child nodes](../customize/modify-areas-iterations.md) </p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>
<tr>
<td>
<p>View project-level information</p>
</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>

<tr>
<td>
<p>Edit project-level information <br/>(This permission grants users access to all team administration tasks across all teams defined for the team project.) </p>
</td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td><p>&nbsp;&nbsp;</p></td>
<td>![checkmark](../_img/icons/checkmark.png)</td>
</tr>


</tbody>
</table>



For a comprehensive list of all permissions and default groups, see the [Permissions reference for TFS](https://msdn.microsoft.com/library/ms252587.aspx). 


<a id="add-team-admin">  </a>  

##Add an account as a team administrator

It’s always a good idea to have more than one person with administration permissions for an area. 

1. If you’re not a team administrator, get added as one using this procedure. Ask an administrator for your team project or project collection to add you as an administrator.  

2. Add an administrator from the web portal team admin context.  

	![Open team administration context](_img/add-account-as-team-admin.png)  

	To access this page, choose the ![gear icon](../_img/icons/gear_icon.png) gear icon from your team home page.  

3. Add the account identity.  

	![Add account as a team administrator](_img/add-team-admin-dialog.png) 

<a id="teamroom">  </a>
        
##Administer team room permissions

You can grant permissions to users to administer a team room.  

1. From the context menu, open permissions for the team room.  

	![Open team room permissions](_img/open-security-team-room.png)  

2. Add an account, set the permissions for Administer to **Allow**, and save the changes.   

	![Add menu on Permissions page for a team room](_img/add-team-admin-dialog.png) 

 <a id="team-room-permissions"> </a>

###Create and manage a team room  
A team room is created for each team that gets created. Team administrators can create additional rooms and manage their team rooms.  

Members of the Project Administrators groups can create and administer team rooms that they have created. And, members of the Project Collection Administrators groups can create and administer all team rooms.  

<a id="team-room-event-permissions">  </a>

###Permissions to open team room events
               
Permissions on team room events are managed by their associated operational area. It is possible for a team member to have permissions to collaborate within a team room, yet not be allowed to view work items, build definitions, or source code that have alerts enabled in the team room. 

For information about where these permissions are set in the web portal, see [Restrict access in TFS](https://msdn.microsoft.com/library/dn249791.aspx).

##Related notes 

To create additional teams, see [Multiple teams](multiple-teams.md).  

If team members don't have access to all the features they want, check that they have [the access level needed for those features](../connect/change-access-levels.md).  

You can also [restrict access to select features and functions](https://msdn.microsoft.com/library/dn249791.aspx).

###Team name, description, and picture

Team settings also include the team name, description, and team profile image.  

To add a team picture. Open the administration page and choose the picture icon under Team Profile. The maximum file size is 4 MB. 


 
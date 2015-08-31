Title: Show bugs on backlogs and boards | Visual Studio Online and TFS
Description: Teams choose how bugs appear on Agile tool product and sprint backlogs and Kanban and task boards in Visual Studio Online and team projects connected to Team Foundation Server (TFS)
ms.TocTitle: Show bugs on backlogs and boards
ms.ContentId: 27DCB879-30F6-44F3-998A-755DF66D6E24

#Show bugs on backlogs and boards
As your team identifies code defects or bugs, they can add them to the backlog and track them similar to requirements. Or, they can schedule them to be fixed within a sprint along with other tasks. 
 
When you track bugs as requirements, they'll show up on the product backlog and Kanban board. When you track bugs similar to tasks, they’ll show up on the sprint backlogs and task boards.


##Set your team's preferences for tracking bugs  

1. From Visual Studio Online or the web portal for your team project, open the administration page.  

	![Gear icon provides access to admin pages](_img/control-panel-open.png)

2. From the Overview tab, choose the team whose settings you want to configure.

3. Open **Settings** and choose from the three options available.

 * Choose the first option when your team wants to manage bugs similar to requirements. Bugs can be estimated and tracked against team velocity and cumulative flow.  

 * Choose the second option when your team wants to manage bugs similar to tasks. Remaining work can be tracked for bugs and tracked against the sprint capacity and burndown.  

 * Choose the last option if your team manages bugs separate from requirements or tasks.  

 	![Team Settings page, track bugs on backlog](_img/team-settings.png)  

 	Because this setting affects all team members’ view of the team backlogs and boards, you must be a team administrator to change the setting. Changing the setting is disabled if you’re not a team administrator. Go [here to get added as a team administrator](../scale/manage-team-assets.md#add-team-admin).  

4. To see the changes, open or refresh the team’s [backlog](../backlogs/create-your-backlog.md) or [sprint backlog pages](../scrum/sprint-planning.md).  

## How hierarchical items appear in backlog and board views
 
While you can create a hierarchy of backlog items, tasks, and bugs─we don’t recommend that you do. The Kanban board, sprint backlog, and task board only show the last node in a hierarchy, called the leaf node. For example, if you link items within a hierarchy that is four levels deep, only the items at the fourth level appear on the Kanban board, sprint backlog, and task board.  

Instead of nesting requirements, bugs, and tasks, we recommend that you maintain a flat list─only creating parent-child links one level deep between items. Use the feature work item type when you want to group requirements or user stories. You can [quickly map stories to features](../backlogs/organize-backlog.md), which creates parent-child links in the background.  

Read the next two sections to better understand how child items appear in the Agile tools.  

<a id="leaf-nodes">  </a>
## When bugs appear on the backlog and boards with requirements

When you make a bug or requirement a child of another bug or requirement, all items appear on the product backlog page, but only the child bug or requirement appears on the Kanban board. For example, the third user story, Interim save on long form, has a child bug, Save takes too long. 

The bug appears on the Kanban board, but not the parent user story.  

**All bugs and requirements appear on the backlog**  

![Child bug appears on backlog ](_img/bugs-appear-on-backlog.png)  

**Only leaf nodes appear on the Kanban board**  

![Kanban board, leaf node bug appears](_img/bugs-appear-on-board.png)  

## When bugs appear on the backlog and boards with tasks  

When you choose to have bugs appear in the backlog with tasks, linking tasks and bugs to their parent requirements groups them accordingly on the sprint backlog and task board.  

However, if you create parent-child links between a requirement and a bug, and the bug and a task, as shown here &#133;  

**Hierarchy of items assigned to the sprint backlog**  

![Sprint backlog query shows linked bug and task ](_img/sprint-backlog-hierarchy.png)   

&#133; only the task and not the bug will appear on the sprint backlog  

**Only leaf nodes appear on the sprint backlog and task board**  

![Sprint backlog, leaf node task ](_img/sprint-backlog-leaf-only.png)  

&#133; and only the task will appear on the task board.  
 
![Sprint board, leaf node task appears](_img/bugs-appear-on-taskboard.png)  

Is there a workaround to display intermediate nodes within a hierarchy?  Not at this time. You can always check the entire list of items assigned to a sprint by using the **Create Query** link. 


##Related notes
Bugs are a common item that teams want to track, and choose how they track it. However, what if you want to track other work item types (WITs) on your backlogs and boards?  

You can add other WITs&#8212;such as change requests, issues, or impediments&#8212; 
 by customizing your process or team project, based on whether you work in the cloud or on-premises: 
*	**Visual Studio Online:  **[Customize a process for import](../import-process/customize-process.md)  
*	**On-premises TFS:  **[Add work item types to backlogs and boards](add-wits-to-backlogs-and-boards.md)  

Other quickly configurable options you can make:
*	[Customize cards on the Kanban board or task board](customize-cards.md)
*	[Activate backlogs of interest to your team](../backlogs/organize-backlog.md#activate-backlogs) 






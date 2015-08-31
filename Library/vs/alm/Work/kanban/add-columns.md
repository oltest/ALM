Title: Add columns | Visual Studio Online
Description: Various ways to customize your kanban board - Visual Studio Online and Team Foundation Server
ms.TocTitle: Add columns
ms.ContentId: 8afd3481-6fab-401d-90ff-0dd443da0f0e

#Add columns
Kanban’s number one practice is to visualize the flow of work. Accordingly, your number one task is to visualize your team’s workflow. You do this by identifying the types of work and handoffs that occur regularly as your team moves items off the backlog and into a shippable state.

After you identify your team’s workflow stages, you’re ready to [configure your Kanban board to map to them](add-columns.md#add-or-rename-columns). Once configured, you use your Kanban board to update status, reassign work, and reorder items to reflect changing priorities.

For example, the main workflow stages performed by our example dev team are captured here as Analyze, Develop, and Test. Each column corresponds to a work stage the team performs on each item before it can be considered done.

![Kanban board, columns customized ](_img/ALM_AC_KanbanIntro.png)

If you’re just getting started, review [Kanban basics](kanban-basics.md) to get an overview of how to access your board and implement Kanban.

<a id="map-the-flow-of-work">  </a>

##Map the flow of work
It’s best if you involve the entire team to identify an initial set of workflow stages. Each team member provides useful perspectives to capture and further deepen team understanding of the end-to-end processes.

To get started, ask your team these questions: 

* What types of activities do we regularly perform? 

* What natural handoffs occur within our team? Or, from our team to other teams? 

* What activities will help reinforce our team policies, such as analysis, code review, or design acceptance?

* What work needs to occur at each stage? 


Our example dev team came up with these stages as essential to their process: 

![Example workflow stages ](_img/ALM_AC_Workflow.png)

* **Backlog**: Prioritized list of items which aren’t yet ready to work on

* **Analyze**: Well understood and shared acceptance criteria identified and overall work required to develop and test item

* **Develop**: Code and run unit tests for the item

* **Test**: Perform exploratory, automated, integration, and other tests

* **Done**: Item ready to handoff to production.


You can always revisit these initial stages later and adjust. 

Another idea, capture the list of items your team identifies as critical-to-complete for each stage. You can use that later to fill out the [Definition of Done](http://msdn.microsoft.com/library/dn914589.aspx) for each column. 

## Update status and handoff items

Using your Kanban board couldn’t be simpler. Using drag-and-drop operations you update the status or change priorities. 

For example, to signal when work can start in a downstream stage, simply drag items into the next column. 

![Kanban board, move an item](_img/ALM_AC_DragItem.png)

You’ll notice that you can move an item from one column to any other column on the board. That way, if you discover more work is needed at an earlier stage, you can simply move the item backward, for example from Test into Analyze or Develop. 

Also, to handoff work to another team member, simply reassign it directly from the board.

![Kanban board, assign item](_img/ALM_AC_Reassign.png)

And, team members receiving the handoff can [set alerts](../track/alerts-and-notifications.md) to receive immediate email notifications of their newly assigned work. 

## Change priorities

To keep teams working on the highest priority items, you’ll want to react quickly when a change in priority occurs even after work starts. With your Kanban board it’s a snap. Simply drag an item up or down within a column.

![Kanban column, reorder within column ](_img/ALM_AC_ChangePriorities.png)

<a id="add-or-rename-columns"> </a>

##Add or rename columns

Now that you’ve got the essentials of how to work with your Kanban board, here’s how you get it to look like what you need it to.

1. From your Kanban board, click ![settings icon](../_img/icons/gear_icon.png) and as needed, click Columns.  

	![Kanban board, open settings-columns ](../customize/_img/kanban-card-customize-open-settings.png)
	
	If you’re not a team admin, [get added as one](../scale/manage-team-assets.md#add-team-admin). Only team and project admins can customize columns.

	You’ll see different column titles and choices based on the following:
	
	- You connect to Visual Studio Online or an on-premises TFS
	- The [Process](../guidance/choose-process.md) you used to create your team project  
	- Whether your team has chosen to [treat bugs like requirements or like tasks](../customize/show-bugs-on-backlog.md)  

	**Visual Studio Online options:**  
	Click a column tab to see all the settings you can modify. Your initial column settings will look something like this.   
	![Kanban board, Customize columns, default columns, Agile process](_img/vso-column-settings-active-agile-no-tags.png)  

	**On-premises TFS options:**   
	![Kanban board, Customize columns, default columns, Agile process ](_img/ALM_AC_CustomizeColumns.png)  

3.	Change your column titles to map to your workflow stages. You can add, rename, and move columns to support more stages.  

	Here, we rename the first, second, and third columns to Backlog, Analyze, and Develop. We then add a column and label it Test. 
	
	**Visual Studio Online:**  
	![Kanban board, add and rename columns](_img/vso-column-settings-add-rename-columns-no-tags.png)  

	**On-premises TFS:**   
	![Customize columns, add column ](_img/ALM_AC_CustomizeColumnsDetailed.png)
	
	Rename column titles to best reflect each stage of work. Keep the column titles as simple as possible.
	
4.	To change the column order:  
	- **Visual Studio Online:** Simply drag the column tab to the position you want.  
	- **On-premises TFS:** use the left ![left arrow](_img/ALM_AC_LeftIcon.png) or right ![right arrow](_img/ALM_AC_RightIcon.png) arrow icons.  

5.	To delete a column, first make sure that the column doesn’t contain any work items. If it does, move the items to another column.  

	**Visual Studio Online:**  Click Delete on the column tab menu.  
	![Kanban board, delete a column](_img/kanban-delete-column.png)  
	**On-premises TFS:**   Click X at the top of the column. 

6.	[Change State mappings as needed](#state-mappings) for added columns, added workflow states, or added work item types (WITs).  
	Usually you need to do this when you change the [Working with bugs](../customize/show-bugs-on-backlog.md) setting or add [WITs to the Requirement Category](../customize/add-wits-to-backlogs-and-boards.md). 


## Related Kanban notes

That’s about all you need to know about working with Kanban columns. Here are a few more options you have for customizing the look and feel of the board. 

* [Work in Progress limits ](wip-limits.md)  
* [Add swimlanes, expedite work](expedite-work.md)   
* [Split columns](split-columns.md)   
* [Definition of Done](definition-of-done.md)  
* [Customize cards](../customize/customize-cards.md) 

<a id="state-mappings" >   </a>
### Kanban column-to-State mappings and tracking column moves

Your Kanban board is but one of several tools you have for tracking work. The [query tool](../track/using-queries.md) allows you to list a subset of work items for the purposes of review, triage, update, or chart generation. For example, you can create a query to list all active user stories (specify two clauses: Work Item Type=User Story; State=Active). 

But what if you want to list items based on their Kanban column assignment? Can you do that? The short answer: not at this time, and it’s explained more in this blog post: [Kanban customizable columns, “under the hood”](http://blogs.msdn.com/b/visualstudioalm/archive/2013/02/28/kanban-customizable-columns-under-the-hood.aspx).

What you can do is view the history of changes made to a work item. The [History field](http://msdn.microsoft.com/library/ms181319.aspx) captures all updates made to an item, including column moves. You can view this by opening the card (double-click to open). 

For example, the following History shows two updates made by dragging the item into a different Kanban column. The first (revision 8) involved a column move, from Analyze to Develop; and a State change, New to Active. However, the second (revision 9) only involved a column move, from Develop to Test; the State remains at Active.
 
![History field updates with Kanban column moves ](_img/ALM_AC_History.png)

As an item’s card moves from one Kanban column to the next, the item’s workflow state updates based on the Kanban column-to-State mapping. You can see and set these mappings from the Customize Columns dialog. For example, here’s the default mapping for the Agile user story.

![Kanban column to State mappings ](_img/ALM_AC_State.png)

Kanban columns may correspond to an actual workflow state or a pseudo state. For example, Develop, Test, and Verify columns may all map to the Active state. In this case, when you move an item from Develop to Test or from Test to Verify, the item’s State doesn’t change. 

### <a id="when-to-update-the-kanban-column-to-state-mappings"></a>When to update the Kanban column-to-State mappings
 
Another “under the hood” item that impacts Kanban column-to-State mappings is categories. The Kanban board and other Agile tools uses categories to group WITs that they want to treat the same. 

What does this mean for Kanban board users? First, only work items whose WITs belong to the Requirement Category show up on the Kanban board. Second, if you add bugs or other WITs to appear on the Kanban board, you potentially introduce additional workflow states. This means that you may need to adjust the Kanban column-to-State mappings when you perform one of these additional customizations:

* Your team administrator chooses to [show bugs on backlogs and boards](../customize/show-bugs-on-backlog.md)

* Your project administrator [adds WITs to backlogs and boards](../customize/add-wits-to-backlogs-and-boards.md) (on-premises TFS team projects only)

* You project administrator [customizes the workflow for a WIT in the Requirement Category](http://msdn.microsoft.com/library/ms194981.aspx)  

For example, if you change the team setting and add bugs to the Requirements Category, the bug WIT will now appear in the Customize Columns dialog. You’ll want to make sure that the Kanban column-to-State mappings match what you want. 

![Kanban column to State mappings with bugs ](_img/ALM_AC_Update.png)

With Agile tools, you have a mix of features that you can [configure or customize](http://msdn.microsoft.com/library/hh543813.aspx). 



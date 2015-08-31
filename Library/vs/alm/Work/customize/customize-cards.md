Title: Customize cards | Visual Studio Online and TFS
Description: Customize cards on the Kanban and task boards for Agile tools in Visual Studio Online and Team Foundation Server
ms.TocTitle: Customize cards 
ms.ContentId: 951A73EA-7411-4A2A-B3F0-ACBBC7EFC68F


#Customize cards 

While many work tracking views show up as lists – such as your backlogs and queries – board views display cards. Information rich cards not only provide at-a-glance info of interest to you and your team, they also provide a way for you to update a field without opening the work item. And, with style rules, you can highlight those work items with select colors based on the criteria you set.  

Each card corresponds to a work item which you use to share information, track status, and assign work. 

In this example, the bug work item type (WIT) shows all the core fields, three additional fields, and tags. Also, To make severity 1 bugs stand out, a styling rule has been added to cause the card to display as yellow.  

<table>
<tbody valign="top">
<tr>
<td>
In this example, the following customizations have been set for the bug work item type (WIT):
<ul>
<li>Show all core fields: ID, Assigned To, Story Points, Tags </li>
<li>Show three additional fields: State, Changed By, and Changed Date</li>
<li>Apply tag colors</li> 
<li>Apply styling rule to display bugs with Severity=1 as yellow and bold and underline the Title field</li>  
</ul>
</td>
<td width="460px">
![Card customize to show additional fields, tags, and style rule ](_img/card-customize-example-bug-with-callouts.png)
</td>
</tr>
</tbody>
</table>


<blockquote style="font-size: 13px">**Note:  **Some features are only available when you work from Visual Studio Online. </blockquote>  

You can either increase or simplify the information that displays on your cards. It all depends on what's of interest to your team. Does your team like to refer to work items by their ID? Do they want to see estimates? Do they want to highlight work items according to set criteria? Or, will just the bare bones of title and assignment suffice? 

Your best bet is to show fields on cards based on what your team frequently refers to or updates when using the Kanban and task boards. If you’re new to working with these tools, see [Kanban basics](/Library/vs/alm/Work/kanban/kanban-basics.md) and [Sprint planning](../scrum/sprint-planning.md). 

##Add fields and update them from the board
Using the board views provides you with quick and easy ways to update work items as work progresses. Making daily or frequent updates helps everyone on your team stay in sync with what’s been done and what needs doing next. 

To update status of a work item, you simply drag-and-drop cards to a different column. To change the order or stack ranking of a work item, you drag a card up or down within a column. 

For example, on the Kanban board, moving the card from Analyze to Develop updates the corresponding State field. In this case, the State field updates from Approved to Committed. 

![Kanban board, move a work item](_img/ALM_CC_MoveCard.png)

Another handy feature is to simply update a field without having to open the work item. You can update most fields shown on the card. Here we reassign a requirement. 

![Kanban board, assign a work item](_img/ALM_CC_UpdateFieldOnCard.png)

This quick update feature is particularly useful when you need to update a number of work items at once. For example, you can add estimates for backlog items on the Kanban board or update remaining work on the task board. 

To change the title, click the pencil icon in the upper-right corner. To add tags, double-click the work item to open it. And, just a reminder, you can’t change the IDs for a work work item, not from the card and not from within the form. 

To customize cards on the Kanban board, go [here](#kanban-board). To customize task board cards, go [here](#task-board).  


##Highlight work items based on custom criteria 

<blockquote style="font-size: 13px">**Note: ** *This feature is currently supported only on the Kanban and task boards for Visual Studio Online.*  </blockquote>  

With styling rules, you can cause cards to change color when their corresponding work items meet criteria that you set. Here, we highlight severity 1 bugs by having the cards display as yellow. 

![Styling rule applied to bugs with Severity=1](_img/kanban-board-card-style-rule-example.png)


###Example styling rules 
What rules should you apply to highlight work items? Here are a few examples and their associated criteria . 


| Work items | Criteria |
|------------|------------|
| High priority items | ```Priority = 1``` |
| High effort items | ```Effort > 20 ``` or ```Story Points > 20 ``` |
| Stale items unchanged in the last 5 days | ```Changed Date > @Today-5``` |
|Title contains a key word | ```Title Contains Yes``` |
|Severity 1 bugs | ```Severity = 1 - Critical   AND   Work Item Type = Bug``` |
|High value business items | ```Business Value > 50``` |
|Items assigned to specific feature area  | ```Area Path Under Fabrikam Fiber\Phone``` |
|Contains specific tag   | ```Tags Contain RTM``` |
|Blocked tasks (Scrum process only) | ```Blocked = Yes``` |

[Add style rules](#style-rule).

<a id="kanban-board">  </a>

##Change how cards display on the Kanban board

As a first step, you’ll see that you can change the card display for each work item type (WIT) that shows up on your Kanban board. 

<ol>
<li>From your Kanban board, open Settings (for on-premises TFS, choose Cards). <br/>  

	![Kanban board, open card customization](_img/kanban-card-customize-open-settings.png)<br/>

	If you're not a team admin, [get added as one](../scale/manage-team-assets.md#add-team-admin). Only team and project admins can customize cards. Learn more about accessing and using your Kanban board from [Kanban basics](../kanban/kanban-basics.md).<br/>
</li>
<li>Select the WIT you want to customize. Different WITs may present different options for customization.  <br/>

	Here we choose User Story. Your choices will vary based on the following:  <br/>
	<ul>
	<li>You connect to Visual Studio Online or an on-premises TFS</li>  
	<li>[Process](../guidance/choose-process.md) used to create your team project</li>  
	<li>Whether your team has chosen to [treat bugs like requirements or like tasks](show-bugs-on-backlog.md) </li> 
	</ul>
 <br/>
	**Card field options:** <br/>
	<table>
	<tbody valign="top">
	<tr>
	<th>Visual Studio Online options</th>
	<th>On-premises TFS options</th>
	</tr>
	<tr><td>Select core fields--ID, Assigned to, Estimate, Tags--to display on the card</td>  <td>Select core fields to display on the card</td> </tr>
	<tr>
	<td>Choose to show avatar, full name, or both for Assigned to field  </td>  <td>Choose to show avatar, full name, or both for Assigned to field</td> </tr>
	<tr><td>Add and reorder fields that display on the card</td> <td>Add fields that display on the card (To change the order, you have to start over) </td> </tr>
	<tr><td>Choose to show or hide fields that contain no data</td>  <td>n/a</td> </tr>
	</tbody>
	</table>
<br/>
**Visual Studio Online options:**  
![Kanban board,Visual Studio card customization dialog](_img/vso-kanban-card-customize.png)  

**On-premises TFS options:**   
![Kanban board, card customization dialog](_img/ALM_CC_KBCardOptions.png)
</li>
<li>Once you’ve clicked a WIT, select all the options that you want for that work item type.

	If you want work estimates to show, check the Show Effort, Story Points, Size, or Cost option. Cost corresponds to these fields: Effort ([Scrum](http://msdn.microsoft.com/library/ff731587%28v=vs.140%29.aspx)), Story Points ([Agile](http://msdn.microsoft.com/library/dd380647%28v=vs.140%29.aspx)), and Size ([CMMI](http://msdn.microsoft.com/library/dd997574%28v=vs.140%29.aspx)) field.
</li>
<li>To add a field to a card, click ![add icon](../_img/icons/add_icon.png) to select a field from the pick list. <br/>

![Kanban board, Add fields to a card](_img/customize-cards-add-fields.png)<br/>

To add a custom field, you must first [add it to the WIT definition](http://msdn.microsoft.com/library/dd695793%28v=vs.140%29.aspx). <br/>

Here we've added three fields:<br/>

![Kanban board, three fields added](_img/customize-cards-three-fields-added.png)  <br/>

You can edit a value in a field you add to a card, unless it's a read-only field, such as the Change By and Changed Date fields.  
</li>

</ol>

You can also customize the cards that appear on the Kanban board for features and epics. You follow similar steps, however you start from the [corresponding portfolio backlog](../backlogs/organize-backlog.md). 



<a id="task-board">  </a>
##Change how cards display on the task board
Scrum teams use the task board to burn down work and report on progress during daily standups. Your task board shows cards that correspond to both requirements and tasks. If you want bugs to appear on the task board, change your team settings for [show bugs on the backlogs and boards](http://msdn.microsoft.com/library/dn947440%28v=vs.140%29.aspx).

You change the way cards display on the task board the same way you change the Kanban cards display. Only here, you start from the task board.

1.	Open Settings from your task board (for on-premises TFS, choose Cards). .

	![Task board, open card customization dialog](_img/task-board-customize-open-settings.png)

	Remember, only [team or project administrators](../scale/manage-team-assets.md#add-team-admin) can customize the task board.  

2.	Just as before, choose the WIT you want to customize, and then checkmark or select the options you want.  

	**Visual Studio Online options:**  
	![Task board, card customization dialog](_img/vso-task-board-card-customize.png)

	**On-premises TFS options:**  
	![Task board, card customization dialog](_img/ALM_CC_TaskCardOptions.png)

3.	Repeat this step for each WIT you want to change. Don’t be surprised if the options change when you click on a different WIT. For example, Show Remaining Work only applies to tasks and perhaps bugs, but not to PBIs or requirements.  

4.	To add a field to a card, click the add field icon to select a field from the pick list. 

<a id="style-rule">  </a>
##Add style rules to highlight work items with color 

<blockquote style="font-size: 13px">**Note: ** *This feature is currently supported only on the Kanban and task boards for Visual Studio Online.*  </blockquote>  

1.	To cause a card on the Kanban board to change color based on criteria you specify, open Styles. Add a styling rule and set the criteria for the rule.  

	![Kanban board, Style dialog](_img/vso-card-styling.png)  

	Follow these rules when creating and ordering your style rules:
	- The criteria you specify works with [query operators and macros](https://msdnstage.redmond.corp.microsoft.com/en-us/library/dd286638%28v=vs.140%29.aspx) 
	- All clauses are considered AND clauses, grouping clauses isn't supported  
	- Card rules apply to all work items that meet the rule criteria  
	- Rule color applies to work items based on the order in which rules are listed. If you add more than one style rule, make sure that you move them in the order of most importance. Simply drag them into the order you want them applied.  
	- You can quickly enable and disable a style rule  
<br/>
2.	To highlight work items on the task board, open Styles from the task board Settings and add a styling rule.  
	Here we add a Stale tasks rule which highlights tasks that haven't changed in the last five days.

	![Task board, Style dialog, example style rule](_img/task-board-card-style-rule-stale-tasks.png)  

<a id="color-tags">  </a>
##Add color to your tags  

<blockquote style="font-size: 13px">**Note: ** *This feature is currently supported only on the Kanban board for Visual Studio Online.*  </blockquote>  

1.	Prior to setting tag colors, first [add tags to backlog items](https://msdn.microsoft.com/library/dn132606.aspx) that you want to highlight with color.   

2.	To add color to Kanban cards, open Tag colors and select a tag and the color you want it to display.  

	![Kanban board, tag colors](_img/kanban-card-customize-tag-colors.png)  
 
	If tags don't display on the cards, open Fields and make sure that you've checked Show Tags. 


##Related customization notes
That’s all there is to card customization. See these choices for further options to customize the Kanban and task board:

*	[Add, rename, move, and delete columns](../kanban/add-columns.md)  
*	[Split columns](../kanban/split-columns.md)  
*	[Expedite work](../kanban/expedite-work.md)  
*	[Add or modify area paths or iterations](modify-areas-iterations.md) 
*	[Show bugs on backlogs and boards](show-bugs-on-backlog.md) 

If you want to dig deep into other customization options, start with [Customize your work tracking experience](customize-work.md). 

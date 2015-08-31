Title: Expedite work | Visual Studio Online
Description: Add swimlanes to expedite and track work on the Kanban board
ms.TocTitle: Expedite work
ms.ContentId: 0BBD90C3-7156-4027-B100-9E46F5BD53FB

# Expedite work

Your Kanban board supports your ability to visualize the flow of work as it moves from new to done. When you add swimlanes, you can also visualize the status of work that supports different service-level classes. You can create a swimlane to represent any other dimension that supports your tracking needs.    

For example, you can create three swimlanes-Expedite, Standard, and Park-to track high-priority work, standard work, and work that's currently blocked.  

![Three swimlane Kanban board](_img/ALM_EW_IntroChart_3C.png)


## Types of swimlanes  
You can use swimlanes to sort work on your Kanban board to track items that you differentiate as follows: 
*	High priority items  
*	Service-level class  
*	Date-driven requirement  
*	Dependency for or from another team   
*	Blocked items  
*	Technical debt or other engineering work that's not a specific user story  


## Track work in swimlanes  
Once you've set up your swimlanes, you can drag items into a swimlane as well as reorder them within the lane.  

![Drag items into a swimlane](_img/ALM_EW_MoveToNewLane.png)   

You can also focus on a single swimlane by collapsing all other lanes.

![Collapsed swimlanes](_img/ALM_EW_CollapseLanes.png)    

## Configure swimlanes 
So, what swimlanes will support your tracking needs?  

Once you've identified one or two, add them to your working Kanban board.  

1. From your Kanban board, click ![settings icon](../_img/icons/gear_icon.png) and as needed, click Swimlanes.  

	![Kanban board, open settings ](../customize/_img/kanban-card-customize-open-settings.png) 

	If you're not a team admin, [get added as one](../scale/manage-team-assets.md#add-team-admin). Only team and project admins can customize the Kanban board.

2.	Click ![add icon](../_img/icons/add_icon.png) and enter the name of the swimlane you want to add.  
	
	**Visual Studio Online:**  
	![Kanban board, Add a swimlane](_img/kanban-board-add-swimlane.png)  

	The default lane appears unlabeled on the Kanban board. You can rename it to anything you like, however, you can't delete it. 

	**On-premises TFS:**   
	![Add a swimlane](_img/ALM_SW.AddLane.png)  

	The default lane is automatically renamed to Standard when you add a second lane. You can rename it to anything you like, however, you can't delete it. 

3.	To reorder your swimlanes, simply grab the lane and move it up or down.

	![Open swimlanes](_img/ALM_EW_ReorderLanes.png)  

4.	If you need to delete a lane, first move all items out of the lane, and then click Delete from the lane's context menu.  

	![Delete a swimlane](_img/ALM_EW_DeleteLane.png)  

## Related Kanban notes

As you can see, swimlanes provides another way to organize and visualize the flow of work using [Kanban](kanban-basics.md). Here are a few more options you have for customizing the look and feel of your Kanban board.   

*	[Add columns](add-columns.md)  
*	[Work in Progress limits](wip-limits.md)   
*	[Split columns](split-columns.md)   
*	[Definition of Done](definition-of-done.md)   
*	[Customize cards](../customize/customize-cards.md)   
*	[Show bugs on backlogs and boards](../customize/show-bugs-on-backlog.md)   
### Tracking lane moves  
Similar to the way [column moves are tracked](add-columns.md), swimlane moves are captured in the history field.  

![History of a swimlane move](_img/ALM_EW_HistorySwimLanes.png)   

Can you [query](../track/using-queries.md) for all items in a particular swimlane? Not at this time. 
To perform a query, you'd have to assign a value to a field, such as the Priority field, 
or [tag](http://msdn.microsoft.com/library/dn132606.aspx) each item in a similar way.  



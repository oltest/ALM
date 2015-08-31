Title: Add tags to work items | Visual Studio Online | TFS
Description: Add tags to work items to categorize and filter lists when working in  Visual Studio Online and Team Foundation Server
ms.TocTitle: Add tags to work items
ms.ContentId: 79A08F31-BB8A-48BD-AD17-477EE0B76BC7

#Add tags to work items to categorize and filter lists  

Tagging work items helps you quickly filter the product backlog or a work item query by categories that you define.  

You can add and modify tags in Visual Studio Online, the web portal for Team Foundation Server (TSF), and the Team Explorer plug-in for Visual Studio. Also, you can open a query in Excel or Project to perform bulk modifications of tags.  

From the Team Explorer plug-in for Eclipse, you can filter queries by tags, however, you can’t add or modify tags from the user interface. You must use the web portal to add and modify tags.  

By default, all Contributors are granted permissions to create and modify tags.  

##Add tags and assign tags to work items  

1. From the web portal, open a work item and add a tag. Or, select from the list of previously assigned tags.  

	![Add one or more tags to a work item](_img/add-tags-to-work-items-vso-tfs.png)  

2. To add several tags at one time, type a comma between tags. Tags are case sensitive.  

	Tags that appear in the tag bar are already assigned to the work item. To unassign a tag, simply choose the x on the tag,![Delete a tag assigned to a work item](_img/unassign-a-tag.png).   

##Show tags in your backlog or query results  

1. Open Column Options to add the Tags field to the product backlog or a work item query.  

	![Add Tags to the selected columns to display](_img/add-tags-to-query-results.png)

2. All tags that are assigned to the listed work items appear.

	![View with Tags column added](_img/query-results-with-tags-listed.png)  

##Filter a list of work items  

1. Turn on filtering and choose a tag.  

	![Choose a tag to filter the list by that tag](_img/filter-a-list-using-tags.png)  

	The list refreshes. Only those work items with the selected tag are displayed. Filtering the list disables add-a-backlog-item panel, stack ranking, and forecasting.  

	![Filtered list disables other features](_img/filtered-list-based-on-tags.png)  

2. To apply a sub-filter, choose another tag. You filter successively by choosing from the set of tags that appear in the filter tag bar. To start your filter process over, choose All to show all tags.  

3. To show all items, choose All or choose the Tag filter image on backlog and queries pages filter icon to turn filtering off.   

##Related notes

Tags are a shared resource, they're associated with a team project and not a team. If your team project contains multiple teams, all teams will add to and work from the same set of tags. 
- [Using queries](using-queries.md) 
- [Show tags on cards](../customize/customize-cards.md)

###Limits on number of tags
While no hard limit exists, creating more than 100K tags for a team project collection can negatively impact performance. Also, the auto-complete dropdown menu for the tag control displays a maximum of 200 tags. When more than 200 tags are defined, begin typing to cause the tag control to display relevant tags.  

You can’t assign more than 256 tags to a work item. And, you can’t add more than 32 new tags within a single revision to a work item.  

Limit queries to fewer than 25 tags. More than that and the query will likely time out.  

###Delete or remove tags 

You can’t delete a tag itself. However, if you delete a tag from all work items to which it’s currently assigned, the system will delete the tag. The system automatically deletes unassigned tags after 3 days of disuse.  

If you misspell a tag, don't assign the misspelled tag to any work item and the system will automatically delete it within 3 days.  

###Add tags to the default column view on the product backlog 

Modify the ProcessConfiguration file to include ```System.Tags``` in the set of fields to display. See Process configuration XML element reference.

###Add or modify tags using an API 
You can use ```WorkItem.Fields``` or Work Item Field Explorer (provided with [Team Foundation Server Power Tools](http://go.microsoft.com/fwlink/?LinkId=320602)) to determine if the Tags field is editable (IsEditable).
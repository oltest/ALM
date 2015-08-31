Title: Dashboards | Visual Studio Online and TFS
Description: View progress and gain quick access to code, builds, and work items from the team home page in Visual Studio Online and team projects connected to Team Foundation Server (TFS)
ms.TocTitle: Dashboards
ms.ContentId: B080CEFA-4D94-44B2-99E3-0E3E85616D04


#Dashboards

Teams can view the progress of work from the team home page. Team administrators can add or pin items to this dashboard and re-sequence tiles. Each tile provides team members quick access to the progress of builds, status of work items, or version control paths defined in Team Foundation Server (TFS).


If you need to add a team first, go [here](../Work/scale/multiple-teams.md). 


From Visual Studio Online or the web portal, you can view pinned items on the home page, including flat-list query charts. 


![Pinned items on the team home page](_img/on-premises-tfs-team-dashboard.png)

##To pin items to the team dashboard 

You pin an item to the team dashboard from the code, work, and build pages. 

1.	If you aren’t a team administrator, [get added as one](../Work/scale/manage-team-assets.md#add-team-admin).  

2.	Pin a work item query from its context menu.  

	![Pin a query to the team homepage](_img/tfs-pin-to-homepage.png)  

	To add a source control folder or a build definition, open the corresponding page and access the pin feature in the same way.   

	To pin a chart, go to the query’s Charts page and pin it to the home page.  

	![Chart context menu]( _img/tfs-pin-chart-to-team-homepage-dashboard.png)  

3.	Drag tiles to reorder their sequence on the dashboard.   

	Using Internet Explorer 10 or Internet Explorer 11, you can also tab to a tile and press Shift+L or Shift+R to move the selected tile to the left or to the right.  

4.	Choose a tile to open it.  


##Q: &amp; A

<!-- BEGINSECTION class="md-qanda" -->


###Q: How do I remove a pinned item from the home page?

**A: **Go to the Queries page. Either choose the context menu for the query that you want to remove and select Unpin from the home page, or drag it from the Team favorites section. You have to be a [team administrator](../Work/scale/manage-team-assets.md#add-team-admin) or belong to the Project Administrators group to perform these steps. 

###Q: How do I add team members or team administrators?

**A: **Go [here](../Work/scale/multiple-teams.md#add-team-members) to add team members. Go [here](../Work/scale/manage-team-assets.md#add-team-admin) To add an account as a team administrator. 

###Q: How do I create a team home page? 
**A: **You don’t have to do any work to add a home page. A team home page is created when you [add a team](../Work/scale/multiple-teams.md). You access it through the following URL:  
```http://ServerName:8080/tfs/CollectionName/TeamProjectName/TeamName``` 

###Q: How do I create a work item query?  

**A: **See [Query for work items](../Work/track/using-queries.md). 

###Q: How do I define builds?   
**A: **See [Build](../Build/overview.md). 

###Q: How do I set team alerts?  
**A: **See [Set team alerts](../Work/track/alerts-and-notifications.md). 

<!-- ENDSECTION -->

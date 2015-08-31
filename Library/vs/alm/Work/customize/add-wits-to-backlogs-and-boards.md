Title: Add work item types to backlogs and boards | Team Foundation Server
Description: Add work item types to product backlogs and boards when working with team projects that connect to Team Foundation Server
ms.TocTitle: Add work item types to backlogs and boards 
ms.ContentId: f3e42cd4-912b-4fff-a6f2-cf584edc782a

#Add work item types to backlogs and boards

To satisfy other business processes, your team may want to track additional work item types (WITs) as requirements or as tasks. This way, you can add them and track them within the product and sprint backlogs or Kanban and task boards. 

For example, you may want to track different types of requirements based on their target customer, or different types of bugs based on their source. Here the Fabrikam Fiber team has added the Service App WIT to track work that supports their customer service team.   

![Add a custom WIT, e.g., Service App, to the Requirement Category to track it like a requirement](_img/ALM_AWB_Intro.png)

<blockquote style="font-size: 13px">**Tip:  **If all you want to do is add bugs to your backlogs and boards, go [here](show-bugs-on-backlog.md) to make your team's selection. If you want to add another WIT and portfolio backlog, go [here](add-portfolio-backlogs.md).
</blockquote>  

To add a WIT to track as requirements, tasks, or as bugs perform the corresponding steps:  
- [Add a WIT to track as requirements](#wit-as-requirements)
- [Add a WIT to track as tasks](#wit-as-tasks)
- [Add a WIT to the Bug Category](#wit-as-bugs)

<blockquote style="font-size: 13px">**Note: **We recommend that you add a WIT to one and only one of the following categories: Requirement Category, Task Category, or Bug Category.    
The system prevents you from adding the same WIT to both the Requirement Category and Task Category. WITs that you add to the Bug Category will follow the [bug behavior set for the team](show-bugs-on-backlog.md).  </blockquote>  



<a id="first-steps">  </a>
##First steps

###Visual Studio Online
You'll make your changes to your process definition files, and then import that process to either update existing team projects or use the process to create a team project. 

- If you aren't the account owner or a member of the Project Collection Administrator's group, [get added](https://msdn.microsoft.com/library/dd547204.aspx). 
- [Export the process you want to update](../import-process/import-process.md) 
-  If you're new to customizing a process, familiarize yourself with the following resources:
	- [Customize a process for import into Visual Studio Online](../import-process/customize-process.md)



###On-premises TFS  
You'll first export your work tracking definition files, update them, and then import them to your team project.  
-  If you aren't a member of the Project Administrator or Project Collection Administrator's group, [get added](https://msdn.microsoft.com/library/dd547204.aspx). 
-  Update your team project to [enable the latest features](configure-features-after-upgrade.md)
-  [Export the following objects from your team project](#import-export): 
	- WIT you want to add to backlogs and boards (if you haven't created it, [do that now](https://msdn.microsoft.com/library/ms404855.aspx))
	- Categories definition  
	- ProcessConfiguration  
-  If you're new to customizing work tracking objects, familiarize yourself with the following resources:
	- [Modify or add a field](http://msdn.microsoft.com/library/dd695793%28v=vs.140%29.aspx)
	- [Modify or add a WIT](http://msdn.microsoft.com/library/hh409273%28v=vs.140%29.aspx)
	- [ProcessConfiguration XML reference](https://msdn.microsoft.com/library/hh500408.aspx)




<a id="wits-as-requirements">  </a>
##Add a WIT to track it like a requirement   

WITs that you add to the Requirement Category show up on the product backlog and Kanban board. You must make sure that the WIT definition contains required fields to support the Agile planning tools.  


1.	Export your process (Visual Studio Online) or your definition files (on-premises TFS) as indicated in [First steps](#first-steps).
2.	Edit the WIT definition to support planning tools. 
	<table>
	<tbody valign="top">
	<tr>
	<th>Customize</th>
	<th>Syntax to add or update</th>
	</tr>
	<tr>
	<td>
	Backlog priority field (Agile, CMMI)
	</td>
	<td>
	```<FIELD name="Stack Rank" refname="Microsoft.VSTS.Common.StackRank" type="Double" reportable="dimension">  ```  
	&nbsp;&nbsp;&nbsp;```<HELPTEXT>Work first on items with lower-valued stack rank. Set in triage.</HELPTEXT>  ```  
	```</FIELD>  ```  
	
	</td>
	</tr>
	<tr>
	<td>
	Stack rank field (Scrum)
	</td>
	<td>
	```<FIELD name="Backlog Priority" refname="Microsoft.VSTS.Common.BacklogPriority" type="Double" reportable="detail" />```
	</td>
	</tr>
	<tr>
	<td>
	Value Area field  
	</td>
	<td>
	```<FIELD name="Value Area" refname="Microsoft.VSTS.Common.ValueArea" type="String">  ```  
	&nbsp;&nbsp;&nbsp;```<REQUIRED />  ```  
	&nbsp;&nbsp;&nbsp;```<ALLOWEDVALUES>  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Architectural" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Business" />  ```  
	&nbsp;&nbsp;&nbsp;```</ALLOWEDVALUES>  ```  
	&nbsp;&nbsp;&nbsp;```<DEFAULT from="value" value="Business" />  ```  
	&nbsp;&nbsp;&nbsp;```<HELPTEXT>Business = delivers value to a user or another system; Architectural = work to support other stories or components</HELPTEXT>  ```  
	```</FIELD>  ```  
	</td>
	</tr>
	<tr>
	<td>
	Requirement Type field (CMMI)
	</td>
	<td>
	```<FIELD name="Requirement Type" refname="Microsoft.VSTS.CMMI.RequirementType" type="String" reportable="dimension">  ```  
	&nbsp;&nbsp;&nbsp;```<REQUIRED />  ```  
	&nbsp;&nbsp;&nbsp;```<ALLOWEDVALUES>  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Scenario" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Quality of Service" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Functional" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Operational" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Interface" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Security" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Safety" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Business Objective" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Feature" />  ```  
	&nbsp;&nbsp;&nbsp;```</ALLOWEDVALUES>  ```  
	&nbsp;&nbsp;&nbsp;```<DEFAULT from="value" value="Functional" />  ```  
	```</FIELD>  ```  
	</td>
	</tr>
	<tr>
	<td>
	```WORKFLOW``` section
	</td>
	<td>
	<p>Update or verify the ```WORKFLOW``` section as follows: </p>
	<ul>
	<li>Agile, User Story: Add transitions from ```Active``` to ```Removed``` and ```Resolved``` to ```Removed```; remove rules that populate  ```Activated By``` and ```Activated Date``` fields when state=```Resolved```  </li>
	<li>Scrum, Product backlog item: Add transition from ```Committed``` to ```Removed``` </li>
	</ul>
	<p>If you've customized the ```WORKFLOW```, make sure to define the required state-to-metastate mappings in the [ProcessConfiguration ```RequirementBacklog``` section](#edit-processconfig). </p>
	</td>
	</tr>
	<tr>
	<td>
	```FORM``` section
	</td>
	<td>
	<p>Add or verify the following fields have been added to the ```FORM``` section: </p>
	<ul>
	<li><p>Agile:</p>
	```<Control FieldName="Microsoft.VSTS.Scheduling.StoryPoints" Type="FieldControl" Label="Story Points" LabelPosition="Left" />```  
	```<Control FieldName="Microsoft.VSTS.Common.ValueArea" Type="FieldControl" Label="Value area" LabelPosition="Left" />```  
	</li>
		<li><p>CMMI:</p>
	```<Control Type="FieldControl" FieldName="Microsoft.VSTS.Scheduling.Size" Label="Size" LabelPosition="Left" />```  
	```<Control Type="FieldControl" FieldName="Microsoft.VSTS.CMMI.RequirementType" Label="Type" LabelPosition="Left" />```  
	```<Control FieldName="Microsoft.VSTS.Common.ValueArea" Type="FieldControl" Label="Value area" LabelPosition="Left" />```  
	</li>
		<li><p>Scrum:</p>
	```<Control FieldName="Microsoft.VSTS.Scheduling.Effort" Type="FieldControl" Label="Effort" LabelPosition="Left" />```  
	```<Control FieldName="Microsoft.VSTS.Common.ValueArea" Type="FieldControl" Label="Value area" LabelPosition="Left" />```  
	</li>
	</ul>
	</td>
	</tr>
	</tbody>
	</table>  

4.	Edit the Categories definition. Add the WIT to the Requirement category. Here we add Service App.  

	```
	 <CATEGORY name="Requirement Category" refname="Microsoft.RequirementCategory">
	    <DEFAULTWORKITEMTYPE name="User Story" />
	    <WORKITEMTYPE name="Service App" />
	 </CATEGORY>
	```

4.	Update or verify ProcessConfiguration definition: ```RequirementBacklog``` section for the WIT you're adding. Specifically, make sure that the following conditions are met:
	<ul>
	<li>Map the start of each workflow state to ```type="Proposed"``` </li>
	<li>Map each intermediate workflow state you want to have show up on the Kanban board to ```type="InProgress"``` </li>
	<li>Map the end of each workflow state to ```type="Complete"``` </li>
	<li>Make sure that you have only one State mapped to ```type="Complete"```</li>
	</ul>
	For example, add the Pending workflow state:
	```
	    <States>
	      <State value="New" type="Proposed" />
	      <State value="Active" type="InProgress" />
	      <State value="Pending" type="InProgress" />
	      <State value="Resolved" type="InProgress" />
	      <State value="Closed" type="Complete" />
	    </States>
	```
5.	Add the WIT color definition to the ProcessConfiguration ```WorkItemColors``` section. For example:  
	```<WorkItemColor primary="FF33CC33" secondary="FFD6F5D6" name="Service App" />```  

6.	Update your team project:  
	- **Visual Studio Online: **[Import your process](../import-process/import-process.md).  
	- **On-premises TFS: **[Import the definition files you updated](#import-export) in this order:  
		a. WIT 
		b. Categories  
		c. ProcessConfiguration  




<a id="wits-as-tasks">  </a>
##Add a WIT to track it like a task   

WITs that you add to the Task Category show up on the sprint backlogs and task boards. The WIT you add must specify required fields to support the Agile planning tools.  

1.	Export your process (Visual Studio Online) or your definition files (on-premises TFS) as indicated in [First steps](#first-steps).
2.	Edit the WIT definition to support planning tools. 
	<table>
	<tbody valign="top">
	<tr>
	<th>Customize</th>
	<th>Syntax to add or update</th>
	</tr>
	<tr>
	<td>
	Backlog priority field (Agile, CMMI)
	</td>
	<td>
	```<FIELD name="Stack Rank" refname="Microsoft.VSTS.Common.StackRank" type="Double" reportable="dimension">  ```  
	&nbsp;&nbsp;&nbsp;```<HELPTEXT>Work first on items with lower-valued stack rank. Set in triage.</HELPTEXT>  ```  
	```</FIELD>  ```  
	
	</td>
	</tr>
	<tr>
	<td>
	Stack rank field (Scrum)
	</td>
	<td>
	```<FIELD name="Backlog Priority" refname="Microsoft.VSTS.Common.BacklogPriority" type="Double" reportable="detail" />```
	</td>
	</tr>
	<tr>
	<td>
	Activity field (Agile, Scrum)
	</td>
	<td>
	```<FIELD name="Backlog Priority" refname="Microsoft.VSTS.Common.BacklogPriority" type="Double" reportable="detail" />```
	</td>
	</tr>
	<tr>
	<td>
	Discipline field (CMMI)
	</td>
	<td>
	```<FIELD name="Discipline" refname="Microsoft.VSTS.Common.Discipline" type="String" reportable="dimension">  ```  
	&nbsp;&nbsp;&nbsp;```<ALLOWEDVALUES>  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Analysis" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="User Experience" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="User Education" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Development" />  ```  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```<LISTITEM value="Test" />  ```  
	&nbsp;&nbsp;&nbsp;```</ALLOWEDVALUES>  ```  
	&nbsp;&nbsp;&nbsp;```<HELPTEXT>The discipline to which the task belongs</HELPTEXT>  ```  
	```</FIELD>  ```  
	</td>
	</tr>
	<tr>
	<td>
	Remaining Work field (all) 
	</td>
	<td>
	```<FIELD name="Remaining Work" refname="Microsoft.VSTS.Scheduling.RemainingWork" type="Double" reportable="measure" formula="sum">  ```  
	&nbsp;&nbsp;&nbsp;```<HELPTEXT>An estimate of the work remaining to complete the task (in person hours)</HELPTEXT>  ```  
	&nbsp;&nbsp;&nbsp;```<HELPTEXT>The discipline to which the task belongs</HELPTEXT>  ```  
	```</FIELD>  ```  
	</td>
	</tr>
	<tr>
	<tr>
	<td>
	Additional scheduling fields (Agile, CMMI)
	</td>
	<td>
	```<FIELD name="Original Estimate" refname="Microsoft.VSTS.Scheduling.OriginalEstimate" type="Double" reportable="measure" formula="sum">  ```  
	&nbsp;&nbsp;&nbsp;```<HELPTEXT>The original estimate of work required to complete the task (in person hours)</HELPTEXT>  ```  
	```</FIELD>  ```  
	```<FIELD name="Remaining Work" refname="Microsoft.VSTS.Scheduling.RemainingWork" type="Double" reportable="measure" formula="sum">  ```  
	&nbsp;&nbsp;&nbsp;```<HELPTEXT>An estimate of the work remaining to complete the task (in person hours)</HELPTEXT>  ```  
	```</FIELD>  ```  
	```<FIELD name="Completed Work" refname="Microsoft.VSTS.Scheduling.CompletedWork" type="Double" reportable="measure" formula="sum">  ```  
	&nbsp;&nbsp;&nbsp;```<HELPTEXT>The work that has been completed for this task (in person hours)</HELPTEXT>  ```  
	```</FIELD>  ```  
	```<FIELD name="Start Date" refname="Microsoft.VSTS.Scheduling.StartDate" type="DateTime" reportable="dimension" />  ```  
	```<FIELD name="Finish Date" refname="Microsoft.VSTS.Scheduling.FinishDate" type="DateTime" reportable="dimension" />  ```  
	</td>
	</tr>
	<td>
	```WORKFLOW``` section
	</td>
	<td>
	<p>Update or verify the ```WORKFLOW``` section as follows: </p>
	<ul>
	<li>Agile, User Story: Add transitions from ```Active``` to ```Removed``` and ```Resolved``` to ```Removed```; remove rules that populate  ```Activated By``` and ```Activated Date``` fields when state=```Resolved```  </li>
	<li>Scrum, Product backlog item: Add transition from ```Committed``` to ```Removed``` </li>
	</ul>
	<p>If you've customized the ```WORKFLOW```, make sure to define the required state-to-metastate mappings in the [ProcessConfiguration ```TaskBacklog``` section](#edit-processconfig). </p>
	</td>
	</tr>
	<tr>
	<td>
	```FORM``` section
	</td>
	<td>
	<p>Add or verify the following fields have been added to the ```FORM``` section: </p>
	<ul>
	<li><p>Agile:</p>
	```<Control FieldName="Microsoft.VSTS.Scheduling.StoryPoints" Type="FieldControl" Label="Story Points" LabelPosition="Left" />```  
	```<Control FieldName="Microsoft.VSTS.Common.ValueArea" Type="FieldControl" Label="Value area" LabelPosition="Left" />```  
	</li>
		<li><p>CMMI:</p>
	```<Control Type="FieldControl" FieldName="Microsoft.VSTS.Scheduling.Size" Label="Size" LabelPosition="Left" />```  
	```<Control FieldName="Microsoft.VSTS.Common.ValueArea" Type="FieldControl" Label="Value area" LabelPosition="Left" />```  
	</li>
		<li><p>Scrum:</p>
	```<Control FieldName="Microsoft.VSTS.Scheduling.Effort" Type="FieldControl" Label="Effort" LabelPosition="Left" />```  
	```<Control FieldName="Microsoft.VSTS.Common.ValueArea" Type="FieldControl" Label="Value area" LabelPosition="Left" />```  
	</li>
	</ul>
	</td>
	</tr>
	</tbody>
	</table>  

4.	Edit the Categories definition. Add the WIT to the Task category. Here we add Service Task.  

	```
	 <CATEGORY name="Task Category" refname="Microsoft.TaskCategory">
	    <DEFAULTWORKITEMTYPE name="Task" />
	    <WORKITEMTYPE name="Service Task" />
	 </CATEGORY>
	```

4.	Update or verify ProcessConfiguration definition: ```TaskBacklog``` section for the WIT you're adding.  

	Specifically, make sure that the following conditions are met:
	<ul>
	<li>Map the start of each workflow state to ```type="Proposed"``` </li>
	<li>Map each intermediate workflow state you want to have show up on the task board to ```type="InProgress"``` </li>
	<li>Map the end of each workflow state to ```type="Complete"``` </li>
	<li>Make sure that you have only one State mapped to ```type="Complete"```</li>
	</ul>
	For example, add the Blocked workflow state:
	```
	    <States>
	      <State value="New" type="Proposed" />
	      <State value="Active" type="InProgress" />
	      <State value="Blocked" type="InProgress" />
	      <State value="Resolved" type="InProgress" />
	      <State value="Closed" type="Complete" />
	    </States>
	```
5.	Add the WIT color definition to the ProcessConfiguration ```WorkItemColors``` section. For example:  
	```<WorkItemColor primary="FFF2CB1D" secondary="FFF6F5D2" name="Service Task" />```

6.	Update your team project:  
	- **Visual Studio Online: **[Import your process](../import-process/import-process.md).  
	- **On-premises TFS: **[Import the definition files you updated](#import-export) in this order:  
		a. WIT  
		b. Categories   
		c. ProcessConfiguration  

5. Confirm that you can add the WIT to the task board. Open the task board page, or refresh the page if it’s already open.  
	You should be able to select either Task or Service Task as a linked work item to a user story.  
	![Task board with Service Task work item type added](_img/ALM_AWB_AddTaskConfirm.png)  

	On the task board, drag the work item to update its status. You’ll notice that you can’t drag an item to a column for which the state isn’t valid. For example, you can’t drag Task to the Blocked state, or a Task into a resolved state. If you want to use these states, then add them to the workflow definition for the corresponding WIT definition. 


<a id="wits-as-bugs">  </a>
##Add a WIT to the Bug Category  

WITs that you add to the Bug Category will be treated based on the [team setting](show-bugs-on-backlog.md). Because these WITs may be treated either as requirements or tasks, they must meet Agile planning tool requirements for both requirements and tasks.  
1.	Export your process (Visual Studio Online) or your definition files (on-premises TFS) as indicated in [First steps](#first-steps).
2.	Edit the WIT definition to support planning tools by meeting the conditions listed for Step 2 of [Add a WIT to track as requirements](#wit-as-requirements) and [Add a WIT to track as tasks](#wit-as-tasks).  

3.	Edit the Categories definition. Add the WIT to the Bug Category. Here we add two WITs.  

	```
	 <CATEGORY name="Bug Category" refname="Microsoft.BugCategory">
	    <DEFAULTWORKITEMTYPE name="Bug" />
	    <WORKITEMTYPE name="Service Bug" />
	    <WORKITEMTYPE name="Feedback" />
	 </CATEGORY>
	```

4.	Update or verify ProcessConfiguration definition: ```BugWorkItems``` section for the WIT you're adding.  

	Specifically, make sure that the following conditions are met:
	<ul>
	<li>Map the start of each workflow state to ```type="Proposed"``` </li>
	<li>Map each intermediate workflow state you want to have show up on the Kanban or task board to ```type="InProgress"``` </li>
	<li>Map the end of each workflow state to ```type="Complete"``` </li>
	<li>Make sure that you have only one State mapped to ```type="Complete"```</li>
	</ul>
	For example, add the Investigate workflow state:
	```
	    <States>
	      <State value="New" type="Proposed" />
	      <State value="Active" type="InProgress" />
	      <State value="Investigate" type="InProgress" />
	      <State value="Resolved" type="InProgress" />
	      <State value="Closed" type="Complete" />
	    </States>
	```
5.	Add the WIT color definition to the ProcessConfiguration ```WorkItemColors``` section. For example:  
	```<WorkItemColor primary="FFF2CB1D" secondary="FFF6F5D2" name="Service Bug" />```
	```<WorkItemColor primary="FFFF00FF" secondary="FFFFCCFF" name="Feedback" />```

6.	Update your team project:  
	- **Visual Studio Online: **[Import your process](../import-process/import-process.md).  
	- **On-premises TFS: **[Import the definition files you updated](#import-export) in this order:  
		a. WIT  
		b. Categories   
		c. ProcessConfiguration  
7.	[Choose your team setting](show-bugs-on-backlog.md).  

8. Confirm that the WIT appears on the backlogs and boards as expected and that you can add it through the backlogs as expected.  


<a id="import-export">  </a>
##Import and export definition files (on-premises TFS only) 
If you're updating a team project that connects to an on-premises TFS, you'll use the witadmin commands to import and export definition files.  

<blockquote style="font-size: 13px">**Tip:  **You can also use the Process Editor, available with the download of TFS Power Tools, to import, edit, and export definition files. </blockquote>  

1. Open a Command Prompt window where either Visual Studio or Team Explorer is installed and enter:  

	```cd %programfiles(x86)%\Microsoft Visual Studio 14.0\Common7\IDE```  

	On a 32-bit edition of Windows, replace ```%programfiles(x86)%``` with ```%programfiles%```. 

	The version of Visual Studio or Team Explorer must be at the same version as the on-premises TFS. 

2.	Enter the ```witadmin``` command, substituting your data for the arguments that are shown. For example, to import a WIT:   

	```witadmin importwitd /collection:CollectionURL /p:"ProjectName" /f:"DirectoryPath\WITDefinitionFile.xml"```

		For *CollectionURL* specify the URL of a team project collection and for *ProjectName* specify the name of a team project defined within the collection. You must specify the URL in the following format: ```http://ServerName:Port/VirtualDirectoryName/CollectionName```.  

		For *DirectoryPath*, specify the path to the ```WorkItem Tracking/TypeDefinitions``` folder that holds the process template that you downloaded. The directory path must follow this structure: ```Drive:\TemplateFolder\WorkItem Tracking\TypeDefinitions```.

	For  example,  import the ServiceApp WIT:

	```witadmin importwitd /collection:"http://MyServer:8080/tfs/DefaultCollection"/p:MyProject /f:"DirectoryPath/ServiceApp.xml"``` 

Use these commands to export and import categories and process configuration: 

	witadmin exportwitd /collection:CollectionURL /p:"ProjectName" /n:TypeName /f:"DirectoryPath\WITDefinitionFile.xml"

	witadmin importwitd /collection:CollectionURL /p:"ProjectName" /f:"DirectoryPath\WITDefinitionFile.xml"

	witadmin exportcategories /collection:"CollectionURL" /p:"ProjectName" /f:"DirectoryPath/categories.xml"

	witadmin importcategories /collection:"CollectionURL" /p:"ProjectName" /f:"DirectoryPath/categories.xml"

	witadmin exportprocessconfig /collection:"CollectionURL" /p:"ProjectName" /f:"DirectoryPath/ProcessConfiguration.xml"

	witadmin importprocessconfig /collection:"CollectionURL" /p:"ProjectName" /f:"DirectoryPath/ProcessConfiguration.xml"


##Related customization notes  
We've just shown how to add another WIT to your backlogs or boards. However, if you want to add another WIT to act as a portfolio backlog, see [Add portfolio backlogs](add-portfolio-backlogs.md)


See [Customize your work tracking experience](customize-work.md) for an overview of all the options available for customizing work tracking objects. 


Depending on whether you're working in the cloud or on-premises, you can learn more about 
how to manage your process or process template from these articles.    
<table valign="top" width="60%">
<tbody width="60%">
<tr valign="top">
<td width="50%">
<p><b>Visual Studio Online</b></p>
</td>
<td width="50%">
<p><b>On-premises TFS</b></p>
</td>
</tr>
<tr valign="top">
<td>
[Create a team project](http://www.visualstudio.com/get-started/set-up-vs)
</td>
<td>
[Create a team project](http://msdn.microsoft.com/library/ms181477%28v=vs.140%29.aspx)
</td>
</tr>
<tr valign="top">
<td>
[Add or update a process](../import-process/import-process.md)
</td>
<td>
[Upload or download a process template](../guidance/manage-process-templates.md)
</td>
</tr>
    <tr valign="top">
<td>
[Customize a process](../import-process/customize-process.md)
</td>
<td>
[Customize a process template](http://msdn.microsoft.com/library/ms243782%28v=vs.140%29.aspx)
</td>
</tr>
<tr>
<td>
N/A
</td>
<td>
[Configure an existing team project with new features](configure-features-after-upgrade.md)
</td>
</tr>
           
</tbody>
</table>



##Q & A
<!-- BEGINSECTION class="md-qanda" -->

###Q: Why aren’t all bugs displaying on the product backlog?
 
**A: **The In progress items filter causes some backlog items to display or not display. Bugs and other backlog items aren’t listed when In progress items=Hide and their assigned State corresponds to In Progress metastate. Bugs in a New state will display, however, bugs in an Assigned state won’t. 

Set ```In progress items=Show``` to see all active bugs and other items on your backlog.

###Q: Why don’t all the bugs and tasks I’ve assigned to a sprint appear on the sprint backlog?
 
**A: **It’s possible to assign tasks to an iteration but not have them linked to a parent backlog item. These items will show up in the created query, but may not show up on the task board itself. TFS runs the query and then applies a few background processes before displaying the task board items.

Task which aren't linked to a parent backlog item appear in the Unparented row on the task board.  

These two reasons can cause work items that belong to the Task Category to not appear on a sprint backlog or task board:  
	
* The task is a parent of another task. If you’ve created a hierarchy of tasks, only the child-level tasks at the bottom of the hierarchy appear.  
* The task’s linked parent corresponds to a backlog item defined for another team. Or, the area path of the task’s parent backlog item differs from the task’s area path.  
 

###Q: How are hierarchical items displayed on the backlogs and boards?
 
**A: **While you can create a hierarchy of backlog items, tasks, and bugs─we don’t recommend that you do. The Kanban board, sprint backlog, and task board only show the last node within a hierarchy, called the leaf node. For example, if you link items within a hierarchy that is four levels deep, only the items at the fourth level appear on the Kanban board, sprint backlogs, and task boards. 

Instead of nesting requirements, bugs, and tasks within themselves, we recommend that you use different WITs to group items within a hierarchy and maintain a flat list across the same WITs. 

Use Features to group PBIs, user stories, or requirements. You can [quickly map stories to features](../backlogs/organize-backlog.md), which creates parent-child links in the background.  

![Create wits using different hiearchy](_img/create-hierarchy-with-different-wits.png)

For examples of how hierarchically linked items that belong to the Requirements Category appear on the backlogs and boards, go [here](show-bugs-on-backlog.md#leaf-nodes). 

###Q: How are the Backlog Priority or Stack Rank fields used?

**A: **The backlog and board pages use the ```Backlog Priority``` (Scrum) and ```Stack Rank``` (Agile and CMMI) fields to manage the priority or order of work items on the backlog. These fields should be defined for all WITs for a team project. However, you don’t need to include them on the work item form. These fields must match the field assigned to the ```Order``` type in the ProcessConfiguration definition file. 

<!-- ENDSECTION -->



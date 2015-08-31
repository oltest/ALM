Title: New features added when you update TFS | Team Foundation Server
Description: Topic description - Team Foundation Server
ms.TocTitle: New features added when you update TFS
ms.ContentId: 1A7B7A18-457F-4AFF-9151-FCF13B850907


*This topic applies only to team projects hosted on an on-premises Team Foundation Server (TFS). Team projects on Visual Studio Online [update automatically with each service upgrade](https://www.visualstudio.com/news/release-archive-vso).  * 

<!---
Supports the following FWLINK: Learn more about these configuration changes: http://go.microsoft.com/fwlink/?LinkID=242985 - 

-->
#New features added through feature enablement 

The Configure Features Wizard detects which features have and haven't been configured. Most new features include additions or changes to work item types (WITs), categories, or process configuration. New features are introduced with different updates to Team Foundation Server (TFS). 


<table>
<tbody valign="top">
<tr>
<th width="18%">
Feature
</th>
<th width="70%">
Changes
</th>
<th width="12%">
Update
</th>
</tr>
<tr>
<td>
Code Review
</td>
<td>
Adds the Code Review Request and Code Review Response WITs and categories to the team project. These items support [code review requests and responses from the My Work page in Team Explorer](https://www.visualstudio.com/get-started/code/get-code-reviewed-vs). My Work only appears when you have Visual Studio Premium or Visual Studio Ultimate installed.<br /> 
Go [here](https://msdn.microsoft.com/library/hh500409%28v=vs.110%29.aspx#wit) if you need to manually add them to a team project.   
</td>
<td>
TFS 2012
</td>
</tr>
<tr>
<td>
My Work
</td>
<td>
Supports your ability to [develop code and manage pending changes](https://msdn.microsoft.com/library/ms245462.aspx#my_work) from the My Work page in Team Explorer. My Work only appears when you have Visual Studio Premium or Visual Studio Ultimate installed.<br /> 
Adds the metastate-to-workflow state mapping in ProcessConfiguration for the Bug Category. If you need to manually update the bug workflow states and metastates, see [Support bug update status using My Work](https://msdn.microsoft.com/library/hh739067%28v=vs.140%29.aspx).   
</td>
<td>
TFS 2012
</td>
</tr>

<tr>
<td>
Feedback
</td>
<td>
Adds the Feedback Request and Feedback Response WITs and categories to the team project. These items support [feedback requests and responses](https://msdn.microsoft.com/library/hh301769.aspx). <br/>
Go [here](https://msdn.microsoft.com/library/hh500409%28v=vs.110%29.aspx#wit) if you need to manually update a team project.   
</td>
<td>
TFS 2012
</td>
</tr>

<tr>
<td>
Planning Tools
</td>
<td>
Adds or updates process configuration that supports using the Agile tools: [product backlog](../backlogs/create-your-backlog.md), [plan sprints](../scrum/sprint-planning.md), [Kanban board](../kanban/kanban-basics.md), and [more](../scrum/define-sprints.md).<br/>

Agile tools depend on the WITs, categories, and process configuration definitions that are made.  Definitions are interdependent. <br/>

See [Configure Agile tools](https://msdn.microsoft.com/library/hh543813.aspx) and [ProcessConfiguration XML element reference](https://msdn.microsoft.com/library/hh500408.aspx) to learn more about defining the process configuration for your team project.  
</td>
<td>
TFS 2012
</td>
</tr>

<tr>
<td>
Storyboarding
</td>
<td>
Adds the Storyboards control and tab to requirement WIT for the team project--such as Product backlog item for Scrum, User Story for Agile, and Requirement for CMMI. The Storyboards control [supports linking storyboards to the work item as well as launching the Storyboarding](https://msdn.microsoft.com/library/hh409276.aspx). <br/>

Go [here](https://msdn.microsoft.com/library/hh500409%28v=vs.110%29.aspx##storyboard) if you need to manually add the Storyboards control to a WIT. 
</td>
<td>
TFS 2012
</td>
</tr>
 

<tr>
<td>
Portfolio Backlogs
</td>
<td>
Adds the Feature and Epic WITs and categories to the team project and modifies the process configuration to support portfolio backlogs. These features enable teams to [activate the portfolio backlogs they work with to organize their backlogs](../backlogs/organize-backlog.md). <br/>

Go [here](add-features-manually.md) if you need to manually add them to a team project. <br/>
Go [here](add-portfolio-backlogs.md) if you want to add more portfolio backlogs. 
</td>
<td>
TFS 2013, TFS 2015
</td>
</tr>


<tr>
<td>
Shared Parameters
</td>
<td>
Adds the Shared Parameter WIT and category to the team project. You use Shared Parameter work items to [run tests with different data](https://msdn.microsoft.com/library/dd997832.aspx).<br/>
Go [here](https://msdn.microsoft.com/en-us/library/hh500409%28v=vs.120%29.aspx) if you need to manually add them to a team project.   

</td>
<td>
TFS 2013.2
</td>
</tr>


<tr>
<td>
Test Plan and Test Suite
</td>
<td>
Adds the Test Plan and Test Suite WITs and categories to the team project. These items support managing and customizing test plans and test suites similar to other WITs, as well as [planning and executing manual tests using the web portal](https://msdn.microsoft.com/library/dd380763.aspx). <br/>

Go [here](#test-management) to learn more about how this feature gets enabled.    
</td>
<td>
TFS 2013.3
</td>
</tr>

<tr>
<td>
Bug Behavior
</td>
<td>
Adds the required fields to the Bug WIT definition so that they can be treated like requirements or like tasks. Teams can configure this option as described in [Show bugs on backlogs and boards feature](show-bugs-on-backlog.md).<br/>

Go [here](add-features-manually.md) if you need to manually add them to a team project. 
</td>
<td>
TFS 2015
</td>
</tr>

</tbody>
</table>

##Related features notes 

Not all new features require feature enablement. To learn more about additional feature updates with the latest upgrade of TFS, check out these resources: 

- [Team Foundation Server 2015 - TFS RC](https://www.visualstudio.com/news/tfs2015-vs)
- [Visual Studio 2013 Update 4 (2013.4) RC](https://www.visualstudio.com/news/vs2013-update4-rc-vs#WIT)

<a id="test-management" >   </a>
###Test Plan and Test Suite features  
The Test Plan and Test Suite WITs are added when you run the TFS Upgrade Wizard. They aren't enabled through the Configure Feature wizard. They support customization of test plans and test suites

<p>The enhancements support:</p>
                  <ul>
                    <li>
                      <p>Test plans and test suites are now work item types (WITs). You can add fields, change the workflow, and <a href="https://msdn.microsoft.com/en-us/library/hh409273.aspx">customize them like any other work item type</a>. </p>
                    </li>
                    <li>
                      <p>The area path security model now contains permissions to <b>Manage test suites</b>. The <b>Manage test plans</b> permissions has been re-scoped to manage only test plans. Previously it covered permission management of both test plans and test suites.</p>
                    </li>
                    <li>
                      <p>The History field for test-related artifacts now provides a consolidated view of changes made to work item fields as well as changes to related artifacts such as test points and test configurations. A new field, the Test Suite Audit field, available in the test suite work item form, captures and displays these related artifact changes in the work item history.</p>
                    </li>
                  </ul>
                  <p>The server upgrade automatically converts existing test plans and test suites to WITs and migrates test data and links. If it encounters a problem, a warning message appears in the server log. To learn more, see <a href="https://msdn.microsoft.com/en-us/library/dn789837.aspx">Update a team project manually to support test management</a>. </p>
                  <p>To learn about changes introduced to Test Manager and the web portal, see [Plan manual tests](https://msdn.microsoft.com/library/dd380763.aspx).</p>


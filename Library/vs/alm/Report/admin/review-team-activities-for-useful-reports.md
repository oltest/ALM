Title: Review team activities to support useful reports | Team Foundation Server
Description: Review team activities to support useful SQL Server reports when working in Team Foundation Server (TFS)
ms.TocTitle: Review team activities
ms.ContentId: 46456FBF-EECC-4096-9A98-3A9457F97EB2

#Review team activities to support useful reports
By adding a report server to your on-premises Team Foundation Server (TFS), you can access a wealth of data about your team's projects, such as build quality, bug trends, burndown, and test progress. SQL Server Reporting Services (SSRS) reports provide insight to help teams manage work and improve processes.


<table>
    <tr valign="top">
        <td width="25%">
            ![Step 1: Add a report server](_img/step-1-add-a-report-server.png)
            <br/>
            [Add a report server](add-a-report-server.md)
        </td>
        <td width="25%">
            ![Step 2: Upload reports](_img/step-2-upload-reports.png)
            <br/>
            [Upload reports](upload-reports.md)
        </td>
        <td width="25%">
            ![Step 3: Grant permissions](_img/step-3-grant-permissions.png)
            <br/>
            [Grant permissions to view or create reports](grant-permissions-to-reports.md)
        </td>
        <td width="25%">
            ![Step 4: Review team tasks](_img/step-4-review-team-activities.png)
        </td>
    </tr>
</table>


Now that you've uploaded reports, how do you use them to track progress, gain insight, and improve processes?

First, make sure your team is performing the activities that create the data that these reports use. Your team is probably performing most of these activities already.

Here's a summary of the reports that TFS provides and the team activities that are associated with them. Over time, you can use these reports to see trends and identify which practices and processes require more attention to deliver desired results.

##Monitor code quality
Build reports track the quality of software under development. By defining tests to run automatically as part of each build definition and instrumenting tests to gather code coverage data, you can gain insight about the quality of the builds, tests, and code. 

<table>
<tr valign="top">
<td>
<b>Build and test activities</b> 
<ol>
<li><a href="https://msdn.microsoft.com/library/ms252495.aspx">Configure a build system</a>.</li>
<li><a href="https://msdn.microsoft.com/library/ms181715.aspx">Define your build process</a>.</li>
<li><a href="https://msdn.microsoft.com/library/ms253138.aspx">Run tests in your build process</a>.</li>
<li><a href="https://msdn.microsoft.com/library/ms181734.aspx">Rate completed builds</a> to populate the Build Quality dimension.</li>
</ol>
</td>
<td>
<b>Build reports</b>
<ul>
<li><a href="https://msdn.microsoft.com/library/dd380683.aspx">Build Quality Indicators</a> (Agile and CMMI only)</li>
<li><a href="https://msdn.microsoft.com/library/dd380643.aspx">Build Success Over Time</a> (pictured)</li>
<li><a href="https://msdn.microsoft.com/library/dd380708.aspx">Build Summary</a></li>
</ul>
    </td>
</tr>
</table>

For a free downloadable guide to testing and monitoring builds, see [Testing for Continuous Delivery with Visual Studio 2012](https://msdn.microsoft.com/library/jj159345.aspx).

**Sample build success over time report**  

![Sample build summary report](_img/IC665009.png)  

##Monitor progress
Project management reports provide insight into how much work the team is tackling within a sprint or release, and the rate of their progress. By linking work items and updating specific fields as work is performed, you can track the progress of individual stories and be able to more accurately estimate future activities. 

<table>
<tr valign="top">
<td>
<b>Work item tracking activities</b>
    <ol>
        <li>
            <a href="https://msdn.microsoft.com/library/ee518933.aspx">Create the backlog</a>.
            <ul>
                <li>Create product backlog items and specify the <b>Effort</b> (Scrum).</li>
                <li>Create user stories and specify the <b>Story Points</b> (Agile).</li>
                <li>Create requirements and specify the <b>Size</b> (CMMI).</li>
            </ul>
        </li>
        <li><a href="https://msdn.microsoft.com/library/ee191595.aspx">Work in sprints</a>. Assign backlog items to sprints, create tasks and link them to parent backlog items, and assign to a team member.</li>
        <li>
            <a href="https://msdn.microsoft.com/library/hh409275.aspx">Update Remaining Work for tasks</a>. For Agile and CMMI team projects, update <b>Completed Work</b> as well.
            <br />
            <b>Tip</b>
            <br />
            The only report that references <b>Original Estimate</b> is <a href="https://msdn.microsoft.com/library/dd380706.aspx">Status of All Iterations</a>.
        </li>
        <li>Create test cases and bugs, link them to their parent backlog item, and update their <b>State</b>.</li>
        <li>(Optional) Assign work items to areas to filter reports.</li>
    </ol>
</td>
    <td>
        <b>Project management (Scrum) reports</b>
        <ul>
            <li><a href="https://msdn.microsoft.com/library/dn641200.aspx">Backlog Overview</a></li>
            <li><a href="https://msdn.microsoft.com/library/ff731579.aspx">Release Burndown</a></li>
            <li><a href="https://msdn.microsoft.com/library/ff731588.aspx">Sprint Burndown</a></li>
            <li><a href="https://msdn.microsoft.com/library/ff731575.aspx">Velocity</a></li>
        </ul>
        <b>Project management (Agile and CMMI) reports</b>
        <ul>
<li><a href="https://msdn.microsoft.com/library/dd380678.aspx">Burndown and Burn Rate</a></li>
<li><a href="https://msdn.microsoft.com/library/dd380673.aspx">Remaining Work</a></li>
<li><a href="https://msdn.microsoft.com/library/ee461517.aspx">Requirements Overview</a> (CMMI)</li>
<li><a href="https://msdn.microsoft.com/library/ee461582.aspx">Requirements Progress</a> (CMMI)</li>
<li><a href="https://msdn.microsoft.com/library/dd380706.aspx">Status of All Iterations</a> (similar to Velocity)</li>
<li><a href="https://msdn.microsoft.com/library/dd380641.aspx">Stories Overview</a> (Agile) (pictured)</li>
<li><a href="https://msdn.microsoft.com/library/dd380641.aspx">Stories Progress</a> (Agile)</li>
<li><a href="https://msdn.microsoft.com/library/ee707132.aspx">Unplanned Work</a></li>
</ul>
    </td>
</tr>
</table>

**Sample stories overview report**  
![Sample stories overview report](_img/IC665011.png)  


##Monitor test plans and bug tracking
Test planning reports support monitoring the test progress and coverage of backlog items or user stories. Bug tracking reports illustrate the team's capacity to find and resolve bugs.

<table>
<tr valign="top">
<td>
<b>Test planning and bug tracking activities</b>
<ol>
<li>Define test plans and test cases, and update their <b>State</b> as work progresses.</li>
<li><a href="https://msdn.microsoft.com/library/dd293545.aspx">Mark the results of each validation step in manual tests</a> as either passed or failed.</li>
<li><b>Create bugs</b>, specify the <b>Priority</b> and <b>Severity</b>, assign to a team member, and update the <b>State</b>.</li>
<li>(Optional) Assign test cases and bugs to areas and iterations to filter reports.</li>
</ol>
</td>
<td>
<b>Test and bug reports</b>
<ul>
<li><a href="https://msdn.microsoft.com/library/dd380713.aspx">Test Case Readiness</a></li>
<li><a href="https://msdn.microsoft.com/library/dd380702.aspx">Test Plan Progress</a> (pictured)</li>
<li><a href="https://msdn.microsoft.com/library/dd380736.aspx">Bug Status</a> (Agile and CMMI only)</li>
<li><a href="https://msdn.microsoft.com/library/dd380674.aspx">Bug Trends</a> (Agile and CMMI only)</li>
<li><a href="https://msdn.microsoft.com/library/dd380731.aspx">Reactivations</a> (Agile and CMMI only)</li>
</ul>
</td>
</tr>
</table>

**Sample test plan progress report**   
![Sample test plan progress report](_img/IC665012.png)  

##Q & A
<!-- BEGINSECTION class="md-qanda" -->


####Q: Do reports handle stories and substories or tasks and subtasks?
**A:**  Yes, you can subdivide stories or backlog items as well as tasks, creating a nested hierarchy of both backlog items and tasks. You can nest items several levels deep. If you subdivide a task into subtasks, specify hours only for the subtasks. These hours are rolled up as summary values for the parent task and their parent backlog item. To correct reports you believe are in error, see [Address inaccuracies published for summary values](https://msdn.microsoft.com/library/dd997572.aspx).

####Q: Which reports depend on linking work items?
**A:**  The overview and progress reports depend on linking tasks, test cases, and bugs to backlog items. You must link these items using the parent-child link for tasks and bugs and the Tested By link for test cases.

####Q: Which reports depend on Microsoft Test Manager?
**A:**  [Test Case Readiness](https://msdn.microsoft.com/library/dd380713.aspx) and [Test Plan Progress](https://msdn.microsoft.com/library/dd380702.aspx) reports are designed to work with Test Manager. Also, the test points and test progress in project management overview reports depend on linking test cases to backlog items.

####Q: Are these reports the same as the agile planning charts that appear in the web portal?
 **A:**  While some reports do display similar information, such as sprint burndown and velocity or status on all iterations, these reports are formatted differently and support additional filters. Other reports, such as the build and test planning reports, are not available through the web portal at this time.

####Q: Do you want to create additional product areas or release milestones?
**A:**  See [Modify areas or iterations](../../Work/customize/modify-areas-iterations.md).

####Q: Do you want to bulk edit work items to assign them to an area, iteration, team member, or priority?
**A:**  See [Bulk modify work items](https://msdn.microsoft.com/library/hh409280.aspx).

####Q: Do you want to add a field to track additional data?
**A:**  See [Add or modify a work item field to support reporting](https://msdn.microsoft.com/library/ee921481.aspx).  

<!-- ENDSECTION -->
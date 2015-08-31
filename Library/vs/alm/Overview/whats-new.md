Title: What's new for DevOps and Visual Studio Team Foundation Server 2015 | TFS
Description: Your guide to new features available with Team Foundation Server 2015
ms.TocTitle: What's new
ms.ContentId: F72EC483-F195-4157-82AB-1EBEE87F7C10

#What's new for Team Foundation Server 2015

You can use Visual Studio Team Foundation Server to manage your product lifecycle, reduce risks, and improve efficiencies. This page highlights some important features that are available with TFS 2015.  

To learn about  what's new with the cloud service offering, see  [Visual Studio Online Features update](https://www.visualstudio.com/news/release-archive-vso).   

##DevOps

<table>
<tbody valign="top">
<tr>
<td width="195">
![version control](_img/get-started-vso-tfs-tfvc-git-source-control.png)
</td>
<td>
<h3>Code</h3>

<p>When you use Git, it's easier than ever to work with branches and see how the changes in your history diverged.</p>

<p>See [What's new in version control](/Library/vs/alm/Code/whats-new.md).</p>
</td>
</tr>
<tr>
<td>
![build](_img/get-started-vso-tfs-build-tools.png)
</td>
<td>
<h3>Build</h3>
<p>We've built a brand new scriptable build system that's web-based and cross-platform. We believe all new and most existing customers should use it instead of the XAML build system.</p>
<p>See [Overview of Team Foundation Build 2015](/library/vs/alm/build/feature-overview.md)</p>
</td>
</tr>
<tr>
<td>
![testing](_img/get-started-vso-tfs-testing.png)
</td>
<td>
<h3>Test</h3>
<ul>
<li>[Create unit tests](https://msdn.microsoft.com/library/dn823749%28v=vs.140%29.aspx) for your code. 
Explore your .NET code to generate test data and a suite of unit tests. 
For every statement in the code, a test input is generated that will execute that statement.</li>
<li>[Run cloud-based load tests where your users are](https://msdn.microsoft.com/en-us/library/dn250793%28v=vs.140%29.aspx) 
when you use Visual Studio Online. This generates load in an Azure datacenter that's closer to your users, reducing latency and simulating local conditions.</li>
<li>[Run automated tests continuously with your builds](https://msdn.microsoft.com/library/mt270060%28v=vs.140%29.aspx). Make sure that your app still works after changes are checked in and built.</li> 
</ul>
</td>
</tr>
<tr>
<td>
![release management](_img/get-started-vso-tfs-release-management.png)
</td>
<td>
<h3>Release</h3>
<p>An updated version of Release Management is available for Visual Studio 2015 
with improved usability in the client launch page, faster rendering and interactivity 
in other client pages, better synchronization of Active Directory and TFS 
security groups, and improved performance when creating new releases.
Go [here](https://msdn.microsoft.com/Library/vs/alm/Release/previous-version/release-management-overview) for more details.</p>
<p>In addition, a preview of the new version of Release Management is now available.
This is a comprehensive and fully integrated service in Visual Studio Online and Team Foundation Server 2015.
More details of the service, and how you can sign up for the preview, are 
[here](https://msdn.microsoft.com/Library/vs/alm/Release/getting-started/understand-rm)</p>
</td>
</tr>
</tbody>
</table>

## Developer productivity and Application Insights

<table>
<tbody valign="top">
<tr>
<td width="195">
![cross platform support](_img/get-started-vso-tfs-cross-platform-support.png)
</td>
<td>
<h3>Developer productivity</h3>

<p>
**Code maps**: Find out more about your code’s design, while reading less code, when using Visual Studio Enterprise. Code maps now:</p>
<ul>
<li>Make it easier to see containment context as you add items to maps.
</li>
<li>Render more quickly and are more responsive.
</li>
<li>Allow you to filter elements and relationships to make maps easier to use.
</li>
<li>Have a much better organized and more intuitive shortcut command menus.
</li>
</ul>
<p>Find out more about <a href="https://msdn.microsoft.com/en-us/library/dd409453(v=vs.140).aspx">code maps</a>.</p>
<p>
**Layer diagrams**: Update these diagrams using Class View and Object Browser. Read more in the <a href="https://www.visualstudio.com/news/vs2015-vs">release notes</a>, or find out more about <a href="https://msdn.microsoft.com/en-us/library/dd418995(v=vs.140).aspx">layer diagrams</a>.</p>
<p>
**UML diagrams**: You can no longer create UML class diagrams and sequence diagrams from code, and you can no longer import UML elements from XMI files. You can still create these diagrams using new UML elements. Find out more about <a href="https://msdn.microsoft.com/en-us/library/dd409416(v=vs.140).aspx">UML class diagrams</a> and <a href="https://msdn.microsoft.com/en-us/library/dd409389(v=vs.140).aspx">UML sequence diagrams</a>.</p>
<p>You can no longer use Architecture Explorer to work with code maps, layer diagrams, and UML class diagrams. Use Solution Explorer, Class View, and Object Browser instead. Read more in the <a href="https://www.visualstudio.com/news/vs2015-vs">release notes</a>.</p>

<p>With **CodeLens** you can find patterns in your code's change history to understand their impact. CodeLens shows change history as a chart. It is also now available in Visual Studio Professional edition. Read more in the <a href="https://www.visualstudio.com/news/vs2015-vs">release notes</a>. Or, find out more about <a href="https://msdn.microsoft.com/library/dn269218(v=vs.140).aspx">CodeLens</a>.</p>
</td>
</tr>
<tr>
<td>
![application insights](_img/get-started-vso-tfs-application-insights.png)
</td>
<td>
<h3>Application Insights</h3>
<p>Track the performance and usage of your live applications with [Visual Studio Application Insights](https://azure.microsoft.com/services/application-insights).</p>
<ul>
<li>Extensible analytics service designed for developers.
</li>
<li>Monitor both web and stand-alone apps on a wide variety of platforms: [ASP.NET](https://azure.microsoft.com/documentation/articles/app-insights-start-monitoring-app-health-usage/) 
or [J2EE](https://azure.microsoft.com/documentation/articles/app-insights-java-get-started/), hosted on-premises 
or in the cloud; device apps on [Windows](https://azure.microsoft.com/documentation/articles/app-insights-windows-get-started/), 
[iOS](https://azure.microsoft.com/documentation/articles/app-insights-ios/), 
[Android](https://azure.microsoft.com/documentation/articles/app-insights-android/), 
[OSX](https://azure.microsoft.com/documentation/articles/app-insights-platforms/) and 
[other platforms](https://azure.microsoft.com/documentation/articles/app-insights-platforms/).
</li>
<li>[Analyze usage patterns](https://azure.microsoft.com/documentation/articles/app-insights-platforms/) to continuously improve the usability of your app. Page, user and session counts, usage path traces.
</li>
<li>[Detect, triage and diagnose performance issues](https://azure.microsoft.com/documentation/articles/app-insights-detect-triage-diagnose/). Performance and availability alerts, crash and exception reports, dependency tracing, integrated log and event search.
</li>
<li>
[Export](https://azure.microsoft.com/documentation/articles/app-insights-export-telemetry/) to [SQL](https://azure.microsoft.com/en-gb/documentation/articles/app-insights-code-sample-export-telemetry-sql-database/), [Power BI](https://azure.microsoft.com/documentation/articles/app-insights-export-power-bi/) or your own tools for even deeper analysis.
</li>
</ul>
</td>
</tr>
<tr>
<td>
![integrate](_img/get-started-vso-tfs-integration.png)
</td>
<td>
<h3>Integrate</h3>

<ul>
<li><p>**[JSON REST APIs](https://www.visualstudio.com/integrate/api/overview)** enable a lightweight way to work with TFS from virtually any device, platform, or technology stack, including Windows, Android, iOS, Node.js, and others. You can create and query work items, queue a build, get recent team room messages, access source code, and accomplish almost any team or code management task.</p>
<p>Go [here](https://www.visualstudio.com/en-us/integrate/get-started/rest/basics) to get started.</p>
</li>
<li><p>**Service hooks: ** make it easy to integrate with external services such as Trello or Campfire, and to build an app experience that is instantly notified when events are triggered in TFS, such as completed builds, commits/check-ins or work item changes. You'll find the Services hooks hub under project administration.</p>
 <p>A service hook subscription controls what action to perform on a target, external service when a specific type of event happens. Similarly to an email alert subscription, a service hook subscription is associated with the user who created it. When an event occurs and a service hook attempts to match a configured subscription to an event, a permission check is performed to ensure the user who created the subscription has permission to access to the resource associated with the event. For example, a user (likely a project administrator) creates a service hook subscription that is triggered on all “work item created” events. When a new work item is created under an area path that this user does not have access to, the permission check will prevent the subscription from matching and therefore avoid any external notification from being sent via this subscription.</p>
 <p>However, because service hooks make it easy to integrate with external services, you should make sure that the data that the creator of a subscription has access to is not made available to other users who might not have the same level of access. For example, a subscription that is defined to send all “code push” events to a Campfire room could result in information being improperly disclosed to users who do not have access to the repository associated with the event (but would be able to see the information because they have access to the Campfire room).</p>
 <p>[Learn more about working with service hooks](https://www.visualstudio.com/get-started/integrate/integrating-with-service-hooks-vs). </p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

##Agile software development

<table>
<tbody valign="top">
<tr>
<td width="195">
![Work item tracking, Agile tools](_img/get-started-vso-tfs-work-item-tracking.png)
</td>
<td>
<h4>Backlog and bug management</h4>
<ul>
<li>The Epic portfolio backlog has been added
</li>
<li>[Backlogs and portfolio backlogs are now team-configurable](../Work/backlogs/organize-backlog.md)
</li>
<li>[**Track bugs as requirements or as tasks** has been added as a team-configurable option](../Work/customize/show-bugs-on-backlog.md)
</li>
<li>[Quickly expand and collapse the product backlog hierarchy with Parents Show/Hide control](../Work/backlogs/organize-backlog.md)
</li>
<li>[Add card-editable fields and tags to the task board](../Work/customize/customize-cards.md)
</li>
<li>[Unparented tasks now appear on the task board](../Work/scrum/task-board.md) 
</li>
<li>Quickly filter your product and portfolio backlogs with the **Key word filter** control
</li>
</ul>

<h4>Kanban board</h4>
<ul>
<li>[Add, edit, and reorder items](../Work/kanban/kanban-basics.md) directly on the board
</li>
<li>[Implement a pull system using split columns of Doing and Done](../Work/kanban/split-columns.md)
</li>

<li>[Add custom swimlanes to track work at different service classes](../Work/kanban/expedite-work.md)  
</li>
<li>Support team policies for handoff by specifying a column's [Definition of done](../Work/kanban/definition-of-done.md)
</li>
<li>[Customize cards](../Work/customize/customize-cards.md) to display card-editable fields 
</li>
<li>Include/exclude the first column of the Kanban board from the Cumulative flow diagram, as well as set the start date
</li>
<li>Quickly filter the board with the **Key word filter** control
</li>
</ul>

<h4>Work item form and query enhancements</h4>
<ul>
<li>[**&#64;CurrentIteration** macro](../Work/track/query-by-date-or-current-iteration.md) allows you to create queries that automatically update based on the team's current iteration.  
</li>
<li>Quickly filter query results with the **Key word filter** control
</li>
<li>**Query progressive disclosure** displays only the first two levels of results, so large queries open quickly—additional results are loaded on demand.</li>
<li>History discussions are easier due to optimizations made to the **History control** 
</li>
</ul>

<h4>Process template enhancements</h4>
<ul>
<li>Agile, CMMI, and Scrum process templates have been renamed, locked, and are now versionless  
</li>
<li>**Scaled Agile Framework** more fully supported by adding the Epic work item type and portfolio backlog and the [Value Area (Business vs. Architectural)](https://msdn.microsoft.com/library/dd983994.aspx) and the [Time Criticality](https://msdn.microsoft.com/library/dd983994.aspx) fields.
</li>

<li>Large queries now open more quickly with **Query progressive disclosure** as only the first two levels of results display with loading of additional results occuring on demand  
</li>
<li>History discussions are easier due to optimizations made to the **History control** 
</li>
</ul>
[Changes made to process templates](../Work/guidance/manage-process-templates.md) provides a complete list of all other field and workflow changes. 
<h4>Identity selector support for distinct user selection and query on identity fields</h4>
<p>Prior to TFS 2015, you couldn’t distinguish between users with the same display name when 
assigning and querying work items. The identity selector chooses the correct user from  
those users who share the same display name based on their account name.  </p>

![Identity selector](_img/identity-selector.png)  

<p>What does this mean for queries? When querying with Visual Studio 2013 or earlier versions, queries return results of everyone who shares the same display name. With Visual Studio 2015 and later clients, as well as the web portal for TFS 2015, queries return results only for the user you selected through the Identity selector.</p> 


</td>
</tr>
</tbody>
</table>

##Additional changes and enhancements 

###Access levels and licensing changes
The following new features have been introduced and are available with Basic and Advanced licenses: 
- Web-based test execution 
- Analyze test results and manage machine groups 

The following features which previously required an Advanced license are now available with a Basic license:  
- [Chart authoring](../Report/charts.md)   
- [Team rooms](https://msdn.microsoft.com/en-us/library/dn169471.aspx)   
- [Advanced portfolio management](../Work/backlogs/organize-backlog.md)

In addition, you can [storyboard your ideas using Storyboarding using PowerPoint](https://msdn.microsoft.com/library/hh409276%28v=vs.140%29.aspx) when you download the free [Visual Studio Community edition](https://www.visualstudio.com/products/vs-2015-product-editions.aspx), or other Visual Studio 2015 product. 

###Project rename
[Project rename](https://msdn.microsoft.com/library/vs/alm/tfs/administer/project-rename) allows you to change the name of your team project.  

##Related notes

Learn more about the latest updates available from these resources:  

- [What's new in Visual Studio 2015](https://msdn.microsoft.com/library/bb386063%28v=vs.140%29.aspx) - to review the latest features of the Visual Studio client
- [Visual Studio Online, Get started](https://www.visualstudio.com/get-started/overview-of-get-started-tasks-vs) - to get started using our cloud offering, Visual Studio Online which provides end-to-end support for software development without the overhead of maintaining and managing servers. 
- [Visual Studio download page](https://www.visualstudio.com/products/visual-studio-2015-downloads-vs) - to download the latest version of TFS


<!---
You can download the latest version of TFS from the [Visual Studio download page](https://www.visualstudio.com/products/visual-studio-2015-downloads-vs).

You can get started using our cloud offering, Visual Studio Online, or our on-premises TFS server. Visual Studio Onlines provide end-to-end support for software development without the overhead of maintaining and managing servers. Go [here](https://www.visualstudio.com/get-started/overview-of-get-started-tasks-vs) to sign up and use Visual Studio ALM in the cloud. 

-->


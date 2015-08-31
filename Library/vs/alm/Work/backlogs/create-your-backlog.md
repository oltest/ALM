Title: Create your backlog | Visual Studio Online
Description: Add items, plan, order, and estimate your backlog of deliverables - Visual Studio Online and Team Foundation Server
ms.TocTitle: Create your backlog
ms.ContentId: 04df6b31-ef6c-4285-81a6-96768f03ecf4

# Create your backlog
Your product backlog corresponds to your project plan, the roadmap for what your team plans to deliver. 
Once defined, you have a prioritized list of features and requirements to build. Your backlog also provides a 
repository of all the information you need to track and share with your team.

A great backlog conveys customer needs and value. Over the course of the project, your team will add detailed 
information to each backlog item, break them down into smaller items, prioritize and estimate them, and finally, 
implement them and deliver the results to your customers.

Here's a view of a backlog based on the Scrum process template. This particular backlog includes both product backlog items 
(PBIs)--shown here with blue bars--and bugs--shown with red bars. These are just two of several work item types that you 
have available to plan and track your project. Because each work item type has its own color assignment, you can quickly 
differentiate the types of work in the list.

![Product backlog](_img/ALM_CB_Overview.png)

Your backlog consists of a list of [work items](https://msdn.microsoft.com/library/hh409275.aspx). 
You use work items to share information, assign work to team members, track dependencies, organize work, 
and more. Because the most important work appears at the top of the list, your team always knows what to work on next.


<blockquote style="font-size: 13px">**Note:  **Depending on the process template you chose when creating your team project--[Scrum](https://msdn.microsoft.com/library/ff731587.aspx), 
[Agile](https://msdn.microsoft.com/library/dd380647.aspx), or [CMMI](https://msdn.microsoft.com/library/dd997574.aspx)--
the items in your backlog may be called product backlog items (PBIs), user stories, or requirements. All three are similar: they describe the customer value to delivered and the work to be performed.   

By default, PBIs and bugs appear on Scrum backlogs, user stories on Agile backlogs, and requirements on CMMI backlogs. Each team can [choose how they want to treat bugs: either as requirements or tasks](../customize/show-bugs-on-backlog.md).  
</blockquote>  

##Convert ideas into backlog items or stories
Building your backlog starts by quickly capturing the requirements you want for your product. 

###Open your backlog from the web portal
![Open the backlog](_img/ALM_CB_OpenBacklog.png)

The URL follows this pattern:
* Visual Studio Online: ```https://{account}.visualstudio.com/DefaultCollection/{project}/_backlogs```
* Team Foundation Server (on-premises): ```http://{server}:8080/tfs/{collection}/{project}/_backlogs```

If you don't have a team project yet, create one in [Visual Studio Online](https://www.visualstudio.com/get-started/set-up-vs) or set one up in an [on-premises TFS](https://msdn.microsoft.com/library/ee518933.aspx). If you don't have access to the team project, [get invited to the team](../scale/multiple-teams.md#add-team-members).

###Build your backlog
Begin building your backlog by entering a title and click Add. Repeat this step until you've captured all your main ideas.
![Add work items to the backlog](_img/ALM_CB_BacklogItems.png)

If you've already defined a long list of items, you don't have to reenter them one at a time. Instead, use [Microsoft Excel](https://msdn.microsoft.com/library/dd286627.aspx) to quickly import them to your backlog.

##Move items into priority order
After you've got some items on your backlog, you can order them and create a prioritized list of work. Frequently reviewing and prioritizing your backlog can help your team know what's most important to deliver next.

Reorder your backlog by simply dragging work items. Or, if you prefer the keyboard, hold the Alt key  and use the up and down arrows.

![Reorder work items](_img/ALM_CB_OrderBacklog.png)

<a id="estimates">  </a>
##Add details and estimates
Getting your backlog built and prioritized provides the high level roadmap. However, before your team can actually start work on any item, they'll need more details. You capture these details within the work item form.

Open each item (double-click, or press Enter to open the selected item) and add all the info you want to track. Enter as much detail as the team needs to understand the scope, estimate the work required, develop tests, and ensure that the end product meets acceptance criteria.

![Add details to a work item](_img/ALM_CB_CreateWorkItem.png)

Field|Usage
-----|------
[Effort](https://msdn.microsoft.com/library/dd997792.aspx)|Provide a relative estimate of the amount of work required to complete a PBI. Use any unit of measurement your team prefers. Some options are [t-shirt size, story points, or other relative unit](#estimates).<br />For user stories and requirements, you capture estimates in the Story Points and Size fields. These fields support usage of the [velocity and forecast](../scrum/velocity-and-forecasting.md) tools.
[Business Value](https://msdn.microsoft.com/library/dd983994.aspx)|Specify a priority that captures the relative value of a PBI compared to other PBIs. The higher the number, the greater the business value.<br />Use this field when you want to capture a priority separate from the changeable backlog stack ranking.
[Description](https://msdn.microsoft.com/library/dd997882.aspx) (PBIs)|Provide enough detail to create shared understanding of scope and to support estimation efforts. Focus on the user, what they want to accomplish, and why. Don't describe how to develop the product. Do provide sufficient details so that your team can write tasks and test cases to implement the item.
[Acceptance Criteria](https://msdn.microsoft.com/library/dd983994.aspx)|Define what "Done" means by describing the criteria that the team should use to verify whether the PBI or the bug fix has been fully implemented.<br />
Before work begins on a PBI or bug, describe the [criteria for customer acceptance](#acceptance) as clearly as possible. Conversations between the team and customers to determine the acceptance criteria help ensure a common understanding within the team to meet customers' expectations. Also, this info provides the basis for acceptance testing.

<a id="bulk-modify">  </a>
##Bulk modify items and other options   
<blockquote style="font-size: 13px">**Feature availability: ** *Multi-select of work items on the backlog and sprint backlogs is currently supported only for Visual Studio Online. This feature works in the same way as [multi-select works within query results](https://msdn.microsoft.com/library/hh409280.aspx). *  </blockquote>  

You can quickly perform several tasks from a work item's context menu.  

From the backlog, select the work item(s) you want to modify. To select several items in a sequence, hold down the shift key. To select several non-sequential items, use the Ctrl key.   

![Backlog multi-select several non-sequential items and open context menu](_img/backlog-multi-select-non-sequential-items.png)

The menu options change based on whether you have selected a single work item or several. 

| Single-select menu options    | Multi-select menu options        |
|--------------------------|-------------------------------|
| ![Backlog single-select menu](_img/vso-backlog-single-select-menu.png) | ![Backlog multi-select menu](_img/vso-backlog-multi-select-menu.png)       |

You can use the [hotkeys and keyboard shortcuts](https://msdn.microsoft.com/library/dd380652.aspx) to navigate within the backlog list. 


##Organize your backlog
In addition to adding items to your backlog, you may want to group items in your backlog, break backlog items into smaller items, or [capture and manage spikes](#spikes) in your backlog. Breaking backlog items into smaller items minimizes the size variability of estimates. When estimates around effort or story points vary widely, it's harder to plan consistently and gain good metrics around team velocity.  

To [organize your backlog](organize-backlog.md), you can map PBIs to Features and Features to Epics. This also groups backlog items within a hierarchy. Another way to group items and filter your backlog is by [tagging items](https://msdn.microsoft.com/library/dn132606.aspx).  

Lastly, if you work with several teams, and each team wants their own backlog view, you can [create additional teams](../scale/multiple-teams.md). Each team gets access to a set of Agile tools focused on their work based on their team's default area path.  

##Try this next
Now that you've got a working backlog in place, your team can begin work on the top priority items. From here, it's time to make the decision on how you want to work as a team: Scrum or Kanban? You can use these methods independently or together.

Teams that want the least overhead in terms of tracking and estimating may prefer Kanban. Teams that like to work at a steady cadence and plot the details of their sprint plan may prefer Scrum.

With [Kanban](../kanban/kanban-basics.md), teams focus on the flow of work from start to finish - limiting work in progress in order to optimize flow and deliver the highest priority items as quickly as possible.

Using [Scrum](https://msdn.microsoft.com/library/dn986599.aspx) methods, teams define a sprint schedule: a time-boxed set of periods for planning and developing. Using the sprint backlog, they plan their sprints by assigning items to the sprint and defining the tasks required to develop each item. Task boards, capacity charts, and sprint burndown charts all help to keep the team aware of progress throughout the sprint cycle.

##Related backlog notes
Use your backlog to plan and manage your project. A few things to keep in mind...
*   Every team owns their own backlog, to create a new backlog you [create a new team](../scale/multiple-teams.md) 
*   Every backlog has a corresponding [Kanban board](../kanban/kanban-basics.md) you can use to track progress and update status  
*   Each team can control how [bugs show up on their backlogs ](../customize/show-bugs-on-backlog.md)   
*   To have work performed by several teams roll up in to a portfolio backlog, you'll want to [setup the team hierarchy](http://msdn.microsoft.com/library/hh500414.aspx)  

### Backlog controls

| Control                  | Function                      |
|--------------------------|-------------------------------|
| Backlog               | Switch to backlog view           |
| Board    | [Switch to Kanban board view](../kanban/kanban-basics.md)  |
| Forecast | [Turn forecasting Off/On](../scrum/velocity-and-forecasting.md) |
| Mapping | [Turn mapping Off/On](organize-backlog.md)   |
| Parents | [Show/Hide parents](organize-backlog.md) |
| In progress items | [Show/Hide in progress items](../scrum/velocity-and-forecasting.md)   |
| ![Settings icon](../_img/icons/gear_icon.png)    | Configure team settings: [Backlogs](../backlogs/organize-backlog.md#activate-backlogs), [Working days](../scale/capacity-planning.md#team_settings), [Working with bugs](../customize/show-bugs-on-backlog.md)   |
| ![full screen icon](../_img/icons/fullscreen_icon.png) / ![exit full screen icon](../_img/icons/exitfullscreen_icon.png)     | Enter or exit full screen mode      |
| ![expand icon](../_img/icons/expand_icon.png) / ![collapse icon](../_img/icons/collapse_icon.png)   | Expand or collapse one level of the tree hierarchy    |
| ![mail icon](../_img/icons/mail_icon.png)  | Email a copy of your backlog      |
| ![Filter](../_img/icons/tag_filter_icon.png)  | [Turn tag filtering On/Off ](https://msdn.microsoft.com/en-us/library/dn132606.aspx)  |

Note that even if you have show parents turned on, the Create query and mail ![mail icon](../_img/icons/mail_icon.png) controls will only list items at the currently selected level. 

<a name="product-owner-role"></a>
###Role of the product owner
Product owners play an important role in Scrum, primarily as the interface between customers and the team. Their primary responsibilities include:

* Analyzing customer requirements and articulate them as user stories, features, or requirements
* Building, prioritizing, and grooming the product backlog
* Representing customer and stakeholder requirements to the team and responding to questions your team has about them
* Meeting regularly with stakeholders to address their needs and keep them informed
* Helping stakeholders understand the decisions underlying the priority order of your backlog
* Responding to any and all requests from your team for more information concerning backlog priorities and requirements

A product owner can reduce the need for detailed specifications by being more responsive to the team's questions about implementation details and clearly articulating acceptance criteria within each requirement.

<a name="estimates"></a>
###Estimation techniques
Most Agile methods recommend setting estimates for backlog items based on relative size of work. Such methods include t-shirt sizes (S, M, L, XL, and too big), powers of 2 (1, 2, 4, 8), and the Fibonacci sequence (1, 2, 3, 5, 8, etc.). You can use any method that works for your team.

[You can read more about estimates here](https://msdn.microsoft.com/library/hh765979.aspx). 

<a name="acceptance"></a>
###Acceptance criteria
Acceptance criteria define what "Done" means by describing the conditions that the team should use to verify whether a requirement or bug fix has been fully implemented. You can capture these criteria in the work item. Clear acceptance criteria help with estimating and developing requirements and with testing.

Product owners are the ultimate deciders of the criteria that create customer value.

<blockquote style="font-size: 13px"><p>**Tips from the trenches: Start to love and embrace acceptance criteria.**</p> <p>Ask 10 mature agile teams "How do you know when you're 
'<a href="http://blogs.msdn.com/controlpanel/blogs/posteditor.aspx/done%20done%20agile">done done</a>'?" 
and you'll get the same answer from each one. . . get serious about writing acceptance criteria.</p>
<p>Acceptance criteria are the handshake between the product owner and the team on what "done done" really means.  
Until the acceptance criteria are met, the team isn't done with the story. Period. 
However, the value of acceptance criteria only starts here.
</p><p>
Acceptance criteria provide the stage for some of most meaningful conversations and interactions 
that can happen on an agile team. On my own team we routinely have some of our best interactions as 
we start digging into the acceptance criteria for each story on our backlog. 
Inevitably we all start with our own ideas about what "done" means for a given story. 
</p>
<p>However, as we begin to discuss the acceptance criteria presented by the product owner what 
ensues is a series of "<a href="http://www.bing.com/search?q=Ah-ha moments">ah-ha moments</a>." 
A shared understanding of the story begins to emerge. A comment one team member might elicit 
the following response from someone else. . .  "Ah-ha, great point. . . I never thought of that."
</p><p>Regardless of who is being enlightened, the power is in the fact that the product owner and 
the team are building together a shared understanding of what "done" means for each backlog item.
And, this is happening before the team has written a single line of code. . .  before any work has been done. . .  
before commitments have been made. . .  and before the sprint has begun.</p>
<p>By collaborating on acceptance criteria the team is minimizing risk and greatly increasing the chance of delivering successfully. 
I don't think it's a coincidence that the first bullet in the 
<a href="http://agilemanifesto.org/">Agile Manifesto</a> states ". . . we have come to value 
<b>individual and interactions</b> over processes and tools".
Agile teams work together. And by working together, they create better software.</p> 
<p>Start learning to love acceptance criteria and see if your team isn't more successful delivering software.</p>

<p>--Aaron Bjork, Principal Product Manager, Visual Studio Cloud Services, first published in the 
blog post: <a href="http://blogs.msdn.com/b/aaronbjork/archive/2010/05/04/msf-agile-5-0-tip-5-learn-to-love-acceptance-criteria.aspx">
Agile Tip #5 – Learn to Love Acceptance Criteria</a></p> </blockquote>  


[You can read more about acceptance criteria here](http://blogs.msdn.com/b/aaronbjork/archive/2010/05/04/msf-agile-5-0-tip-5-learn-to-love-acceptance-criteria.aspx).

<a name="spikes"></a>
###Capture and manage spikes
In addition to new features and requirements to build, you can capture non-feature work that still needs to be done for a healthy ecosystem of delivery. This work can include necessary research, design, exploration, or prototyping. Any work done that doesn't directly lead to shippable software can be considered and captured as a spike.

As the need to perform this work arises, capture it along with other items on your backlog. 

[You can read more about spikes here](http://www.scaledagileframework.com/spikes/).

###Treat bugs like requirements or tasks
You have a choice as to how you want to manage bugs. Some teams like to track bugs along with requirements on the backlog. Other teams like to track bugs as tasks performed in support of a requirement, and have them appear on their [task board](../scrum/task-board.md).

If you're using the Scrum process, your default setup is to track bugs along with PBIs. However, if you're working in a team project based on the [Agile or CMMI processes](../guidance/choose-process.md), bugs don't automatically appear on your backlog.

Talk with your team to determine how they want to manage bugs and then [change your team settings](../customize/show-bugs-on-backlog.md) accordingly.

<a name="manage-impediments"></a>
###Manage impediments
If you have known issues you want to track, you can do so by defining an impediment or issue. 

![Create a new impediment](_img/ALM_CB_CreateImpediments.png)

Impediments don't appear on your backlog. Instead, you track them using [queries](../track/using-queries.md).

Don't confuse impediments with bugs. You track impediments that may cause problems with delivering one or more requirements. For example, you may have to address feature ambiguity, personnel or resource issues, problems with environments, or other risks that impact scope, quality, or schedule. Other issues that deserve tracking are decisions that require several stakeholders or product teams to weigh in on.
Impediments and issues represent unplanned activities. Resolving them requires more work beyond what's tracked for actual requirements. Using the impediment work item type helps you track and manage these issues until you can resolve and close them.



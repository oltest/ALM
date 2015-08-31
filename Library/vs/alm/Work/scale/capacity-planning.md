Title: Capacity planning | Visual Studio Online and TFS
Description: Set or copy team member capacity to plan your Scrum sprints when when working from Visual Studio Online or Team Foundation Server
ms.TocTitle: Capacity planning
ms.ContentId: F9DC4D34-36D6-42D6-AA8F-E7FE1CC60676


#Capacity planning
How much work can your team accomplish in a sprint? Using the capacity planning tools, your team can estimate both the amount of work and types of work required to complete their sprint plan. Then, during the sprint, you can [monitor the capacity bars](../scrum/sprint-planning.md#adjust-work) to determine when an individual team member or a team area of activity is on target to finish, or needs help from other team members to finish. 

[Sprint planning](../scrum/sprint-planning.md#set-capacity) introduced the basics of setting your team capacity. Here, we go into more detail to address how to:  

- Copy capacity from the previous sprint to the current sprint  
- Track capacity when performing multiple activities  
- Track capacity when working on more than one team  


<a id="set-capacity">  </a>

##Set team capacity and activity

Capacity correlates to actual task time - either hours or days. Capacity takes into account variation in work hours by team members as well as holidays, vacation days, and non-working days. 

Because days off and time available for each team member can vary from sprint to sprint, you set capacity for each sprint. The capacity tool helps you make sure your team isn't over or under committed for the sprint. Also, as you work day-to-day, you'll be able to see if your team is on track.

From the Capacity page, enter the capacity and days off for each member of your team. If your team tracks capacity by activity, then also select the Activity for each team member.  

For example, Christie Church's capacity is 6 hours hours/day for design work.

 ![Capacity](_img/set-sprint1-capacity.png)

Most teams specify capacity in terms of hours, however, you can also specify it in days. For example, .5 days would correspond to 4 hours for a typical 8 hour day. Choose the same unit you will use to estimate the time a task will take to complete.

If you haven't set up sprints yet for your team, go [here to do that now](../scrum/define-sprints.md).

If you don't see a team member listed, you need to [add them to the team](../scale/manage-team-assets.md#add-team-admin). Also, you only have to indicate planned days off for the team. You [set weekend days or other recurring days off](#team_settings) under team settings.  

<a id="copy-capacity">  </a>
##Copy capacity planning from the previous sprint
By copying the capacity from the previous sprint, you save time. With the basics defined, all you have to do is adjust the capacity based on individual and team days off and capacity allocation per activity.  

For example, here we choose Sprint 2 and copy the capacity set for Sprint 1. 

![Copy capacity from the previous iteration](_img/copy-capacity-from-previous-sprint.png)

Notice that only the capacity per day and activity are copied over. Individual and team days off remain unset. The copy operation always copies the latest updates made to the previous sprint. So you can repeat the copy operation if you've made changes to the previous sprint that you want to copy to the latest sprint. 

<a id="track-multiple-activities">  </a>
##Track capacity when performing multiple activities

Because individual team members have different sets of skills and duties, you can track their activity and capacity for each activity and for each sprint. 

Here, Jamal divides his time between Deployment and Development. 

![Add activity to capacity tracking for an individual](_img/add-activity-to-capacity-planning.png)

<a id="track-capacity-per-team">  </a>
##Track capacity when working on more than one team
If you work on more than one team, you'll want to switch between teams easily and specify your sprint capacity to support each team's sprint activities.  

###Switch your team view
Switch to another team when you work on items for that team. From the web portal, choose Browse All if the name you want doesn't appear.  

![Choose another team from the team project menu](_img/vso-team-selector.png)  

###Specify sprint capacity for each team you work on
If you work on more than one team during a sprint cycle, you'll probably allocate some percentage of your time to each team.  

For example, both Christie and Raisa split their time between the Web and Phone teams. They therefore allocate 3 hours a day to the Web team, and 3 hours a day to the Phone team.  
![Allocate capacity for team Web](_img/set-capacity-web-team.png)  
 
![Allocate capacity for team Phone](_img/set-capacity-phone-team.png)  
 
If your name isn't listed in the capacity view, you need to be added as a team member. 

##Related Scrum notes
Setting capacity and [estimating remaining work for each task](../scrum/sprint-planning.md#define-tasks) provides you with the tools you need to track the amount of work and resources you have allocated sprint over sprint. You can learn more about working with your Scrum tools from these topics:

- [Task board](../scrum/task-board.md)
- [Sprint burndown](../scrum/sprint-burndown.md)
- [Velocity & forecasting](../scrum/velocity-and-forecasting.md)

<a id="customize-activity-list">  </a>
###Customize the pick list of activities or discipline

You can add to or modify the items listed for the [Activity](https://msdn.microsoft.com/en-us/library/dd997792%28v=vs.140%29.aspx) (Agile or Scrum) or [Discipline](https://msdn.microsoft.com/en-us/library/dd997792%28v=vs.140%29.aspx) (CMMI) field by [customizing its pick list](https://msdn.microsoft.com/en-us/library/ms194947%28v=vs.140%29.aspx). 

<blockquote style="font-size: 13px">**Note:  **  The set of values listed corresponds to the combined set of all values defined for the field across all team projects in the collection. </blockquote>  
 
<a id="team_settings">  </a>

###Set recurring days off  
Your sprint planning and tracking tools automatically consider days off when calculating capacity and sprint burndown. Leave those days of the week that your team doesn’t work unchecked in your team’s settings page. 

If you're not a team administrator, [get added as one](../scale/manage-team-assets.md#add-team-admin). Only team and project admins can change team settings. 

####Visual Studio Online
Open the Settings dialog from the Capacity page to set Working days. 

![Settings, Working days ](_img/open-team-settings.png)

####On-premises TFS
Open your team settings from the Overview tab of your team’s admin context.  

![Team settings page for default working days](_img/ALM_DS_WorkingDaysOff.png)
 
 
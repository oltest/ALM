Title: Before you upgrade TFS | Team Foundation Server
Description: Learn what steps you need to take when upgrading from earlier versions of TFS to the latest version  
ms.TocTitle: Before you upgrade TFS
ms.ContentId: F52E3DB7-4A62-4BD2-8C6F-CC44CC09464D

*This topic applies only to team projects hosted on an on-premises Team Foundation Server (TFS). Team projects on Visual Studio Online [update automatically with each service upgrade](https://www.visualstudio.com/news/release-archive-vso).  * 

#Before you upgrade TFS  
Each version of Team Foundation Server (TFS) typically introduces one or more changes to work item tracking. To gain access to the new features that rely on these changes, your existing team projects must be updated. 

The Configure Features wizard is designed to make the update process pain free, however, customized team projects may prevent the wizard from being successful. Also, depending on the TFS version you're upgrading from, you may need to take additional actions as summarized below.  


<table>
<tbody valign="top">
<tr>
<th width="25%">
<p>Upgrade path </p>
</th>
<th width="75%">
<p>Recommended steps</p>
</th>
</tr>
<tr>
<td>
<p>TFS 2012 or TFS 2013<br/> to TFS 2015</p>
</td>
<td>
<ol>
<li>[Upgrade your TFS instance to TFS 2015](../../TFS/upgrade/upgrade.md).   </li> 
<li>[Run the Configure Features Wizard](configure-features-after-upgrade.md).</li> 
<li>[Perform additional configurations](additional-configuration-options.md).</li> 
</ol>
</td>
</tr>

<tr>
<td>
<p>TFS 2008 or TFS 2010<br/>to TFS 2015</p>
</td>
<td>
<b>Option 1:</b><br/>
<ol>
<li>[Upgrade your TFS instance to TFS 2012 by downloading the TFS 2012 ISO](http://go.microsoft.com/fwlink?linkid=255990).</li> 
<li>[Run the Configure Features Wizard](configure-features-after-upgrade.md).</li> 
<li>[Update a Team Project Based on an MSF v4.2 Process Template](https://msdn.microsoft.com/library/ff452591.aspx).</li> 
<li>[Upgrade your TFS instance to TFS 2015](../../TFS/upgrade/upgrade.md).   </li> 
<li>[Run the Configure Features Wizard](configure-features-after-upgrade.md).</li> 
<li>[Perform additional configurations](additional-configuration-options.md).</li> 
</ol>
<b>Option 2:</b><br/>
<ol>
<li>[Upgrade your TFS instance to TFS 2015](../../TFS/upgrade/upgrade.md).   </li> 
<li><p>Manually update your team project:</p>
<ul>
<li>[Update a Team Project Based on an MSF v4.2 Process Template](https://msdn.microsoft.com/library/ff452591.aspx).</li> 
<li>[Update the Workflow for Agile Team Projects](https://msdn.microsoft.com/library/hh500412.aspx).</li> 
<li>[Apply updates manually based on the features you want to enable](add-features-manually.md).</li> 
</ul>
</li>
<li>[Perform additional configurations](additional-configuration-options.md).</li> 
</ol>
</td>
</tr>
</tbody>
</table>


<a id="earlier-versions">  </a> 

##Updating team projects based on earlier versions of MSF process templates 
If you upgrade your TFS instance to TFS 2015 and your existing team projects were created with MSF version 5.0 or earlier process templates, you may have to apply a few updates manually. Two specific problems can occur having to do with a missing field or workflow state.  

###Value Area field missing   
The following message reported by the Configure Features wizard indicates that the Value Area field is missing from either the User Story or Requirement WIT definition:  

```
[Error] TF400654: Unable to configure Planning Tools. The following element contains an error: RequirementBacklog/Columns. TF400529: This element defines the columns that appear on the backlog. You must set all values to fields that exist in at least one of the work item types belonging to the category. The following fields do not exist in any of the work item types: Microsoft.VSTS.Common.ValueArea.
```

You can resolve this error by (1) adding the following syntax to the ```FIELDS``` section of the User Story or Requirement definition:
```
<FIELD name="Value Area" refname="Microsoft.VSTS.Common.ValueArea" type="String">
   <REQUIRED />
   <ALLOWEDVALUES>
     <LISTITEM value="Architectural" />
     <LISTITEM value="Business" />
   </ALLOWEDVALUES>
   <DEFAULT from="value" value="Business" />
   <HELPTEXT>Business = delivers value to a user or another system; Architectural = work to support other stories or components</HELPTEXT>
</FIELD>
```

and the following syntax to the ```FORM``` section:
```
<Control FieldName="Microsoft.VSTS.Common.ValueArea" Type="FieldControl" Label="Value area" LabelPosition="Left" />
```

Or (2) removing the following entry from the ProcessConfiguration ```RequirementBacklog``` section: 
```
<Column refname="Microsoft.VSTS.Common.ValueArea" width="100" />
```

See [Add features using a manual update process](add-features-manually.md) for more information about updating these files manually. 


###New workflow state missing 
The following message reported by the Configure Features wizard indicates that the New workflow state is missing for the Bug WIT definition:  

**[Error] TF400654: Unable to configure Planning Tools.** The following element contains an error: BugWorkItems/BugWorkItems. TF400506: This element defines the states for work items that represent Bugs or Defects. Each state must exist in at least one of the work item types that are defined in: BugWorkItems. The following states do not exist in any of the work item types: New.


To resolve this error, you must add the New workflow state to the Bug definition as described in [Add features using a manual update process](add-features-manually.md). 


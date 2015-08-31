Title: Manage process templates | Team Foundation Server
Description: Upload, download, and delete a process template for a team project collection - Team Foundation Server
ms.TocTitle: Manage process templates
ms.ContentId: 5D5AF176-B3C6-47AD-87FF-5FAFE1BA4AAE

*This topic applies only to team projects hosted on an on-premises Team Foundation Server (TFS). To import, export, or update a process to customize a team project hosted on Visual Studio Online, see [Import process](../import-process/import-process.md).* 

#Upload or download a process template

Visual Studio Team Foundation Server (TFS) uses process templates to create team projects. 

You can upload, download, and delete process templates for a team project collection. Also, you can mark a template to appear as the default in the New Team Project Wizard. For a comparison of the default process templates TFS provides -- Agile, CMMI, and Scrum -- see [Choose a process](choose-process.md). 

<blockquote style="font-size: 13px"><b>Tip:  </b>To access the latest versions of the default process templates, install the latest version of [Visual Studio Team Foundation Server](https://www.visualstudio.com/downloads/download-visual-studio-vs). You may want to do this in order to manually add features and functionality to a team project that has been upgraded to the latest version of TFS. <br/>
You can access the latest versions of the default process templates installed on TFS here: %programfiles%/Microsoft Team Foundation Server 14.0/Tools/Deploy/ProcessTemplateManagerFiles/1033. For descriptions of each file and folder, see [Overview of process template files](https://msdn.microsoft.com/library/ms243856%28v=vs.140%29.aspx). </blockquote>  

To customize a process template, you first download it. After you’ve customize the files contained within the process template folder, you upload the new version to the team project collection. To learn how to customize process templates, see [Customize a process template](https://msdn.microsoft.com/library/ms243782%28v=vs.140%29.aspx).  



##To manage a process template 

1.	Open the same version of Visual Studio or Team Explorer as the on-premises TFS that you connect to. For example, if you connect to a TFS 2015 instance, you must connect from Visual Studio 2015 or Team Explorer 2015.  

	You can always download a free version of Team Explorer from the [Visual Studio download site](https://www.visualstudio.com/downloads/download-visual-studio-vs).  

	If you aren’t a member of the Project Collection Administrators group, [get added as one](https://msdn.microsoft.com/library/dd547204%28v=vs.140%29.aspx).  

2.	Open the Process Template Manager from the **Team, Team Project Collection Settings** menu.

	![Open Process Template Manager](_img/open-process-template-manager.png)

	You’ll see a list of each process template that has been uploaded to the team project collection. 

	![Select process template to work with](_img/process-template-manager.png)

	The <b>Upload</b>, <b>Download</b>, <b>Make Default</b>, and <b>Delete</b> buttons are disabled when you don’t have the necessary permissions to manage process templates. 
 
3.	Select the process template that you want to work with and then choose from the following actions.  

<table>
<tbody valign="top">
<tr>
<td width="15%">
**Upload**
</td>
<td>To upload a process template.<br/>
<p>In the **Upload Process Template** dialog box, choose the folder that contains the root file, ProcessTemplate.xml, for the process template that you want to upload. See also [Process template restrictions and validation checks](#restrictions).</p>
</td>
</tr>

<tr>
<td>
**Download**
</td>
<td>To download the process template to a local computer.<br/>
<p>In the **Download Process Template** dialog box, select a folder where the process template will be downloaded.</p>
<p>If you're downloading a process template to use to [configure new features](../customize/configure-features-after-upgrade.md), [manually add new features](../customize/add-features-manually.md) or [update a custom process template to enable new features](../customize/update-customized-process-template.md)--choose the process that corresponds to the one you used previously to create your team project. For example, if you're updating a team project based on the Scrum process template, then select **Scrum**. Note that all version numbers have been removed from the process templates. If you don't see Agile, CMMI, or Scrum, then you need to [update TFS](https://www.visualstudio.com/downloads/download-visual-studio-vs). </p>
<p>You can determine which process template to select based on the [work item types defined for your existing team project](#wit_correlation).</p>
</td>
</tr>

<tr>
<td>
**Make Default**
</td>
<td>
To cause the selected process template to appear as the default selection in the **New Team Project Wizard**.
</td>
</tr>

<tr>
<td>
**Delete**
</td>
<td>
To permanently remove the selected process template from the collection.
</td>
</tr>

</tbody>
</table>


<a id="wit_correlation"> </a>

##Process template correlation with an existing team project
<p>To determine the type of process template that was used to create your team project, review the work item types that appear in the <b>New Work Item</b> menu for Team Explorer and then compare them with the work item types in the following chart. If your work item types differ from those shown listed, then a custom process template might have been used.</p>

<table>
<tbody valign="top">
<tr>
<th>Scrum</th>
<th>Agile</th>
<th>CMMI</th>
</tr>
<tr>
<td>
![Scrum work item types](_img/ALM_MPT_WIT_Scrum.png) 
</td>
<td>
![Agile work item types](_img/ALM_MPT_WIT_Agile.png) 
</td>
<td>
![CMMI work item types](_img/ALM_MPT_WIT_CMMI.png) 
</td>
</tr>
</tbody>
</table>

<a id="restrictions"> </a>

##Process template restrictions and validation checks 
Uploading a process template requires that it pass the following validation checks:  

- Process template names must be unique and 256 Unicode characters or less. Same-named templates will overwrite existing templates.<br/>
Also, names cannot contain the following characters: . , ; ' ` : / \ * | ? " &amp; % $ ! + = ( ) [ ] { } &lt; &gt;<br/>
For additional restrictions, see [Naming restrictions](../customize/naming-restrictions.md). 
- Process template folders can’t contain any .exe files. If they do, the process template may upload successfully, however project creation will fail.
- Process template total size should be 2 GB or less, or project creation will fail.
- The upload process performs a partial verification check to make sure that the XML of each process template XML file is valid. If you receive any errors when you try to upload the process template, review the XML to determine the cause of the error. Note that duplicate tags in an XML file can cause errors. If there is no error in the XML, check to make sure all the appropriate files are included in your process template in the correct folder locations.

<blockquote style="font-size: 13px"><b>Important:  </b>The schema definition for process templates uses a mix of camel-case and all capitalized elements. If you encounter errors when validating your type definition files, check the case structure of your elements. Also, the case structure of opening and closing tags must match according to the rules for XML syntax. See [Process template plug-ins: Index to XML element definitions](https://msdn.microsoft.com/library/aa395287.aspx).  </blockquote>  

##Related notes  

Periodically, updates are made to the process templates to support new features which have been cataloged [here](changes-to-process-templates.md).

###Update a process template to enable new features 
When you upgrade your on-premises TFS to a later version, new features may become available. [To gain access to these new features](../customize/configure-features-after-upgrade.md), you may need to [update a customized process template](../customize/update-customized-process-template.md). 

###Add another team project 
You can add a team project using the [New Team Project Wizard](https://msdn.microsoft.com/library/ms181477.aspx). The New Team Project Wizard runs the set of instructions contained within the process template files to configure initial settings and upload artifacts and template files. 

###Import a process when you work in Visual Studio Online  
To import, export, or update a process to customize a team project hosted on Visual Studio Online, see [Import process](../import-process/import-process.md). 



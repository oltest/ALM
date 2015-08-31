Title: Differences between cloud and on-premises process customizations | Visual Studio Online
Description: Summary of what you can and can't customize in a process template to support customized work tracking in Visual Studio Online.
ms.TocTitle: Differences between cloud and on-premises process customizations
ms.ContentId: 2B500AEA-165C-428D-B580-C9C0A8D01635

<span style="color:red; font-size:1.1em;">*[Import process](import-process.md) is in preview and available through request only. Contact [Visual Studio Online Process Customization](mailto:vsocustpt@microsoft.com) to request access.*  </span>

# Differences between Visual Studio Online and TFS process template customizations

Visual Studio Online uses a different model for relating projects and process.  
* In Team Foundation Server, process templates are used as starting points for projects and once a project is created, the project is the scope you customize.
* In Visual Studio Online, process is shared across multiple projects and is the scope you customize.  
 
The structure and overall syntax used in defining process templates remains the same, with only a few minor differences existing between templates 
you customize for import into Visual Studio Online and those you upload to support an on-premises TFS.  

## Unsupported customizations and unreferenced plug-in files

Custom link types and global lists aren't supported in Visual Studio Online at this time. 
Any reference to these objects in any of the WIT definition files will result in a validation error upon import.  
*   Custom controls on work item forms
*   Custom link types  
*   Global lists
*   Global workflow

The following plug-ins and their associated files aren't used in defining a process, nor used to update existing team projects. 
However, they are used to create objects or artifacts when you create a new team project.  
*   Classification      
*   Queries   
*   Test Management
*   Work items  

The following plug-ins and their associated files are replaced by system defaults.  
*   Build    
*   Groups and Permissions
*   Lab  
*   Version Control   

The following plug-ins and their associated files are ignored.  
*   Microsoft Project Mappings
*   Reports  
*   Windows SharePoint Services  

Custom plug-ins aren't supported. 

## Object limits 
When customizing a process template for import, limit the number of the following objects you define.  
*   64 WITs   
*   256 fields per WIT
*   16 workflow states per WIT     
*   16 person-name fields    
*   1024 rules per field   
*   128 pick list values per field   
*   512 fields per account/collection     
*   5 portfolio backlogs  
*   32 categories                                                                                                                                         

## Unsupported tools
The following tools aren't supported when you connect to Visual Studio Online.   
*   Process Editor power tool  
*   Visual Studio Process Template Manager (exception: download a process template is supported)   
*   witadmin command line tool (only works when connected to an on-premises TFS)  


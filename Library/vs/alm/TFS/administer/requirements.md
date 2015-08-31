Title: Requirements and Compatibility | Team Foundation Server Setup, Upgrade and Administration
ms.TocTitle: Requirements
Description: Describes the hardware, operating systems, SQL Server and other requirements for TFS and compatibility. Also describes compatibility between versions of TFS clients with versions of the server. 
ms.ContentId: 12652666-b74e-4fd8-aab1-d87cbba6b820
toc: show

# Requirements and compatibility

## Operating systems

TFS can be installed on a Windows server or client operating system.
We recommend using a server OS unless your TFS instance is for evaluation or personal use.

### Server operating systems
  
TFS Version | Supported server operating systems
------------|--------------------------------
TFS 2015    | Windows Server 2012 R2 (Essentials, Standard, Datacenter)<br/>Windows Server 2012<br/>Windows Server 2008 R2 (minimum SP1) (Standard, Enterprise, Datacenter)
TFS 2013    | Windows Server 2012 R2 (Essentials, Standard, Datacenter)<br/>Windows Server 2012<br/>Windows Server 2008 R2 (minimum SP1) (Standard, Enterprise, Datacenter)
TFS 2012    | Windows Server 2012 R2 (Essentials, Standard, Datacenter)<br/>Windows Server 2012<br/>Windows Server 2008 R2 (Standard, Enterprise, Datacenter)<br/>Windows Server 2008 (minimum SP2)<br/>Windows Small Business Server 2011 (Standard, Essentials, Premium Add-On)<br/>Windows Home Server 2011
TFS 2010    | Windows Server 2008 R2 (Standard, Enterprise, Datacenter)<br/>Windows Server 2008 (minimum SP2)<br/>Windows Server 2003 R2<br/>Windows Server 2003 (minimum SP2)

Don't use the [server core](https://msdn.microsoft.com/library/dd184075.aspx) installation option when you set up Windows Server for TFS. It's not supported.

### Client operating systems

TFS Version | Supported client operating systems
------------|--------------------------------
TFS 2015    | Windows 10 (Home, Professional, Enterprise)<br/>Windows 8.1 (Basic, Professional, Enterprise)<br/>Windows 8<br/>Windows 7 (minimum SP1) (Home Premium, Professional, Enterprise, Ultimate)
TFS 2013    | Windows 8.1 (Basic, Professional, Enterprise)<br/>Windows 8<br/>Windows 7 (minimum SP1) (Home Premium, Professional, Enterprise, Ultimate)
TFS 2012    | Windows 8.1 (Basic, Professional, Enterprise)<br/>Windows 8<br/>Windows 7 (Home Premium, Professional, Enterprise, Ultimate)
TFS 2010    | Windows 8<br/>Windows 7 (Home Premium, Professional, Enterprise, Ultimate)<br/>Windows Vista SP2

While TFS supports installation on client OSes, we don't recommend this except for evaluation purposes or personal use.
TFS installations on client OSes don't support integration with SharePoint products or reporting.
The TFS proxy can't be installed on client OSes. If you need to use any of these features, install TFS on a server OS. 

## Virtualization

Microsoft supports the virtualization of Team Foundation Server in supported virtualization environments.
For more information, see the following pages on the Microsoft website:

* [Microsoft server software and supported virtualization environments](http://go.microsoft.com/fwlink/?LinkId=196061)
* [Support policy for Microsoft software running in non-Microsoft hardware virtualization software](http://go.microsoft.com/fwlink/?LinkId=196062)
* [Support partners for non-Microsoft hardware virtualization software](http://go.microsoft.com/fwlink/?LinkId=196063)
* [Server Virtualization](http://go.microsoft.com/fwlink/?LinkId=196072) (officially supported products)

## SQL Server

Use one of the following versions of SQL Server for TFS:

TFS version        | Support SQL Server version
-------------------|------------------------------------
TFS 2015           | SQL Server 2014<br/>SQL Server 2012 (minimum SP1)
TFS 2013 Update 2  | SQL Server 2014<br/>SQL Server 2012 (minimum SP1)
TFS 2013           | SQL Server 2012 (minimum SP1)
TFS 2012           | SQL Server 2012<br/>SQL Server 2008 R2
TFS 2010           | SQL Server 2008 R2<br/>SQL Server 2008

SQL Server 2014 has increased hardware requirements compared with previous versions.
Certain configurations might hurt TFS performance.
For more information, read [TFS 2013 Update 2: performance considerations using SQL Server 2014](http://support.microsoft.com/kb/2953452).

If you're using SQL Server 2012 with SP1,
we recommend you also apply [cumulative update 2](http://support.microsoft.com/kb/2790947)
on top of SP1 to address a critical SQL Server bug around resource consumption.
This isn't a requirement because the bug only affects a small number of instances,
but we wanted you to be aware of it.
If you don't apply CU2, you should apply a SQL Server hotfix ([KB2793634](http://support.microsoft.com/kb/2793634))
to addresses another (different) issue where SQL Server 2012 with SP1 might request an excessive amount of restarts.

### SQL Server editions

TFS supports Express, Standard, and Enterprise [editions of SQL server](http://www.microsoft.com/en-us/server-cloud/products/sql-server-editions/).
The Express edition is only recommended for evaluation purposes, personal use, or for very small teams.
We recommend Standard or Enterprise for all other scenarios.

## SharePoint

TFS Version | Supported SharePoint versions
------------|------------------------------
TFS 2015    | SharePoint 2013 (Foundation, Standard, Enterprise)<br/>SharePoint 2010 (Foundation, Standard, Enterprise)
TFS 2013    | SharePoint 2013 (Foundation, Standard, Enterprise)<br/>SharePoint 2010 (Foundation, Standard, Enterprise)
TFS 2012    | SharePoint 2013 (Foundation, Standard, Enterprise)<br/>SharePoint 2010 (Foundation, Standard, Enterprise)<br/>Office SharePoint Server 2007 (Standard, Enterprise)<br/>Windows SharePoint Services 3.0
TFS 2010    | Office SharePoint Server 2007 (Standard, Enterprise)<br/>Windows SharePoint Services 3.0

To use SharePoint with TFS, your SharePoint server has to have the TFS extension for SharePoint Projects configured.
You can configure the TFS extension for SharePoint Products on your SharePoint server 
from the TFS administration console where you installed TFS.

## Project Server

TFS Version | Supported Project Server versions
------------|------------------------------
TFS 2015    | Project Server 2013<br/>Project Server 2010 (minimum SP1)
TFS 2013    | Project Server 2013<br/>Project Server 2010 (minimum SP1)
TFS 2012    | Project Server 2013<br/>Project Server 2010 (minimum SP1)<br/>Project Server 2007 (minimum SP2)
TFS 2010    | Project Server 2007 (minimum SP2)

## Major releases and service packs

We don’t always immediately support major new versions of our dependencies (like SQL Server)
because we sometimes have to do updates to add support for those versions. 
However, once we support a major version, we always support the latest service pack – immediately when it releases. 
We work with those teams to test it before the service packs release.

## Hardware recommendations

[!INCLUDE [HARDWARE_REQUIREMENTS](../_shared/hardware-requirements.md)]

### Build service hardware requirements

The build service has the same operating system requirements as TFS.
Sometimes it makes sense to run the build service on a machine separate from the TFS application tier.
Hardware requirements for the build service are the same as the operating system on which it is running.
However, you can optimize build service performance by tailoring the hardware specs
of your build machine to the types of builds your team will use.

<!-- For more information, see System requirements for Team Foundation Build Service  -->

### SharePoint hardware requirements

If you install SharePoint Products,
you will need more robust hardware than what is listed in the previous table.
For example, SharePoint Foundation 2013 requires a 64-bit 4 core CPU and a base minimum of 8 GB of system memory.
If you install SharePoint 2013 on a server that is also running SQL Server,
SharePoint recommends that you have 24 GB of system memory.

Go here for complete SharePoint hardware requirements:

* [Hardware and software requirements for SharePoint 2013 (SharePoint Foundation 2013/SharePoint Server 2013)](https://technet.microsoft.com/library/cc262485.aspx)
* [Hardware and software requirements (SharePoint Foundation 2010)](http://go.microsoft.com/fwlink/?LinkId=231850)
* <a href="https://technet.microsoft.com/library/cc262485(v=office.14).aspx">Hardware and software requirements (SharePoint Server 2010)</a>

<!-- For a complete list of supported versions of SharePoint, go here: SharePoint Products Requirements for Team Foundation Server -->

## Client compatibility

### Visual Studio

We define three levels of client support for different versions of Visual Studio and Team Explorer.
Only the latest version has "full" compatibility with the latest Team Foundation Server,
because this will be the only client that contains components that can interface with new features for that release,
and will also be the only client from which you can perform certain administrative tasks such as creating new team projects.
Previous versions will have varying levels of support below that, depending on how old they are.

Next, we describe the level of support that we guarantee with each client version.
Keep in mind that additional functionality other than what is listed below might continue to work using older clients. In fact,
it often does, but is outside the scope of what we test and support officially.

Visual Studio/ Team Explorer version | TFS 2015 support notes                                                                              | TFS 2013 support notes                                                                              | TFS 2012 support notes                                                                     | TFS 2010 support notes
-------------------------------------|-----------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-----------------------
Visual Studio 2015                   | Supported (RTM or latest update)                                                                    | Supported (RTM or latest update)                                                                    | Supported (RTM or latest update)                                                           | Supported (RTM or latest update)
Visual Studio/Team Explorer 2013     | Supported (RTM or latest update)                                                                    | Supported (RTM or latest update)                                                                    | Supported (RTM or latest update)                                                           | Supported (RTM or latest update)
Visual Studio/Team Explorer 2012     | Requires latest Visual Studio 2012 update. Supports Git with Visual Studio Tools for Git extension. | Requires latest Visual Studio 2012 update. Supports Git with Visual Studio Tools for Git extension. | Supported (RTM or latest update). Supports Git with Visual Studio Tools for Git extension. | Supported (RTM or latest update). Supports Git with Visual Studio Tools for Git extension.
Visual Studio/Team Explorer 2010     | Requires SP1 and Compat GDR.                                                                        | Requires SP1 and Compat GDR.                                                                        | Requires SP1 and Compat GDR.                                                               | Requires SP1 and Compat GDR.
Visual Studio/Team Explorer 2008     | Version Control available using MSSCCI Provider                                                     | Version Control available using MSSCCI Provider                                                     | Requires SP1 and Compat GDR.                                                               | Version control officially supported with MSSCCI Provider. Version control unofficially supported with SP1 and Compat GDR.
Visual Studio 2005                   | Version Control available using MSSCCI Provider                                                     | Version Control available using MSSCCI Provider                                                     | Version Control available using MSSCCI Provider                                            | Version Control available using MSSCCI Provider

#### Full-featured support

Any TFS-facing functionality exposed in the UI of Visual Studio and Team Explorer should work.
We guarantee full feature support between client and server of the same version.

Note: If you are using the latest version of Visual Studio,
but will continue to use the most recent previous version of Team Foundation Server (either temporarily or permanently),
you can expect a high level of compatibility here as well.
All non-administrative scenarios will be supported. 

#### High level of support

If you are running the most recent previous version of Visual Studio or Team Explorer
(for example: Visual Studio 2012, if you are on TFS 2013),
then you can expect most features to be supported from Visual Studio.
You might need to install the latest update,
but after doing so, mainline scenarios for all non-admin personas will be supported.
This includes features needed for developers and testers to continue their daily work,
such as queuing builds, running queries, viewing documents, and getting, editing, and checking in files.
Program Managers should also be able to continue using most features relevant to them,
but might need to rely on web access for some scenarios, such as managing areas and iterations, and writing new queries.

Older process templates that were in use with the previous version of Team Foundation Server should continue to be compatible with the new server.

#### General support

If a client is two versions older than your server, you can expect general support (after installing a compatibility GDR).
This will look similar to the high level of support you see when Visual Studio is one release older than TFS;
however, the experience for some non-mainline scenarios may be degraded but not entirely blocked.
Non-admins should still be able to continue unimpeded in their daily work,
and older process templates should remain compatible with the new server.

#### MSSCCI support

Visual Studio/Team Explorer 2008 and Visual Studio 2005 are no longer officially supported.
To connect to the server, these clients must interface through the MSSCCI provider instead.
MSSCCI support only includes support for source control integration and MSSCCI commands.
The goal is simply to allow developers to continue working with legacy applications in an upgraded server.

### Team Explorer Everywhere

A new version of Team Explorer Everywhere is released with each version of TFS.
You should try to use the version of Team Explorer Everywhere that corresponds to the version of your Team Foundation Server;
however, recent versions of Team Explorer Everywhere have had forward and backward compatibility with all versions of TFS.
If you need support for an older version of Eclipse, Java, or an Operating System,
you may choose to use an older version of Team Explorer Everywhere that encompasses the range you need.
Multiple versions of Team Explorer Everywhere can also be installed side-by-side if you are running multiple versions of Eclipse.

The following table includes all versions of Team Explorer Everywhere that are compatible with TFS 2013, and lists other TFS and Eclipse compatibility.

Team Explorer Everywhere          | Eclipse version | TFS 2015                    | TFS 2013                    | TFS 2012                    | TFS 2010                    | TFS 2008                    | TFS 2005
----------------------------------|-----------------|-----------------------------|-----------------------------|-----------------------------|-----------------------------|-----------------------------|-----------------
Team Explorer Everywhere 2013     | Eclipse 3.5-4.3 | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![x](../_img/x.png)         | ![x](../_img/x.png)
Team Explorer Everywhere 2012     | Eclipse 3.4-4.3 | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png)
Team Explorer Everywhere 2010 SP1 | Eclipse 3.2-3.6 | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png)
Team Explorer Everywhere 2010     | Eclipse 3.0-3.5 | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png) | ![Check](../_img/check.png)

### Browsers

The following browsers are supported when accessing TFS using the web client.

TFS Version | Edge        | Internet Explorer | Safari (Mac) | Firefox     | Chrome
------------|-------------|-------------------|--------------|-------------|-------
TFS 2015    | most recent | 9 - 11            | 5-7          | most recent | most recent
TFS 2013    |             | 9 - 11            | 5-7          | most recent | most recent

Because Edge, Firefox, and Chrome automatically update themselves, TFS supports the most recent version of each.

### Office

TFS Version | Supported Office versions
------------|--------------------------
TFS 2015    | Office 2013<br/>Office 2010<br/>Office 2007
TFS 2013    | Office 2013<br/>Office 2010<br/>Office 2007
TFS 2012    | Office 2010<br/>Office 2007
TFS 2010    | Office 2010<br/>Office 2007

* If you are using SharePoint with TFS, you will need to add SP2 to Office 2007 and SP1 to Office 2010 for integration between Office and SharePoint. 
* SharePoint 2010 does not support Office 2013.

## TFS Build Compatibility

We've built a brand new scriptable build system that's web based and cross-platform. See
[here](../../Build/overview.md) for more information.

You may want to use an older version of Build if you plan to continue using the Xaml build system, 
if you are using Build servers against multiple versions of TFS, or if you need to leverage servers 
with older operating systems in your TFS deployment. TFS 2010 Xaml Controllers support operating 
systems as far back as Windows XP and Windows Server 2003.

TFS Version | Supported Build versions
------------|--------------------------
TFS 2015    | TFS 2015 Build Agent<br/>TFS 2015 Xaml Controller<br/>TFS 2013 Xaml Controller<br/>TFS 2010 Xaml Controller
TFS 2013    | TFS 2013 Xaml Controller<br/>TFS 2012 Xaml Controller<br/>TFS 2010 Xaml Controller
TFS 2012    | TFS 2012 Xaml Controller<br/>TFS 2010 Xaml Controller
TFS 2010    | TFS 2010 Xaml Controller

## More information about TFS requirements for companion products:

SQL Server, SharePoint Products, and Project Server

* [SQL Server requirements for Team Foundation Server](https://msdn.microsoft.com/en-us/library/dd631889.aspx)
 
	Team Foundation Server requires SQL Server, but you have many options,
	including an option to let Team Foundation Server install SQL Server Express for you.

* [SharePoint Products requirements for Team Foundation Server](https://msdn.microsoft.com/en-us/library/hh667648.aspx)  

	Team Foundation Server doesn't require SharePoint Products.

* [Project Server requirements for Team Foundation Server](https://msdn.microsoft.com/en-us/library/hh674251.aspx)

	Team Foundation Server doesn't require Project Server,
	but if you want to use it, you must use a supported version. 

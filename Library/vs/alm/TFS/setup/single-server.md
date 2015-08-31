Title: How to set up TFS on a single server
ms.TocTitle: Single server
Description: How to set up Team Foundation Server (or TFS Express) on a single using the basic configuration wizard
ms.ContentId: 36d82fcb-e849-41e1-a33f-68974c15fbd4
toc: show

# How to set up TFS on a single server

You can set up TFS on a single server using TFS Express,
or the standard version of TFS using the basic configuration wizard.

If you're using TFS for personal use or to evaluate the core features,
[TFS Express](#TFSExpress) is a good choice.

If you're setting TFS up for your team, 
the [TFS basic configuration wizard](#Basicconfigurationwizard) is a better choice.
Make sure to review our [hardware recommendations](../administer/requirements.md#Hardwarerecommendations)
to confirm that this configuration seems appropriate for your team. If not, consider a 
[dual server](./dual-server.md) or [mutliple server](./multiple-server.md) configuration instead.

## TFS Express

0. Prepare a computer that meets the [operating system requirements](../administer/requirements.md#Operatingsystems) for TFS
and that has at least 1 GB of RAM and 256 GB of disk space.

0. [Download](https://www.visualstudio.com/en-us/downloads/download-visual-studio-vs) and install TFS Express and then use the 
Configure Team Foundation Application Server wizard. 

## Basic configuration wizard

0. Prepare a computer that meets the [operating system requirements](../administer/requirements.md#Operatingsystems) for TFS and that 
meets the [hardware recommendations](../administer/requirements.md#Hardwarerecommendations) for your team.

0. Set up an [appropriate version of SQL Server](../administer/requirements.md#SQLServer).
When you set up SQL Server up for TFS, install the database engine and the full text search services.

	![SQL_SERVER_FEATURES](/Library/vs/alm/tfs/setup/_shared/_img/sql-features.png)

	While the basic configuration wizard will install SQL Server Express for you, we don't recommend using SQL Server Express for
	anything but personal or evaluation deployments of TFS. A Team Foundation Server Standard license comes with a license 
	to SQL Server Standard for use with TFS.
	The [TFS licensing whitepaper](http://www.microsoft.com/en-us/download/details.aspx?id=13350) explains the details.
	If you use the license that's included with TFS, you can only use if for the TFS databases.

0. Ensure that the account you plan to use to configure TFS is a member of the SysAdmin server role. 

	> Installing TFS involves a complex set of operations that require a high degree of privilege - these include creating databases, 
	> provisioning logins for service accounts, and more. Technically, all that is required is membership in the ServerAdmin role; 
	> ALTER ANY LOGIN, CREATE ANY DATABASE, and VIEW ANY DEFINITION server scoped permissions; and CONTROL permission on the master 
	> database. Membership in the SysAdmin server role will confer all of these memberships and permissions,
	> and is therefore the easiest way to ensure that TFS configuration will succeed. If necessary, these memberships and permissions 
	> can be revoked after TFS is installed.  

0. [Download](https://www.visualstudio.com/downloads/download-visual-studio-vs) and install TFS and then use the Basic Server configuration wizard.

### Build service

[!INCLUDE [BUILD](./_shared/build.md)]
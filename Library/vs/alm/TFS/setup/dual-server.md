Title: How to set up TFS in a dual server configuration
ms.TocTitle: Dual server
Description: How to set up Team Foundation Server in a dual server configuration using the full configuration wizard
ms.ContentId: 1364dc15-fbd7-4e05-afa4-39ea22a13e02
toc: show

# How to set up TFS in a dual server configuration

You can enable your TFS deployment to handle more load than a single server configuration by deploying the 
application and data tiers on separate servers.
Make sure to review our [hardware recommendations](../administer/requirements.md#Hardwarerecommendations)
to confirm that this configuration seems appropriate for your team. If not, consider a 
[single server](./single-server.md) or [mutliple server](./multiple-server.md) configuration instead.

## Servers

- Prepare a data tier server that meets the [hardware recommendations](../administer/requirements.md#Hardwarerecommendations)
for your team. 

- Prepare an application tier server that meets the [operating system requirements](../administer/requirements.md#Operatingsystems) 
for TFS and that meets the [hardware recommendations](../administer/requirements.md#Hardwarerecommendations) for your team.

- If you want to use SharePoint integration features and plan to install SharePoint on one of your servers, review the 
hardware requirements for the version of SharePoint you plan to use. SharePoint can be installed on either your application
tier or data tier, depending on the specifics of your hardware. All things being equal, we would recommend installing it
on your application tier.

## Data tier

- Set up an [appropriate version of SQL Server](../administer/requirements.md#SQLServer) on the data tier.
When you set up SQL Server up for TFS, install the database engine and the full text search services.

	![SQL_SERVER_FEATURES](/Library/vs/alm/tfs/setup/_shared/_img/sql-features.png)

	A Team Foundation Server Standard license comes with a license to SQL Server Standard for use with TFS.
	The [TFS licensing whitepaper](http://www.microsoft.com/en-us/download/details.aspx?id=13350) explains the details.
	If you use the license that's included with TFS, you can only use if for the TFS databases.

- Configure your firewall to [allow access to the SQL Server database engine](https://msdn.microsoft.com/en-us/library/ms175043.aspx)
so that TFS can get through the firewall to connect to the SQL Server database engine
from the application tier server.

- Ensure that the account you plan to use to configure TFS is a member of the SysAdmin server role. 

	> Installing TFS involves a complex set of operations that require a high degree of privilege - these include creating databases, 
	> provisioning logins for service accounts, and more. Technically, all that is required is membership in the ServerAdmin role; 
	> ALTER ANY LOGIN, CREATE ANY DATABASE, and VIEW ANY DEFINITION server scoped permissions; and CONTROL permission on the master 
	> database. Membership in the SysAdmin server role will confer all of these memberships and permissions,
	> and is therefore the easiest way to ensure that TFS configuration will succeed. If necessary, these memberships and permissions 
	> can be revoked after TFS is installed.  

### Reporting

If you're going to enable reporting, prepare the data tier for that.

- Install SQL Server Analysis Services and install and configure SQL Server Reporting Services.

- Configure your firewall to [allow access to Reporting Services](https://msdn.microsoft.com/en-us/library/bb934283.aspx) 
and to [allow access to Analysis Services](https://msdn.microsoft.com/en-us/library/ms174937.aspx).

### SharePoint

If you're going to enable SharePoint integration, prepare one of the servers for that.

- Install [an appropriate version of SharePoint](../administer/requirements.md#SharePoint).

	If you already have SharePoint deployed, you can use that deployment instead of installing it on one of your new servers.

- [Download](https://www.visualstudio.com/downloads/visual-studio-2015-downloads-vs) and install TFS on the SharePoint server 
and run the Configure Extensions for SharePoint Products wizard.

	![Extensions for SharePoint Products int the TFS Configuration Center](./_img/tfs-extensions-for-sharepoint.png)

- Add the service account you plan to use for your TFS deployment to the Farm Administrators group in SharePoint. 
Note that if you plan to use NetworkService as your service account, this will look like *{domain}\\{app-tier-machine-name}$*.

## Application tier

- If you're going to enable reporting, install SQL Server Client Tools Connectivity on the application tier server.

	![SQL Server Client Tools Connectivity feature installation](./_img/sql-client-tools-connectivity.png)

- [Download](https://www.visualstudio.com/downloads/visual-studio-2015-downloads-vs) and install TFS and run the Full Server configuration wizard.

	![Full configuration wizard](./_img/full-configuration-wizard.png)

- On the database page, point to the SQL Server instance on the data tier and test the connection.

	![Dabatase page in the full configuration wizard](./_img/database.png)

- Set the service account and authentication method.

	![Service account page in the full configuration wizard](./_img/service-account-and-authentication.png)

	By default, TFS services will run as Network Service in a domain
	or as Local System in a workgroup.
	In a domain, you can also use a dedicated domain account.
	In a workgroup, you can also use a dedicated local account. 
	These options can be desirable if you have multiple services running on your application tier and want
	each one running as a separate account with separate permissions.

### Build service

- [!INCLUDE [BUILD](./_shared/build.md)]

### Reporting

- If you want to enable reporting, turn it on here.

	![Configure reporting checkbox](./_img/configure-reporting.png)

- Set the reporting service instance to your data tier and populate the reporting URLs.

	![Reporting services page in the full configuration wizard](./_img/reporting-service-instance.png)

- Set the account that will be assigned the Reports Reader role in the Analysis Services instance
and test that the account and password can be authenticated.
Reports use this account when they access the Analysis Services database.

	![Report reader account page in the full configuration wizard](./_img/report-reader-account.png)

### SharePoint

- If you want to enable SharePoint integration, turn it on here.

- Point to your SharePoint instance and TFS will configure 
the site in SharePoint and hook it up to TFS.

	![Sharepoint page in the full configuration wizard](./_img/sharepoint.png)

	If you don't know the administration URL, go to the start menu and run the SharePoint administration application.
	That will open the adminstration web page and you can copy the URL from your browser.
Title: Install and configure TFS 2015
ms.TocTitle: Install
Description: Use the new install guide for Team Foundation Server to set up TFS on your server or servers
ms.ContentId: 0a44920a-fcdc-4545-b150-8246dcc47f42
toc: show

# Install and configure TFS 2015

## For your team

You have many choices
in how to deploy TFS, from putting everything on a single server all the way to using multiple 
application tiers, multiple SQL instances, and a SharePoint farm. See our
[hardware recommendations](../administer/requirements.md#Hardwarerecommendations) for more detailed help 
in determining the right type of deployment for your team. 

* [Single server](./single-server.md)

	A single server deployment is the easiest way to deploy TFS	and is a good configuration for
	small teams not planning to use reporting features.

* [Dual server](dual-server.md)

	A dual server deployment, with separate application and data tiers, is a good configuration for
	medium sized teams and small teams planning to use reporting features.

* [Multiple server configuration](./multiple-server.md)

	Larger teams or teams with heavier usage (via automated builds, for example, or via having 
	large amounts of version control data) should consider multiple server deployments, which 
	can involve multiple application tiers, multiple SQL instances, etc.

## For evaluation or personal use

If you're setting up TFS for personal use or to evaluate the core features
(version control, build and work item tracking),
use [TFS Express](http://www.microsoft.com/download/details.aspx?id=48259).
It's free, it's simple to set up,
and it can be installed on both client and server operating systems.

Of course, if you want to evaluate all of the features of TFS, like reporting and SharePoint integration,
you should install a [free trial of the standard TFS product](http://www.microsoft.com/download/details.aspx?id=48260) with those features enabled.

You might also want to consider using a free
[Visual Studio Online account](https://www.visualstudio.com/get-started/sign-up-for-visual-studio-online)
for personal use.
Because it's in the cloud, you won't have to install SQL Server and TFS on your own hardware,
and you won't need to do things like manage your own backups.

<!--
## Backup

Create up a [backup plan](../administer/backup.md).

## Support remote teams

If your team is distributed geographically, [set up a proxy](../administer/scale/proxy.md).
-->
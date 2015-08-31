Title: Upgrade TFS
ms.topic: Upgrade
Description: Upgrade your instance of Team Foundation Server to the latest version
ms.ContentId: 575486d5-af44-41a1-b14c-b82e1e362132
toc: show

# Upgrade your deployment to the latest version of TFS

**Important**: Direct upgrade to TFS 2015 is supported only from TFS 2010 SP1 and newer. If your TFS deployment is on an older
version than that, you will need to upgrade to TFS 2015 in multiple hops. For example, if you are on TFS 2008 you could 
upgrade to TFS 2012 first and then to TFS 2015. 

The general process for upgrading an existing deployment of Team Foundation Server is to:

1.	**Prepare your environment**. New [system requirements](..\administer\requirements.md) may require you to upgrade hardware or software. 
And regardless, an upgrade is a good time to consider whether your current environment is meeting your needs, 
or whether it makes sense to make changes. 

2.	**Expect the best, prepare for the worst**. While we put a lot of effort into ensuring that TFS upgrades are highly reliable, it always makes sense to 
prepare for the case where something goes wrong. The single most important step you can take here is to ensure 
you have a complete and consistent set of [database backups](https://msdn.microsoft.com/library/hh561429.aspx). You should also consider doing a 
[dry run](.\pre-production.md) of your upgrade in a pre-production environment.

3.	**Do the upgrade**! Once the preparation is done, you'll need to install the new version of TFS to get new binaries, and then run 
through the upgrade wizard to upgrade your databases. 

## Complexity

Upgrading a TFS deployment can be quite straightforward or quite complicated, depending on the specifics of your 
existing deployment. Factors that will influence the complexity and duration of your upgrade include:

- How many servers are involved in your deployment.
- Whether your deployment is configured with SharePoint integration or reporting.
- How large your databases are.
- How old a version you are upgrading from.

In all cases, however, the general process is logically the same. Get your environment ready; Expect the best, 
prepare for the worst; and finally, Do the upgrade.

## Downtime

Your TFS deployment will be offline for the duration of the upgrade. Upgrade times can be measured in minutes for 
very small deployments or in days for very large deployments. You can keep 
your upgrades comparably speedy by [cleaning up unnecessary data](..\administer\clean-up-data.md). If you're keeping up 
with the latest versions of TFS, that helps a lot, too. 

If you're upgrading a very large database to TFS 2015, consider using the [TfsPreUpgrade tool](.\pre-upgrade.md). 
It performs the most expensive parts of the upgrade from TFS 2013 QU4/QU5 in the background, allowing you to 
continue using TFS. This tool can cut offline times for upgrade significantly for large databases - one internal 
Microsoft database went from over a week of offline time down to under a day. 

## Details

[Walk through a TFS Express upgrade](./express.md) - this is as simple as it gets.

[Walk through a standard upgrade scenario](./walkthrough.md) - upgrading a two server deployment 
from TFS 2012 to TFS 2015.

We will be covering more advanced scenarios - things like upgrading deployments which have multiple application
tiers in a load balancer, deployments which have their databases in SQL Always On availability groups, etc. - in
future updates. In the meantime, the documentation for TFS 2013 and earlier is still relevant and can provide
some guidance for these more advanced scenarios.
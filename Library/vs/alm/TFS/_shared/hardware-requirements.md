ms.ContentId: 9dd3bd16-8876-44e0-837b-84210318fb22

The following table includes minimal hardware requirements
for teams installing Team Foundation Server without SharePoint Products.
If you're going to install SharePoint Products on a data tier sever,
then make sure it meets SharePoint requirements as well as these.


Number of users | Configuration | CPU                                                                                                                 | Memory                              | Hard disk
----------------|---------------|---------------------------------------------------------------------------------------------------------------------|-------------------------------------|------------------------------
< 250           | Single-server | 1 dual core processor at 2.13 GHz                                                                                   | 2 GB                                | 1 disk at 7.2k rpm (125 GB)
250 to 500      | Single-server | 1 dual core processor at 2.13 GHz                                                                                   | 4 GB                                | 1 disk at 10k rpm (300 GB)
500 to 2,200    | Multi-server  | App-tier: 1 dual core Intel Xeon processor at 2.13 GHz<br/>Data-tier: 1 quad core Intel Xeon processor at 2.33 GHz  | App-tier: 4 GB<br/>Data-tier: 8 GB  | App-tier: 1 disk at 7.2k rpm (500 GB)<br/>Data-tier: SAS disk array at 10k rpm (2 TB)
2,200 to 3,600  | Multi-server  | App-tier: 1 quad core Intel Xeon processor at 2.13 GHz<br/>Data-tier: 2 quad core Intel Xeon processors at 2.33 GHz | App-tier: 8 GB<br/>Data-tier: 16 GB | App-tier: 1 disk at 7.2k rpm (500 GB)<br/>Data-tier: SAS disk array at 10k rpm (3 TB)

If you have more than 3,600 TFS users, consider installing [multiple application tiers](/Library/vs/alm/tfs/administer/scale/app-tier.md)
to distribute the application tier load,
and using [SQL Always On](/Library/vs/alm/tfs/administer/scale/data-tier.md) to ensure high availability of your TFS databases.

For evaluation or personal use, you can use TFS Express,
or a basic configuration of the standard TFS product.
These only require 1 GB RAM and 8 GB of hard disk space to get started,
but more will clearly be required for heavier usage.


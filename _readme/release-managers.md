Title: Read me for release managers
Toc: show
ms.ContentId: 7143050D-7C77-473F-96EB-35628040209D

# Release managers

Release managers take the final steps to publish content from our repos to Visual Studio Online and MSDN. One member of [VS ALM Content Release Managers](mailto:ceoacontmgr@microsoft.com) is on active duty each week.

[//]: # (Todo: add calendar to show who's on duty)

Any release manager (even those not on duty for the week) can publish if they want to jump in and do it to expedite getting some content published.

## Repos, builds, staging sites

<table>
<thead>
<tr>
<td style="vertical-align:top">Site</td>
<td style="vertical-align:top">Repo</td>
<td style="vertical-align:top">Preview</td>
<td style="vertical-align:top">Publish</td>
</tr>
</thead>
<tr>
<td style="vertical-align:top">For MSDN</td>
<td style="vertical-align:top">[Content.ALM](https://mseng.visualstudio.com/DefaultCollection/VSOnline/_git/Content.ALM#path=%2F&version=GBmaster&_a=contents)</td>
<td style="vertical-align:top">
<p>Build: [MSDN.ALMContent.Stage](https://mseng.visualstudio.com/web/build.aspx?pcguid=0efb4611-d565-4cd1-9a64-7d6cb6d7d5f0&projectname=vsonline&definitionId=1287&action=viewBuilds)
</p>
<p>Site: [int.msdn](https://int.msdn.microsoft.com/en-us/Library/vs/alm/Build/overview)
</p>
<p>**Known issues:** You you might get a *403 - Forbidden: Access is denied* message if you don't enable itgproxy. This setting might break other sites, such as the VSSStage site mentioned below. Hyperlinks might be broken (e.g. point to msdnstage site). Our layout is currently broken on this site. If you have questions, contact [Xiaokai He](mailto:hxiao@microsoft.com).</p>
</td>
<td style="vertical-align:top">
<p>
Build: [MSDN.ALMContent.Live](https://mseng.visualstudio.com/web/build.aspx?pcguid=0efb4611-d565-4cd1-9a64-7d6cb6d7d5f0&projectname=vsonline&definitionId=1288&action=viewBuilds)
</p>
<p>Site: [MSDN](http://msdn.microsoft.com/en-us/Library/vs/alm/build/overview)</p>
</td>
</tr>
<tr>
<td style="vertical-align:top">For VisualStudio.com (VSO)</td>
<td style="vertical-align:top">[Content.VS](https://mseng.visualstudio.com/DefaultCollection/VSOnline/_git/Content.VS#path=%2F&version=GBmaster&_a=contents)</td>
<td style="vertical-align:top">
<p>
Build: [MSDN.VSContent.Stage](https://mseng.visualstudio.com/web/build.aspx?pcguid=0efb4611-d565-4cd1-9a64-7d6cb6d7d5f0&projectname=vsonline&definitionId=637&action=viewBuilds)
</p>
<p>Site: [VSComInt](https://vscomint.tfsallin.net/en-us/get-started/setup/set-up-vs)
</p>**Known issues:** You you might get a *403 - Forbidden: Access is denied* message if you don't enable itgproxy. This setting might break other sites. If you have questions, contact [Xiaokai He](mailto:hxiao@microsoft.com).
<p>
</p>
</td>
<td style="vertical-align:top">
<p>Build: [MSDN.VSContent](https://mseng.visualstudio.com/web/build.aspx?pcguid=0efb4611-d565-4cd1-9a64-7d6cb6d7d5f0&projectname=vsonline&definitionId=603&action=viewBuilds)
</p>
<p>Site: https://www.visualstudio.com/
</p>
</td>
</tr>
<tr>
<td style="vertical-align:top">That is opinionated or specialized</td>
<td style="vertical-align:top">[Content.VS.Articles](https://mseng.visualstudio.com/DefaultCollection/VSOnline/_git/Content.VS.Articles#path=%2F&version=GBmaster&_a=contents)</td>
<td style="vertical-align:top">
<p>Build: [VSOnline builds](https://mseng.visualstudio.com/DefaultCollection/VSOnline/_Build) search for 
MSDN.VS-Articles.Stage
</p>
<p>Previews: [SandBoxMsdnWorking](https://sandboxmsdnworking.redmond.corp.microsoft.com/en-us/Library/vs/alm/articles/overview)</p>
<p>(This is just a sandbox site. Final site implementation is still TBD.)</p>
</td>
<td style="vertical-align:top">
<p>Build: [VSOnline builds](https://mseng.visualstudio.com/DefaultCollection/VSOnline/_Build) search for 
MSDN.VS-Articles.Live
</p>
<p>[What are articles? Where will we publish them?] (index.md#articles)</p>
</td>
</tr>
</table>

## Publish daily from master

The release manager publishes content at least once a day from ```master``` to ```releases/live```, which contains the content on the live site.

0. Confirm the ```master``` build is green. If not, ask the contributor to fix the issues in their branch and complete another PR.

0. If delays in fixing the build are putting the release at risk, send mail to [VSOnline Content Contributors](mailto:vsocontc@microsoft.com) to let people know the release could be delayed.

0. From the commit that built clean, create a branch called ```releases/next```.

0. Create and complete a PR from ```releases/next``` to ```releases/live```.

0. Delete ```releases/next```.

0. Confirm the ```releases/live``` build is green.

0. Run [PromoteContent.exe] (#promote_content).

<a name="promote_content"></a>
## Run PromoteContent.exe

For the content on the ```releases/live``` branch to be published, you must run PromoteContent.exe.

| Repo | Command |
| ------------- | ------------- |
| [Content.ALM](https://mseng.visualstudio.com/DefaultCollection/VSOnline/_git/Content.ALM) | PromoteContent.exe prod mseng DefaultCollection vsonline content.**alm** releases/live   |
| [Content.VS](https://mseng.visualstudio.com/DefaultCollection/VSOnline/_git/Content.VS/)  | PromoteContent.exe prod mseng DefaultCollection vsonline content.**vs** releases/live   |

See https://int.msdn.microsoft.com/en-us/openauthoring/howto/manualtrigger

## Emergency fixes to releases/live

We should merge only from master to releases/live to avoid having to manually resolve conflicts, which increases the chance of introducing errors.

In emergencies (e.g. geopolitical or LCA issues), we can branch from and then PR merge small changes (e.g. a few words in 1 or 2 files) into releases/live. When we do this, it is the release manager's responsibility to immediately PR merge releases/live into master, and to carefully resolve conflicts that might arise.


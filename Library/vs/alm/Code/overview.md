Title: Use Version Control
ms.TocTitle: Code
Description: Use version control as early as possible in your project. Choose between TFVC and Git.
ms.ContentId: A4D7295A-22AB-4990-BE68-EF81A1C31F01
ms.topic: code reference (API)
Toc: show

# Use Version Control

Whether your software project is large or small, using version control early in the lifecycle of your project is a best practice.

<span style="font-size:16px">[What's new?](whats-new.md)</span>

### Small projects

Even if you’re working alone on a small project, you can use version control to improve your personal productivity and recover from difficult problems.

**I just want to get started coding right away. I’m not sure if I care about sharing right now, but I might in the future.** 

You can begin using Git version control before you write your first line of code with virtually no cost or risk. You get many benefits, including being able to revert to a known good state whenever you get in trouble. All this is done on your local dev machine, with no server required. When you’re ready, you can quickly share your code and begin collaborating in TFS or on a third-party Git service. 

<span style="font-size:16px">[Get started using Git](git/get-started.md).</span>

**I'm looking for a simple system that makes it easy for me to collaborate with others right now.**

For not much more additional time, you can create a team project and get started using Team Foundation Version Control (TFVC). You can use either Visual Studio Online or an on-premises Team Foundation Server (TFS).

<span style="font-size:16px">[Get started using Team Foundation Version Control (TFVC)](http://msdn.microsoft.com/en-us/library/ms181384%28v=vs.140%29).</span>

### Larger projects
  
If you work with a team or on complex projects, you should almost certainly work in a shared, version-controlled file system so that you can improve collaboration and transparency. You can also take advantage of integrated [automated builds](https://int.msdn.microsoft.com/en-us/Library/vs/alm/Build/overview), [project planning and tracking](https://msdn.microsoft.com/en-us/library/dd286619%28v=vs.140%29.aspx), and other [Application Lifecycle Management capabilities](https://msdn.microsoft.com/en-us/library/fda2bad5%28v=vs.140%29.aspx) if you use TFS (either [on-premises](http://int.msdn.microsoft.com/en-us/Library/vs/alm/Admin/overview) or [in the cloud on Visual Studio Online](https://www.visualstudio.com/features/version-control-vs)).
 
<a name="tfvc_or_git_summary"></a>
## Which version control system should I use?
 
When you create a new team project you choose the version control system your team will use in that project: Team Foundation Version Control (TFVC) or Git. This is a permanent choice for each team project you create, but you can use both TFVC and Git team projects in the same team project collection.

![Connecting to a TFVC team project](_img/IC750752.png)

### TFVC (centralized)
 
Team Foundation Version Control (TFVC) is a centralized version control system. Typically, team members have only one version of each file on their dev machines. Historical data is maintained only on the server. Branches are path-based and created on the server.

TFVC enables two models for your team to make changes:

* [Server workspaces](https://msdn.microsoft.com/en-us/library/bb892960%28v=vs.140%29.aspx#server): Before making changes, team members publicly check out files. Most operations require developers to be connected to the server. (In the past teams blocked more than one person from checking out, but this is now less common.) This system facilitates locking work flows. Other systems that work this way include Visual Source Safe, Perforce, and CVS.

* [Local workspaces](https://msdn.microsoft.com/en-us/library/bb892960%28v=vs.140%29.aspx#local): Each team member takes a copy of the latest version of the codebase with them and works offline as needed. Developers check in their changes and resolve conflicts as necessary. Another system that works this way is Subversion.

<span style="font-size:16px;">[Use TFVC](https://msdn.microsoft.com/en-us/library/ms181237%28v=vs.140%29.aspx).</span>

### Git (distributed)

Git is a distributed version control system. Each developer has a copy of the entire source repository on their dev machine. Developers can commit each set of changes on their dev machine and perform version control operations such as history and compare without a network connection. Branches are lightweight. When you need to switch contexts, you can create a private local branch. You can quickly switch from one branch to another to pivot among different variations of your codebase. Later, you can merge, publish, or dispose of the branch. Another system that works this way is Mercurial.

**Important:** Git in Visual Studio and TFS is standard Git. You can use Visual Studio with third-party Git services, and you can also use third-party Git clients with TFS.
 
<span style="font-size:16px">[Use Git](git/overview.md).</span>
 
<a name="tfvc_or_git_details"></a>
## Capabilities

Need more help to make a choice? These charts might help.

### Fundamentals

<table>
<thead>
<tr>
<td>Capability</td>
<td>TFVC</td>
<td>Git</td>
</tr>
</thead>
<tr>
<td>Changes</td>
<td><p>Team members can concurrently change files on their dev machines. You [upload (check-in)](https://msdn.microsoft.com/en-us/library/ms181407%28v=vs.140%29.aspx) changesets to the server when you create them. You can upload your changes at any time. However, you might be interrupted by [conflicts](https://msdn.microsoft.com/en-us/library/ms181432%28v=vs.140%29.aspx).</p>

<p>You can change the comment of a [changeset](https://msdn.microsoft.com/en-us/library/ms181408%28v=vs.140%29.aspx) after you check it in. You can link changesets to work items and associate them with completed builds.</p>
</td>
<td><p>Team members can concurrently change files on their dev machines. You create commits on your dev machine independently of contributing them to the team. When you’re ready you must pull the latest commits before you upload (push) yours to the server. When you pull, you might be interrupted by conflicts.</p>

<p>You can amend the latest local commit. You cannot change older commits. You can link commits to work items and associate them with completed builds.</p>

<p>You can modify and combine local commits from the command prompt.</p></td>
</tr>
<tr>
<td>Branching</td>
<td>
<p>Path-based branches are used mostly as long-standing constructs to isolate risk of change among feature teams and releases. Team members typically set up an additional workspace for each branch they work on.</p>

<p>Changes in each branch are independent from each other, so you don’t have to check them in before switching from one branch to another. Merging between sibling branches requires a baseless merging.
</p>

<p>You can get visualizations of your branch structures and where your changesets have been merged.</p>

<p>See [Use branches to isolate risk in Team Foundation Version Control](https://msdn.microsoft.com/en-us/library/ms181423%28v=vs.140%29.aspx).</p>
</td>
<td><p>Branching is lightweight and path independent. Many developers create a branch for each new feature they are coding, sometimes on a daily basis. You can quickly switch from one branch to another to pivot among different variations of your codebase. You can create branches that exist only on your dev machine and share them if and when you’re ready. </p>

<p>You must commit, branch, stash, or undo changes before switching branches. Merging is simple and independent of the commit that the branch is based on.</p>

<p>You can compare branches to see which commits exist on which branches.</p>

<p>See Use Git branches to switch contexts, suspend work, and isolate risk.</p>
</td>
</tr>
<tr>
<td>Conflict resolution</td>
<td>You might have to [resolve conflicts](https://msdn.microsoft.com/en-us/library/ms181432%28v=vs.140%29.aspx) when you get, check in, merge, or unshelve. You can resolve all types of conflicts in Visual Studio.</td>
<td>You might have to resolve conflicts when you pull or merge. You can resolve content conflicts in Visual Studio. Other types of conflicts can be resolved from the command prompt.</td>
</tr>
<tr>
<td>File storage</td>
<td>You can check in large binary files. You might also want to use [NuGet](http://go.microsoft.com/fwlink/?LinkId=246165) in combination or as an alternative.</td>
<td>You can check in small binary files. Avoid checking in large binary files, especially those that you modify often. If possible, use NuGet as an alternative to checking in binary files.</td>
</tr>
<tr>
<td>History</td>
<td>File history **is not replicated** on the client dev machine and so can be viewed only when you’re connected to the server. You can [view history](https://msdn.microsoft.com/en-us/library/ms245475%28v=vs.140%29.aspx) in Visual Studio and on the web portal. You can annotate files to see who changed a line, and when they changed it.</td>
<td>File history **is replicated** on the client dev machine and can be viewed even when not connected to the server. You can view history in Visual Studio and on the web portal. You can annotate files to see who changed a line, and when they changed it.
</td>
</tr>
<tr>
<td>Tag your files</td>
<td>You can [apply labels](https://msdn.microsoft.com/en-us/library/ms181439%28v=vs.140%29.aspx) to a version of one or more files from either Visual Studio or the command prompt. Each file can have label applied to a different version.</td> 
<td>You can apply tags from the command prompt to individual commits. View tags in the Visual Studio history window.
</td>
</tr>
<tr>
<td>Roll back changes</td>
<td>You can [roll back one or more changesets](https://msdn.microsoft.com/en-us/library/ms194956%28v=vs.140%29.aspx)</td>
<td>You can revert a commit.
</td>
</tr>
<tr>
<td>Scale</td>
<td>You can work on small or very large scale projects using [local workspaces](https://msdn.microsoft.com/en-us/library/bb892960%28v=vs.140%29.aspx#local). Supports massive scale (millions of files per branch and large binary files) projects using [server workspaces](https://msdn.microsoft.com/en-us/library/bb892960%28v=vs.140%29.aspx#server).</td>
<td>You can quickly begin small projects. You can scale up to very large projects, but you have to plan ahead to modularize your codebase. You can create multiple repositories in a team project.
</td>
</tr>
</table>


### Server 

<table>
<thead>
<tr>
<td>Capability</td>
<td>TFVC</td>
<td>Git</td>
</tr>
</thead>
<tr>
<td>Server</td>
<td>TFS</td>
<td>TFS and third-party services</td>
</tr>
<tr>
<td>Alerts</td>
<td>Team members can [receive email alerts when check-ins occur](https://msdn.microsoft.com/en-us/library/ms181407%28v=vs.140%29.aspx#alerts).
</td>
<td>Team members can receive email alerts when commits are pushed to the server. 
</td>
</tr>
<tr>
<td>Auditability</td>
<td>Because your team checks in all their work into a centralized system, you can identify which user checked in a [changeset](https://msdn.microsoft.com/en-us/library/ms181408%28v=vs.140%29.aspx) and use [compare](https://msdn.microsoft.com/en-us/library/bb385990%28v=vs.140%29.aspx) to see what they changed. Looking at a file, you can [annotate](https://msdn.microsoft.com/en-us/library/bb385979%28v=vs.140%29.aspx) it to identify who changed a block of code, and when they did it.</td>
<td>You can identify which user pushed a commit to TFS. (Anyone can claim any identity as the author or committer.) You can identify when changes were made what was changed using history, compare, and annotate.</td>
</tr>
<tr>
<td>Builds (automated by TFBuild)</td>
<td>You can use all [TFBuild](/Library/vs/alm/build/overview.md) capabilities to build any combination of content you want within the team project collection.</td>
<td>You can use most TFBuild capabilities to build one team project at a time, and one or more repositories at a time. Gated check-in builds aren’t available yet. Symbols can be published, but they are not indexed yet.
</td>
</tr>
<tr>
<td>Code reviews</td>
<td>Yes; see [Day in the life of an ALM Developer: Suspend work, fix a bug, and conduct a code review](https://msdn.microsoft.com/en-us/library/hh474795%28v=vs.140%29.aspx). For more lightweight discussions, you can also comment on and send email about a changeset from the web portal.
</td>
<td>Yes; see [Conduct a pull request](git/pull-requests.md). For more lightweight discussions, you can also comment on and send email about a commit from the web portal.
</td>
</tr>
<tr><td>Files</td>
<td><p>Each team project contains all files under a single root path (for example: **$/FabrikamTFVC**). You can [apply permissions](https://msdn.microsoft.com/en-us/library/ms252587%28v=vs.140%29.aspx) at the file level. You can [lock files](https://msdn.microsoft.com/en-us/library/ms181418%28v=vs.140%29.aspx).</p>

<p>You can browse your files on the web portal and using [Source Control Explorer](https://msdn.microsoft.com/en-us/library/ms181370%28v=vs.140%29.aspx) in Visual Studio.</p>

<p>Your team project exists on only one server.</p>
</td>
<td>
<p>Each team project can contain one or more Git repositories and each Git repository can contain one or more branches. The most granular permissions you can apply are to a repository or a branch. Files cannot be locked.</p>
<p>You can browse your files on the web portal.</p>
<p>You can push commits to multiple remote repositories (for example to both your team project repository and to your web site hosted on Windows Azure.</p>
</td>
</tr>
<tr>
<td>Quality gates</td>
<td>You can use CI builds, gated check-in builds and check-in policies.</td>
<td>You can use CI builds. Gated check-in builds aren’t available yet.
</td>
</tr>
</table>



 
### Client

<table>
<thead>
<tr>
<td>Capability</td>
<td>TFVC</td>
<td>Git</td>
</tr>
</thead>
<tr>
<td>Client software</td>
<td> Visual Studio, Eclipse (with [Team Explorer Everywhere](https://msdn.microsoft.com/en-us/library/gg413285%28v=vs.140%29.aspx))</td>
<td>Visual Studio, Eclipse, and other third-party tools</td>
</tr>
<tr>
<td>Files</td>
<td>You can browse your files using [Source Control Explorer](https://msdn.microsoft.com/en-us/library/ms181370%28v=vs.140%29.aspx) in Visual Studio, or using Windows File Explorer or the [command prompt](https://msdn.microsoft.com/en-us/library/cc31bk2e.aspx).</td>
<td>You can browse your files using Windows File Explorer or the command prompt. You cannot yet browse files in Visual Studio.
</td>
</tr>
<tr>
<td>Manage work on your dev machine</td>
<td>[Pending changes](https://msdn.microsoft.com/en-us/library/ms245462%28v=vs.140%29.aspx#pending_changes) and [my work](https://msdn.microsoft.com/en-us/library/ms245462%28v=vs.140%29.aspx#my_work) pages.</td>
<td>Changes, commits, and branches pages.</td>
</tr>
<tr>
<td>Suspend your work</td>
<td>You can [suspend from my work page or shelve your changes](https://msdn.microsoft.com/en-us/library/ms181403%28v=vs.140%29.aspx).</td>
<td>You can create a branch from (from Visual Studio or the command prompt) or stash (from the command prompt)</td>
</tr>
<tr>
<td>User interface</td>
<td>
<ul>
 <li>**Visual Studio:** Offers all commonly used features and many advanced features.</li>
 <li>**TFS web portal:** Can browse, comment, annotate, and see history of the codebase.</li>
 <li>**TF Command prompt:** Installed with Visual Studio. Used for advanced, administrative, and other less common tasks.</li> 
</ul>
</td>
<td>
<ul>
 <li>**Visual Studio:** Offers many commonly used features. Features for some common tasks are not yet available.</li>
 <li>**TFS web portal:** Can browse, comment, annotate, and see history of the codebase.</li>
 <li>**Third-party command prompt:** You can install it from Visual Studio. Used for some common and many less common tasks.</li>
</ul>
</td>
</tr>
<tr>
<td>Visual Studio compatibility</td>
<td>You can use all supported [previous versions of Visual Studio](http://msdn.microsoft.com/en-us/library/dd997788).</td>
<td><p>Git is built into with Visual Studio 2015 and Visual Studio 2013.</p>
<p>You can also use Visual Studio 2012 Update 4 (you must also install [Visual Studio Tools for Git](http://go.microsoft.com/fwlink/?LinkID=275845)).</p></td>
</tr>
<tr>
<td>Web portal</td>
<td>You can browse your codebase (including branches), view history, annotate and comment on changesets and shelvesets, and perform other tasks such as ad hoc downloading of selected parts of your codebase as a .zip file.</td>
<td>You can browse your codebase, view history, compare branches, annotate and comment on commits, and perform other tasks such as ad hoc downloading of selected parts of your codebase as a .zip file.</td>
</tr>
</table>


### Integration and migration

<table>
<thead>
<tr>
<td>Capability</td>
<td>TFVC</td>
<td>Git</td>
</tr>
</thead>
<tr>
<td>CodePlex support</td>
<td>[CodePlex](http://www.codeplex.com/) is supported.</td>
<td>[CodePlex](http://www.codeplex.com/) is supported.</td>
</tr>
<tr>
<td>Migration path</td>
<td>[Git-TF](https://gittf.codeplex.com/)</td>
<td>[Git-TF](https://gittf.codeplex.com/)</td>
</tr>
</table>

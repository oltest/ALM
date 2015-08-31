Title: Work from the Git command prompt
Description: Work from the Git command prompt
ms.TocTitle: Command prompt
ms.ContentId: FAED51BE-2CB0-46DE-8C72-E4EEF6CB8827
toc: show

# Work from the Git command prompt

Visual Studio provides most of the fundamental capabilities to develop an app in a Git version-controlled codebase. You might have to use the command prompt for some manual tasks or to automate work using a script. 

<a href="#set_up"><img alt="Prompt to install Git command prompt tools" src="_img/command-prompt/IC675719.png"></img></a>

## Work from the command prompt
 
**Caution:** If you are not an experienced Git user, use the command prompt carefully. Make sure to research the command thoroughly before you use it. 

<table>
<tr>
<td>I want to...</td>
<td>Can I do it in Visual Studio?</td>
<td>How do I do it from the command prompt?</td>
</tr>
<tr>
<td>
<p>Amend my last commit. Some typical cases:</p>
<ul>
<li>Add a file you wanted to include in the commit. [See Undoing Things](http://git-scm.com/book/en/Git-Basics-Undoing-Things).</li>
<li>Modify a comment. For example, maybe you want to change "Fix a bug" to "Fix bug #32" in order to associate the commit with a work item when you push you changes to TFS. See [How do I edit an incorrect commit message in Git?](http://stackoverflow.com/questions/179123/how-do-i-edit-an-incorrect-commit-message-in-git)</li>
</ul>
</td>
<td>Yes</td>
<td>[git-commit](https://www.kernel.org/pub/software/scm/git/docs/git-commit.html)</td>
</tr>
<tr>
<td>Apply a tag to a commit</td>
<td>Yes</td>
<td> 
 You can use the command prompt to push, edit, and remove tags (see [Git-scm: Git Basics - Tagging](http://git-scm.com/book/en/Git-Basics-Tagging)) from a repository in TFS if you have sufficient permissions.
</td>
</tr>
<tr>
<td>Branch and merge</td>
<td>Yes (but some conflicts can be resolved only at command prompt).</td>
<td>
[git-branch](http://git-scm.com/docs/git-branch), [git-merge](http://git-scm.com/docs/git-merge)
</td>
</tr>
<tr>
<td>Commit my changes</td>
<td>Yes</td>
<td><p>[git-commit ](http://git-scm.com/docs/git-commit)</p>
<p>**Tip:** You can associate a work item with a commit by including the ID in your comment. For example, you apply this comment #35 Catch null exception  to your commit. When you push this commit into TFS, the commit will be associated with work item #35.</p> 
</td>
</tr>
<tr>
<td>Copy (clone) a remote repository to my dev machine</td>
<td>Yes</td>
<td> 
[git-clone](http://git-scm.com/docs/git-clone)</td>
</tr>
<tr>
<td>Create (initialize) a local repository</td>
<td>Yes</td>
<td>[git-init](http://git-scm.com/docs/git-init)
</td>
</tr>
<tr>
<td>Create or edit a note</td>
<td>No
</td>
<td>You can use the command prompt to push, edit, and remove notes (see [Git-scm: Note to Self](http://git-scm.com/2010/08/25/notes.html)) from a repository in TFS if you have [sufficient permissions](http://msdn.microsoft.com/en-us/library/ms252587#Git).
</td>
</tr>
<tr>
<td>Get information about my local repository (such as the remotes I am tracking)
</td>
<td>Yes
</td>
<td>[git-remote](http://git-scm.com/docs/git-remote)
</td>
</tr>
<tr>
<td>Preview (fetch) and then download (pull) changes from a remote repository</td>
<td>Yes (but some conflicts can be resolved only at the command prompt)</td>
<td>[git-fetch](http://git-scm.com/docs/git-fetch), [git-pull](http://git-scm.com/docs/git-pull)
</td>
</tr>
<tr>
<td>Push changes to a remote repository
</td>
<td>Yes</td>
<td>[Git-scm: git-push](http://git-scm.com/docs/git-push)
</td>
</tr>
<tr>
<td>Replay commits from one branch onto another</td>
<td>Yes</td>
<td>[Git-scm: Git Branching - Rebasing](http://git-scm.com/book/en/Git-Branching-Rebasing)<br/>
[Git-scm: Rewriting History](http://git-scm.com/book/en/Git-Tools-Rewriting-History)<br/>
[git-rebase](http://git-scm.com/docs/git-rebase)
</td>
</tr>
<tr>
<td>Re-order history, combine (squash) commits.</td>
<td>No</td>
<td>[Git-scm: Git Branching - Rebasing](http://git-scm.com/book/en/Git-Branching-Rebasing)<br/>
[Git-scm: Rewriting History](http://git-scm.com/book/en/Git-Tools-Rewriting-History)<br/>
[git-rebase](http://git-scm.com/docs/git-rebase)
</td>
</tr>
<tr>
<td>Revert a committed change by applying the inverse of the commit. See rolling back changes with revert.</td>
<td>Yes</td>
<td>[git-revert(1) Manual Page](https://www.kernel.org/pub/software/scm/git/docs/git-revert.html)
</td>
</tr>
<tr>
<td>Stash changes
</td>
<td>No</td>
<td>[Git-scm: Git Tools - Stashing](http://git-scm.com/book/en/Git-Tools-Stashing)
</td>
</tr>
<tr>
<td><p>Undo committed changes by returning my local repo to a prior commit and de-referencing the later commit.</p>
<p>**Caution:** According to [Undoing Things](http://git-scm.com/book/en/Git-Basics-Undoing-Things), "...this is a dangerous command: Any changes you made to that file are gone - you just copied another file over it. Don't ever use this command unless you absolutely know that you don't want the file."
</p>
</td>
<td>No</td>
<td>[git-reset](http://git-scm.com/docs/git-reset)
</td>
</tr>
<tr>
<td>View and manage my changes since the last commit
</td>
<td>Yes</td>
<td>
[Git-scm: Git Basics - Recording Changes to the Repository](http://git-scm.com/book/en/Git-Basics-Recording-Changes-to-the-Repository)<br/>
[Git-scm: Git Basics - Undoing Things](http://git-scm.com/book/en/Git-Basics-Undoing-Things)<br/>
</td>
</tr>
<tr>
<td>View history
</td>
<td>Yes</td>
<td>[Git-scm: Git Basics - Viewing the Commit History](http://git-scm.com/book/en/Git-Basics-Viewing-the-Commit-History)
</td>
</tr>
</table> 

<a name="set_up"></a>
## Get set up to use the command prompt tools
 
Before you can use the command prompt tools, you have to install them and 
then [create a personal access token](#pat) or 
[alternate authentication credentials](#altcred) for authentication.
 
### Install the command prompt tools
 
If you have not already installed some command prompt tools, you can get some quickly from Visual Studio. (One way you can tell that you don't have the tools is if you try to enter a git command and get the ```'git' is not recognized as an internal or external command...``` message.)

![Installing the Git command prompt tools](_img/command-prompt/IC698868.png)

**Tips:**

 * The install process drops a Git Bash icon on your desktop. We recommend you delete this icon because we don't believe this entry point leads to the best experience. If for some reason you want to run Git Bash later, you can do so from Windows Start.

 * To make using the command prompt less tedious (for example, to avoid having to enter your credentials every time you push), you might want to also install [Windows Credential Store for Git](http://gitcredentialstore.codeplex.com/).

 * If you want to run Git commands from PowerShell, install [Posh-Git (a PowerShell environment for Git)](https://github.com/dahlbyk/posh-git).

### Launch the Git command prompt
 
You can launch the Git command prompt from the Actions menu on the Changes (Keyboard: Ctrl + 0, G), Commits, and Branches pages.

![Opening the command prompt](_img/command-prompt/IC675722.png)

You can also launch the Git command prompt from repositories on the Connect (Keyboard: Ctrl + 0, C) page.

![Open the command prompt from a repository](_img/command-prompt/IC675723.png)

<a name="pat"></a>
### Create a personal access token for your Visual Studio Online account

If your repository is hosted on Visual Studio Online, you must authenticate access 
to your account before you can use the command prompt to perform Git tasks.
To authenticate access, create a personal access token. 

[!INCLUDE [personal-access-tokens](_shared/personal-access-tokens.md)]

## Q & A

#### Q: Where can I learn more commands?
 
A: http://git-scm.com/docs

#### Q: Why should I use personal access tokens?

A: Personal access tokens are a more convenient and secure replacement for alternate authentication credentials. 
You can create a token and limit its use to:

*	The token's lifetime
*	A Visual Studio Online account
*	[Scopes](https://www.visualstudio.com/integrate/get-started/auth/oauth#scopes) of activities that this token authorizes
 
<a name="altcred"></a>
#### Q: Can I still use alternate authentication credentials? 
 
A:  Yes. 

[!INCLUDE [alternate-credentials-procedure](_shared/alternate-credentials.md)]

#### Q: I was blocked by the system because I don't have permission. How do I get it?
 
A: [Team Foundation Server permissions](http://msdn.microsoft.com/en-us/library/ms252587)

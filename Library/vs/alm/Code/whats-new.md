toc: show
Title: What's new in version control
ShortTitle: What's new
ms.TocTitle: What's new
ms.ContentId: 3A82A72F-FFBB-416A-BF3D-E8B4768B03E8

# What's new in version control

## Git in Visual Studio 2015

### Branches

You can organize your branches hierarchically, using `/` as a delimiter in the branch name. Local branches and remote branches (including those you have not created locally) are shown separately in a tree view.

![Git branches](_img/whats-new/VCtrlGitBranches.png) 

Other changes: 

* You can now merge from remote branches, as well as local branches.

* The branch that you are merging into is now fixed to the branch that is currently checked out.

* You can now rebase from the current branch onto any local or remote branch.

* You can check out a remote branch that you are not yet tracking by double-clicking it, or right-clicking it and then selecting Checkout.

### Rebase

You can [rebase branches](./git/rebase.md).

![](git/_img/rebase/ClickRebase.png)

### History

Right click on any folder in Solution Explorer, the Changes page, or the Commit Details page, and get the history of changes to files within that folder. 

![View history from Solution Explorer](_img/whats-new/view-history-from-solution-explorer.png)

You can create a new branch or tag from the history.

![New branch or tag from simple history](_img/whats-new/simple-history-item-actions.png)

Use the detailed view to see the commit graph and how the commits diverged in the history.

![Detailed history](_img/whats-new/detailed-history.png)

In the graph, merge commits are gray and non-merge commits are a brighter color. If the graph is truncated, you can resize it. 

### Remotes management

You can add, edit, and remove Git remotes from the Repository Settings page

![](_img/whats-new/VCtrlGitRemotes.png)

### Performance and usability improvements

Changes include:

* If you're working in a large repo, you'll see significant improvements in the performance of operations like fetch, checkout, and merge.

* When you authenticate to the first cloud service in Visual Studio, we will automatically sign you in, or reduce the authentication prompts for other integrated cloud services.

### Publish to Visual Studio Online

It's easier to publish a local repo to Visual Studio Online.

![Detailed history](_img/whats-new/publish-local-repo-to-visual-studio-online-1.png)

From the Synchronization page you can publish to a new or existing Git team project.

![Detailed history](_img/whats-new/publish-local-repo-to-visual-studio-online-2.png)

## Git on the web portal

### Pull requests

Instead of merging on your dev machine, create a pull request to make sure your code quality is high before you merge.

![Create Pull Request button](_img/whats-new/create-pull-request-alert-button.png)

Your team can see the code changes, leave comments in the code, and give a "thumbs up" approval if they're satisfied with those changes. 

![Add a comment](git/_img/pull-requests/LeaveComment1.png)

See [Conduct a Git pull request](git/pull-requests.md).

### Branch policies

Branch policies help teams protect their important branches.

![Check the Require Code Reviews box](git/_img/branch-policies/RequireCodeReviews.png)  

After you configure a branch policy, your team must merge using a pull request. You cannot directly push or merge changes to the branch.

![Error, pushes to this branch are not permitted](git/_img/branch-policies/VSPushFail.png)

You can specify required reviewers. 

![Enter the path and required reviewers](git/_img/branch-policies/RequireSpecificReviewers.png)

You can also specify that if the build does not succeed, the policy rejects the pull request.

![Build rejected with details link](git/_img/branch-policies/BuildRejected.png)

See [Branch policies](git/branch-policies.md).

### New web history view

You can view the history of pushes and pull requests in a branch.

![Branch Updates sub-tab in History tab](_img/whats-new/history-branch-updates.png)

### Web edit

You can edit your code directly in your web browser.

![Edit a file in the browser](_img/whats-new/edit-file-in-web-browser-1.png)

To make sure your changes are good, compare with the previous commit. When you are ready, commit to a new branch and create a pull request to merge the changes.

![Edit a file in the browser](_img/whats-new/edit-file-in-web-browser-2.png)

You can also add, rename, and delete files.

![Add, rename, delete, or edit a file in the browser](_img/whats-new/add-edit-delete-rename-in-web-browser.png)

**Note:** To add a new folder, you must use a client tool such as Visual Studio.


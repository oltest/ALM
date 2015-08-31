Title: Rebase a topic branch
ms.TocTitle: Rebase
Description: Rebase your topic branch in Visual Studio if you want to maintain a linear history.
Toc: show
ms.ContentId: 1A72F67E-2D35-4610-912B-BA78BBDFEB57

# Rebase a topic branch

<div style="background-color:#FFE019;padding:7px 15px 3px 15px; margin-bottom:5px">
<p>**Caution:** Rebase is a very powerful tool.</p>
<p>**Never rebase a branch that is being used by other people.**</p>
<p>This means you should never rebase **master**, a release branch, or any other branch that has been pushed.</p>
</div>

Before merging a topic branch into `master`, some teams like to first rebase their topic branch onto the latest commit in `master`.

The following steps ensure that your topic branch is rebased onto the most recent commit in master, as seen by the server.  This example follows from the topic branch and pull request shown [here](./pull-requests.md).  The rebase happens *before* Raisa publishes the branch.

## Fetch the latest changes and view history

Before you rebase, always fetch to make sure that you have the latest commits from the server.

![](./_img/rebase/Fetch.png)

Now you can look at the history of master to see if any new commits were fetched in that branch. In this case, we can see that Jamal had added another commit to `master`, because `origin/master` contains a commit that `master` does not.

![](./_img/rebase/AfterFetch1.png)
![](./_img/rebase/AfterFetch2.png)

Raisa's topic branch, `users/raisa/omelette` is still based off of the local `master`:

![](./_img/rebase/StaleTopicBranch1.png)
![](./_img/rebase/StaleTopicBranch2.png)


## Choose the target branch

In this example, we want to rebase the topic branch onto the most recent commit in `master`, as seen by the server.  As we saw in the history graphs above, the local `master` is behind `origin/master`.  We have two options for the target branch of the rebase:

1. Bring `master` up to date with `origin/master`, then rebase onto `master`
2. Rebase directly onto `origin/master`

If you want to bring master up to date, do the following:

Check out `master`:

![](./_img/rebase/CheckoutMaster.png)

Then go to the Sync page and pull:

![](./_img/rebase/Pull.png)


## Checkout the source branch

To rebase a topic branch, first make sure that the topic branch is checked out.  You will always rebase the currently checked out branch *onto* another branch.

![](./_img/rebase/CheckoutSourceBranch.png)


## Start the rebase

You can now start the rebase by clicking on the Rebase flyout on the Branches page.  The source branch is always the currently checked out branch.  For the target, we will select `origin/master`, but you can also choose `master` if you know that it is up to date.

![](./_img/rebase/StartRebase.png)

And click the "Rebase" button:

![](./_img/rebase/ClickRebase.png)


## Rebase completed

If there were no conflicts, the rebase is now done.  You can see a message in the Output window that each commit was applied successfully.  The history of `users/raisa/omelette` also now shows Jamal's commit `dec3c3d6`, which was previously not reachable from this branch:

![](./_img/rebase/AfterConflictFreeRebase.png)


## Resolve conflicts

It's possible that Jamal could have modified the same files as Raisa, in which case there could be one or more conflicts.  For example, let's say Jamal had also created an omelette recipe.  After fetching from the server, the history of `master` would look like this:

![](./_img/rebase/AfterFetchWithConflict.png)

Following the same steps as before to rebase onto `origin/master`, you will see the following after clicking on the Rebase button:

![](./_img/rebase/RebaseInProgressConflict.png)

Click on the Conflicts link to resovle the conflicts, or the Abort link to abort the whole rebase operation.  Clicking on Conflicts takes you to the Resolve Conflicts page:

![](./_img/rebase/ResolveConflictsPage.png)

Where you can click on each item and use the merge tool to resolve the conflict:

![](./_img/rebase/MergeTool.png)

Once all conflicts are resolved, go back to the Branches page and continue the rebase:

![](./_img/rebase/ContinueRebase.png)

After each commit is replayed and all conflicts are resolved, you can see the final results in the Output window and the History of the topic branch:

![](./_img/rebase/AfterConflictRebase.png)
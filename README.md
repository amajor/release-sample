# Release Sample
This repository is just a sample to understand branching and releases.

## Git Flow

This video was very helpful to understand **git flow**:

https://youtu.be/aJnFGMclhU8?t=190

### Master and Develop Branches

First, you have two primary branches, `master` and `develop`.

The `master` branch always reflects production-ready code. The _develop_ branch has any features that are ready for the next release.

![Master and Develop Branch][01]

### Feature Branches

Feature branches are added for each new feature. That is, when a developer picks up a story, they create a new branch based from the `develop` branch. This new feature branch should include the story number for clarity, like `Story-123-NewFeatureDescription`.

![Start a feature branch][02]

Once that feature is tested and approved in a pull request, it is merged into the `develop` branch.

![Merge the feature branch][03]

### Release Branches

When ready for a release, a new branch is created from the `develop` branch. It should include naming related to the release for clarity, like `Release-v1.2`.

![Start a release branch][04]

You may find a few bugs to fix while prepping for a release. It's okay to fix these on the release branch. But it's best to avoid adding any NEW features to this branch.

![Add bug fixes to the release branch][05]

When the release branch is ready, merge it into `master` and tag it with the version number. GitHub recognizes tags in branches and lets us easily create releases from them.

![Merge and tag to master][06]

Now we can also safely merge any bug fixes from the release back into the `develop` branch.

![Merge to develop][07]

At this point, we can now delete the release branch.

![Delete release branch][08]

### Hot Fix Branches

If a critical bug comes up in production, a hot fix branch should be created from the `master` branch. For clarity, it should be named something like `HotFix-DescriptionOfFix`. We can create that branch from `master` so that planned work can continue as normal from `develop`.

![Create hot fix branch][09]

Once the hot fix is ready, it should be merged into `master` and tagged with a new release number.

![Merge and tag to master][10]

We'll also want to merge the hot fix branch into `develop`.

![Merge to develop][11]

The hot fix branch can then be deleted.

![Delete hot fix branch][12]

[01]: /images/01_MasterAndDevelopBranches.png "Master and Develop branch"
[02]: /images/02_StartFeatureBranch.png "Start a feature branch"
[03]: /images/03_MergeFeatureBranch.png "Merge the feature branch"
[04]: /images/04_StartReleaseBranch.png "Start a release branch"
[05]: /images/05_ReleaseBugFixes.png "Add bug fixes to release branch"
[06]: /images/06_MergeReleaseMaster.png "Merge the release branch to master"
[07]: /images/07_MergeReleaseDevelop.png "Merge the release branch to develop"
[08]: /images/08_DeleteReleaseBranch.png "Delete release branch"
[09]: /images/09_HotFixBranch.png "Create a hot fix branch"
[10]: /images/10_MergeHotFixMaster.png "Merge the hot fix to master"
[11]: /images/11_MergeHotFixDevelop.png "Merge the hot fix to develop"
[12]: /images/12_DeleteHotFixBranch.png "Delete hot fix branch"

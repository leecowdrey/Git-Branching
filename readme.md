# **About Branches**

Let’s clear that shit up and clear the basics. What are the branches you need ideally
1.) Master
2.) Develop
3.) Feature / Bug Fixes / Issues
4.) Release
5.) Hotfix

![img](https://miro.medium.com/v2/resize:fit:700/1*G9QJE5NVTyP6zfdjFOFK0g.png)

Git flow Workflow

But how are we going to manage each branch and what should be the real flow? Wouldn’t there be conflicts in branches with the modification in some other branches? Ok!! So let’s understand why we are using these all branches and what will be the impact of each branch.

1. Master branch is the most stable branch of all and will be used for production deployment.
2. Develop branch is created from master branch and will contain the latest features and bugfixes.
3. Multiple Feature branches and bugfix branches can be created from develop branch for feature development.
4. Release branch is created from develop branch with all the features which are planned for next release.
5. Hotfix branch will be created from the master branch.

# Creating and Merging Branches

We got an idea of why all these branches are used. Let us dive deeper into how merging will work and what process to be followed by developers and code owners.

At this point let us assume we already had a Master and Develop branch.
1.) To start working on a new feature, we will create a new feature branch feature/f1 out of Develop.
2.) Also a small feature started in parallel, we call that branch feature/f2.

3.) feature/f2 task is completed and it will be merged to develop and at the same time it has to be merged to feature/f1.

4.) It’s decided to put feature/f2 in the next release which is planned in the next few weeks.

5.) At this point we will create a release branch from develop with a version tag. We call this branch release/v0.1.0. And this release branch will be sent for testing.

6.) During testing we got some issues again and created some other bugfix1 and bugfix2 branches out of release. Once bugfix1 and bugfix2 are merged to release, make sure to merge back to develop and feature/f1.

7.) Once we are sure with the testing, this branch is now much more stable and we are ready to merge it to the master branch. And again send the Master branch for testing.

8.) During testing we again faced an issue, and this time we have to create a hotfix branch out of master, we call this branch hotfix/hf1.

9.) Once the hotfix branch is merged to master, it will be merged back to develop and feature/f1 branch.

10.) Cheer’s, we have the most stable branch “The Master Branch”, and we are ready to deploy this to production.

One of the most important things to be noted is that TESTING plays a major role in getting the most stable branches, so make sure to get it tested enough before you say Master as the most STABLE branch.
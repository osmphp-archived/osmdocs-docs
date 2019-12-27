# Team Workflow

"Everyone works on `master` branch" workflow I described so far is enough for getting started. However, as your team and overall Git experience grows, you may consider other options. 

This article lists some of them:

{{ toc }}

You may find more information on the Internet by searching for "Git workflow".

## Feature Branches

A **feature branch** is a temporary branch created for writing single book article or section. Once the book article or section is finished, the feature branch is merged into `master` branch and then deleted.

Typical workflow:

1. Switch to the master branch if not already there:

        git checkout master
    
2. Create new feature branch `f-introduction` for writing introduction section of the book. Be consistent in marking all feature branches in the same way, for instance with `f-` prefix:
 
        git checkout -b f-introduction

3. Do some writing and commit it to `f-introduction` branch:

        git add .
        git commit -am "..."

4. When introduction section is ready, merge `f-introduction` branch back into `master` branch, and delete the feature branch:

        git checkout master
        git merge f-introduction
        git branch -d f-introduction

5. Merge remote changes into the `master` branch push it to the remote repository:   

        git fetch
        git merge origin/master
        git push origin master

As you commit all the changes to a separate branch, not `master` branch, it means that `master` branch contains no half-done content.   

Feature branches allow to pause when writing an article or section and start working on the other part: just commit what you have written so far into the current feature branch, then create new feature branch from `master` branch and work on the other topic.

## Maintainers And Pull Requests

You may agree internally that only one or two persons can merge feature branches into the `master` branch (I'll call them **maintainers**). All the rest team only works on feature branches and then asks maintainers to merge their feature branches back into the `master` branch.

Typical workflow:

1. Ordinary team member: create new feature branch `f-introduction` locally and work on it as described in [Feature Branches](#feature-branches). 

2. Team member: push `f-introduction` feature branch to the remote repository:

        git push origin f-introduction
        
3. Team member: create a pull request on GitHub by pressing `Compare & pull request` button and then `Create pull request` button.       

4. Maintainer: review the changes made in the pull request on GitHub. If the content is OK, merge pull request into the `master` branch on GitHub by pressing `Merge pull request` button and then `Confirm merge` button. 

5. Maintainer: delete `f-introduction` feature branch in the remote repository on GitHub by navigation to `Code -> Branches` and clicking and the recycle bin icon near the branch name.

6. Team member: after the maintainer merges your pull request, delete the feature branch locally:        

        git branch -d f-introduction

## Contributors And Forks

Anyone can send you a pull request (I'll call them **contributors**), not just the team members. 

Contributors create pull requests in a very similar way as team members do:

1. Contributor: **fork** remote repository you want to contribute to on GitHub, that is, create a copy of it in your own GitHub account, by opening that target repository on GitHub and pressing `Fork` button.

2. Contributor: clone the forked repository (or the **fork**) to your local hard drive:

        git clone {fork_repo_url}
        cd {repo_name}
        
3. Contributor: create new feature branch `f-introduction` locally and work on it as described in [Feature Branches](#feature-branches). 

4. Contributor: push `f-introduction` feature branch to your remote fork:

        git push origin f-introduction
        
5. Contributor: create a pull request on GitHub in your fork by pressing `Compare & pull request` button and then `Create pull request` button.       

6. Maintainer: review the changes made in the pull request on GitHub. If the content is OK, merge pull request into the `master` branch on GitHub by pressing `Merge pull request` button and then `Confirm merge` button. 

7. Maintainer: delete `f-introduction` feature branch in the remote repository on GitHub by navigation to `Code -> Branches` and clicking and the recycle bin icon near the branch name.

8. Contributor: after the maintainer merges your pull request, delete the feature branch locally:        

        git branch -d f-introduction

## Release Branches

Once a book is ready, you may attach a **release branch** to the latest commit, let's call it `v1` branch. Later, if you make one more "big release", you can create `v2` release branch, then `v3` and so on.

After you created release branch, you can make big changes in the book on `master` branch while fixing typos on `v1` release branch. 

It is generally a good idea to merge changes you make on the release branch to the `master` branch, so that all the typos you fixed on the release branch would also be fixed on the `master` branch:

    git checkout master
    git merge v1 
 
# Contribution Guidelines

# Table of Contents

1. [Continuous Integration (CI) Best Practices with SAP – CI/CD Practices](CONTRIBUTING.md#1-continuous-integration-ci-best-practices-with-sap--cicd-practices)
2. [Main Line is Branch master](CONTRIBUTING.md#2-main-line-is-branch-master)
3. [Issue Tracking](CONTRIBUTING.md#3-issue-tracking)
4. [Quality of Changes](CONTRIBUTING.md#4-quality-of-changes)
5. [Feature Workflow](CONTRIBUTING.md#5-feature-workflow)

# 1. Continuous Integration (CI) Best Practices with SAP – CI/CD Practices

Continuous Integration (CI) focuses on the controlled integration of any change that is created in a collaborative software project into a common main line.

The CI practices are:

  * Keep everything under version control
  * Automate the build
  * Run unit test in the build
  * Commit early and often
  * Build each change
  * Fix build errors immediately
  * Keep the build fast
  * Test in a clone of the production environment
  * Make it easy to get the latest build results
  * Ensure that the build process is transparent to everyone
  * Automate the deployment


read more: https://www.sap.com/developer/tutorials/ci-best-practices-ci-cd.html


# 2. Main Line is Branch _master_

All changes that are not integrated into the _master_ do not become part of the _persephone_ project.

The sources of _master_ should always bee in a clean state. 

Commit early and often, as this reduces the time for merging activities and 
the risk of  instability introduced by a new change increases when the distance between the original base of the change and the current main line version has increased.
(read more https://www.sap.com/developer/tutorials/ci-best-practices-ci-cd.html chapter "Commit Early and Often")


# 3. Issue Tracking

For issue tracking, we just uses what github is offering us here: [issues](../../../../issues)

* If you find an issue, check if your error is already known at [issues](../../../../issues).
* If you find an unknown issue and  can't immediately provide a solution via pull request, create a new issue.
* If there is an issue in a third party and you had to open a third party issue, create a proxy Issue: 
	* The title of a proxy Issue should start with `[Proxy <the thridparty issue id>]]`
	* Provide a link or a description where to find the third party issue.
* Fixing an issue:
    * Fixing an issue don't differ from providing a new feature. Just follow [Feature Workflow](CONTRIBUTING.md#5-feature-workflow)
	* If you are fixing an issue don't forget to add a `Closes #<issue number>` either to a commits message or to the pull request. 


# 4. Quality of Changes

## Writing good commit messages

* Separate the subject from the body with a newline between the two.
* Use the body to explain what and why you have done something. 
  There is no need to describe the changes in detail, the "git diff" command will help to find out those details.
* In case you are fixing a issue, add a `Closes #<issue number>` to the subject of the commit message,
  as this will close the issue. (see https://help.github.com/articles/closing-issues-using-keywords/)
  

## How to deal with formatting?
The only formatting rule we have is to use *Unix* line endings. 

If a reformatting of a whole file is inevitable, please separate the formatting change 
form "real" changes by providing a **separate** formatting commit. This way you provide the reviews a 
fair chance and even later code-change-analyses are smarter. 

## Help to increase code quality

* Provide comments, where reasonable.
* Add java doc, where reasonable.
* Take you time to find the best names of variables/procedures etc., 
  as this improves the quality and helps to avoid errors.

## Markdown Documentation Practice

The [README.md](../README.md) is the starting point of all markdown based documentation of this project.

Please follow this guidance: 

  * The main chapters are numbered and on level `#`. Here a md code snipped:
    ```md
	# 1. Preparing the Installation 
	```
  * We only have subchapter with `##`. We avoid having sub-subchapter. 
  * if reasonable provide the goal and the result of a (sub-)chapter 
    ```md
    >**Goal:** Goal description .....
	
	[...]
	
	>**Result:** Result description .....
    ```	
  * If some subchapter gets to long you can decide to "outsource" the documentation to the [doc](.) folder. 
    The filname of the "outsource" -md-file should start with the chapter number eg. `2-` followed by a meaningful name. 
  * Here the code snippeds for adding hints and troubleshouding:
    ```md	
	>**Troubleshooting:** [.....]

	>**Hint:** [...]
    ```	
 
# 5. Feature Workflow

## General rules

* For each change create an new feature branch. 
* Direct Changes in branch _master_ are forbidden. 
* Cut features as small as possible.
* Use meaningful feature branch names. 
* Provide test for the new feature. Only providing running code is not sufficient. 
* Before creating a pull request rebase on the actual origin master. 
* After you have created a pull request, only push commit to the according feature branch dealing 
  with the provided review-comments. 
* After creating a pull request, do not add other features to the branch. 
* As long as we don't have automated test, do the needful test to verify that you did not break old coding. 
  Find details at [RunningTests](../readme/RunningTests.md)
* To not overstress the amount of branches of the origin remote, its recommended to work on you own fork.

## Create your Fork

1. Open https://github.wdf.sap.corp/SolutionPioneering/persephone-cpl281-app/ and press the _Fork_ button.
  ![](images/contributing/fork.png)

2. In the upcoming dialog select your user to create you fork.
  ![](images/contributing/yourFork.png)


## Cloning you fork repository

1. Follow https://help.github.com/articles/cloning-a-repository/ .
   If you use _SSH_ you commands will be
  
    ```
    git clone git@github.wdf.sap.corp:<your D number>/persephone-cpl281-app.git
    ```
    and if you use _HTTPS_
    ```
    git clone https://github.wdf.sap.corp/<your D number>/persephone-cpl281-app.git
    ```
2. Add the original repository as _upstream_. Her the git command using  _SSH_ :
  
    ```
    git remote add upstream git@github.wdf.sap.corp:SolutionPioneering/persephone-cpl281-app.git
    ```

## Keep your fork up-to-date with the upstream repository

Folow the nice explanation from https://help.github.com/articles/syncing-a-fork/

## Developing a new Feature

1. If not already done, clone the fork as described above. 
2. Bring your fork up to date with the upstream.
3. Decide for meaningful name of your feature and create a branch.
   ```
   git checkout -b <myFeatureName>
    ```
4. Do the needed code changes, commit this changes and push them to your fork.
5. When you have finished your work, create a Pull request. 
   When you have recently pushed  you will find a _Compare & pull request_ Button here: 
   ![](images/contributing/createPullRequestFromRecentPush.png)
   You can also create a pull request using the _Pull request_ tab
   ![](images/contributing/createPullRequestFromTab.png)
6. Verify your changes and finalize the pull request.  
   Be polite and provide a descriptive Pull request description.    
   
>**Hint:**  If you are fixing an issue don't forget to add a `Closes #<issue number>` either to a commit message or to the pull request. 





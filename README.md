# [SLC-LABS.COM](https://slc-labs.com)

Git & GitHub Handoff:  
Duru Elli, Jordan Stella

# Purpose
This documentation is designed to be a guide for Juniors joining our DevOps team. It will teach how to utilize Git and Github, the management & workflow of our code, and important practices such as CI/CD which are closely involved in our work.  
  
We will be going over the requirements, the basics explained, the importance of CI/CD, the necessary steps, and common mistakes.  
  
-----------------------------------------------------------
  

# Tools & Requirements

## Requirements

• Laptop/PC  
• Latest version of Git installed  
• GitHub account & access  


## Installing Git

The simplest way to install Git to the Windows Enviroment is by first opening an Elevated Power Shell
Execute the following command inside the Elevated Powershell
```
winget install --id Git.Git -e --source winget
```
![GitInstalPS](https://duru-e.github.io/Git-Github-Handoff/3B_GitInstallPS.png)  

For Windows Subsystem for Linux launch the console enviroment  
Execute the following command to install Git for the WSL Enviroment
```
sudo apt-get install git
```
![GitInstalPS](https://duru-e.github.io/Git-Github-Handoff/3C_GitInstallWSL.png)  

Please refer to GitHub's personalized installation guide of Git for additional operating systems located [here](https://github.com/git-guides/install-git).

## Creating Your GitHub account

Navigate to # [GitHub.com](https://github.com/)  
Enter the email you wish to sign up with and click the green "Sign up for GitHub" button.  
![GitHub](https://duru-e.github.io/Git-Github-Handoff/1A_GitHub_Sign_up.png)  

Fill out the following page with a unique e-mail and username.  
When prompted, enter the validation code you have recived in the e-mail you signed up with.  
![GitHub](https://duru-e.github.io/Git-Github-Handoff/1B_GitHub_Sign_up.png)  

You have now successfully created your new GitHub Account.  
![GitHub](https://duru-e.github.io/Git-Github-Handoff/1C_GitHub_Sign_up.png)  

For more details on ACCOUNT CREATION see the [Official DOCS](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github)  

-------------------------------------------------------------------

# Basics

## Git

Git is a distributed version control system (DVCS). This provides many features such as to track the contribution and code changes of multiple collaborators, allow rollbacks to earlier version and view history, and also work from a local environment with an easy connection to the remote repository. Most of our work will be directly involved with Git.  
[Git Official DOCS](https://git-scm.com/docs)  
## GitHub

GitHub is a server where remote Git repositories are stored. It connects developers to a cloud repository regardless of timezone and distance. 


[GitHub Official DOCS](https://docs.github.com/en)  

## Git Workflow
Understanding the Git Workflow proccess, including the features and difficulties associated with the proccess.  
![Flow](https://www.transifex.com/hs-fs/hubfs/Imported_Blog_Media/Gitflow-workflow-1-1.png?width=960&height=544&name=Gitflow-workflow-1-1.png)

Git Workflow is a thorough process generally used by large teams/projects to maintain their release standards. It includes more used branches than general GitHub Workflow, structured desig

The branches included are: 'main', 'develop', 'feature/\*', 'release/\*', 'hotfix/\*'

Main is

Develop is

Feature is

Release is

Hotfix is

## CI/CD connection


# Our Workflow

## Repositories
Repositories

GitHub makes it easy to create your first repository.  
However, we are going to follow the procedure to add a new repo that will work for the second and beyond  
Simply click on your user profile picture on the top right followed by "Repositories"  
![Repo](https://duru-e.github.io/Git-Github-Handoff/2A_GitHub_Repo.png)  

Now click the Green "New" Button on the right side of the screen under your profile picture  
![Repo](https://duru-e.github.io/Git-Github-Handoff/2B_GitHub_Repo.png)  

Here we need to give our Repository a Unique name.  
An optional Description.  
The Visibility, Public or Private.  
Optinaly you may choose the license to release your files under.  
Click the green "Create repository" button on the right and you are done.  
![Repo](https://duru-e.github.io/Git-Github-Handoff/2C_GitHub_Repo.png)  

For more details on REPOSITORY CREATION see the [Official DOCS](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)

---------------------------------------------------------------



## Staging
![Staging](https://mlim.ikim.nrw/_images/git_overview.svg)  

Understanding Staging in GitHub

Staging in GitHub is the preparation of changes before committing them to a repository. We can do this easily through Git, where we move which stage the changes are currently located. There are three local stages and one remote stage.

First is the local repository which we retrieve by cloning the remote cloud repository to our machine using the following command:
```
    git clone <repository-url>
```

The next 

Create a Repository: First, you need a repository on GitHub. You can create one by clicking on the "New" button in your GitHub account.

Clone the Repository: Use Git to clone your repository to your local machine. This can be done with the command:  


Make Changes: Edit files in your local repository as needed.

Stage Changes: To stage your changes, use the command:

```
    git add <file-name>
```

To stage all changes, use:

```
    git add .
```
   
Commit Changes: After staging, commit your changes with:
```
    git commit -m "Your commit message"
```

Staging is an essential part of the Git workflow, allowing you to control what changes are included in your next commit. You can stage changes using command-line Git or through GitHub Desktop for a more visual approach.




For more details on STAGING see the [Official DOCS](https://docs.github.com/en/enterprise-server@3.17/admin/installing-your-enterprise-server/setting-up-a-github-enterprise-server-instance/setting-up-a-staging-instance)  

-----------------------------------------------------------

## Pull

The first time we are working with a repo we will be required to use the Clone function
to do so execute the following:   
git clone https://github.com/<username>/<repository>.git

```
git clone https://github.com/Duru-E/Git-Github-Handoff.git
```
![Pull](https://duru-e.github.io/Git-Github-Handoff/4A_Pull.png)  

The next time we want to work on the repo we can execute a Pull request to ensure we have the latest version
This simple move into the repository and execute a pull request
```
git pull
```
![Pull](https://duru-e.github.io/Git-Github-Handoff/4B_Pull.png)  

We can also pull a specific branch to work on
Before we do that lets verify our current branch we are working in
```
git branch
```
![Pull](https://duru-e.github.io/Git-Github-Handoff/4C_Pull.png)  
As expected we are working in Main.  


Next we are going to change to the branch we want to work on
git checkout <branch_name>
then verify with git branch we have chaged to the intended branch
```
git checkout WorkInProgress
git branch
```
![Pull](https://duru-e.github.io/Git-Github-Handoff/4D_Pull.png) 

Finally we will ensure we are the most current version with the following
git pull <remote> <branch>
As we have alreay cloned our reposioty we can replace the <remote> (https://github.com/Duru-E/Git-Github-Handoff.git) with "origin"
git pull origin <branch> 

```
git pull origin WorkInProgress
```
![Pull](https://duru-e.github.io/Git-Github-Handoff/4E_Pull.png) 




For more details on PULL see the [Official DOCS](https://github.com/git-guides/git-pull)  


-----------------------------------------------------------


## Push

For more details on PUSH see the [Official DOCS](https://github.com/git-guides/git-push)  

---------------------------------------------------------

## Commits

For more details on COMMITS see the [Official DOCS](https://github.com/git-guides/git-commit)  


----------------------------------------------------------



# Common Mistakes
Guess we make some stuff Up/ life what web searches say  

--------------------------------------------------------------------

## Merge Conflicts

For more details on RESOLVING MERGE CONFLICTS see the [Official DOCS](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github)

--------------------------------------------------------------


## CI/CD Connection



-------------------------------------------------------

Criteria:
Scenario 1: Git & GitHub Handoff
Audience: New Junior DevOps Engineer
Focus on Git workflow, repositories, staging, commits, push/pull, common mistakes, and CI/CD connection. Tie them to real world scenarios that you maybe currently responsible for.

Must show:
• What you are doing
• How to do it
• Why it is done that way
• What can go wrong and how to fix it

-------------------------------------------------------
• 8 - 12	pages
• Authentic	screenshots	required
• Step-by-step	professionaldocumentation


old notes to delete and stuff to do

remember two spaces to make a new line

Out main file for the project

Cover download + instal of  git 
Making github accocunt

Then we need to document and make instructions of how to do everything you would do
Both for git (local machine)
and using github (using cloud)


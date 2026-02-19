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

## SSH Authentication

Correctly setting up SSH Authentication is vital for proper Git workflow.  
To do so we must create our Public and Private SSH keypairs to allow remote access to GitHUb.  
Navigate to .ssh located in your home directory, if the directory does not exist you may need to create it first  
The following commands apply to both Powershell and WSL
Replace usernamea@yexample.com with the e-mail associated with your GitHub account
when prompted press [enter] x3 as we will accept the default values for this example

```
mkdir ~/.ssh
cd ~/.ssh
ssh-keygen -C "usernamea@yexample.com"
```

Next we need to view and copy the Public Key we created  
Then copy it into our Account SSH setting in Github  

```
cat id_ed25519.pub
```
![SSH](https://duru-e.github.io/Git-Github-Handoff/SSH_A.png)  

Click your user Icon on the top right of GitHub -> Settings ->  
On the following page on the left side click -> SSH and GPG keys ->  
Finally on the right side the Green button ->  New SSH Key ->  
Paste in the public key you just prior copied -> Add SSH key

![SSH](https://duru-e.github.io/Git-Github-Handoff/SSH_B.png)  

Finally we will test our key with the following command
type yes when prompted
```
ssh -T git@github.com
yes
```

![SSH](https://duru-e.github.io/Git-Github-Handoff/SSH_C.png)  

----------------------------------------------------------

# Basics

## Git

Git is a distributed version control system (DVCS). This provides many features such as to track the contribution and code changes of multiple collaborators, allow rollbacks to earlier version and view history, and also work from a local environment with an easy connection to the remote repository. Most of our work will be directly involved with Git.  
[Git Official DOCS](https://git-scm.com/docs)  

## GitHub

GitHub is a server where remote Git repositories are stored. It connects developers to a cloud repository regardless of timezone and distance. Developers are able to easily clone the cloud repository to their machine and begin working on their local repository. When they have completed their current goal, they are able to easily push their local repository back up to the cloud repository and update it seamlessly.

[GitHub Official DOCS](https://docs.github.com/en)  

## Git Workflow
Understanding the Git Workflow proccess, including the features and difficulties associated with the proccess.  
![Flow](https://github.com/Duru-E/Git-Github-Handoff/blob/Duru-E-patch-1-1/Gitflow-Workflow.png)

Git Workflow is a thorough process generally used by large teams/projects to maintain their release standards. It includes more used branches than general GitHub Workflow due to the importance of good quality content and still be efficient as well. It is a clearly structured design where there are many branches for their own unique purpose which we will go over.

The branches included are: 'main', 'develop', 'feature/\*', 'release/\*', 'hotfix/\*'

Main is the most important branch, it is crucial to not send any updates that are possibly fault to this branch and even more important to never commit immediately to main branch. This is our production-ready branch where it must be functioning as intended with zero bugs intentionally released.

Develop is the branch designated for branching & integrating feature branches with active development. It is derived from the main branch. Here we confirm that the features will function properly and verify the code is consistent and reliable.

Feature is designed for building new features, testing purposes, or bug-fixing. They are branched out from the develop branch and will be merged back into the develop branch again when it is complete and ready for the verification proccesses.

Release is when our feature branches from the develop branches are verified and ready to undergo QA, bug fixes, and smaller updates. This is branched from a progressed develop branch, it is the last branch before the code is confidently integrated into main and ready for release. 

Hotfix is when an important issue is found and needs to be fixed as soon as possible. It is branched from main and then pushed back into main when the hotfix is ready to be deployed. It allows code production to be very quick and efficient and is designed to be a quick fix for whatever the issue is.

## CI/CD connection

CI/CD (Continuous Integration / Continuous Development) is a crucial practice deeply involved in our work process. 

---

# Our Workflow

## Repositories

Repositories are the main location where the code, files, and revision history is all stored. The source repository is generally the remote repository located on the cloud, and specifically in our case, stored in GitHub servers.  
  
When you clone a repository, you have an identical copy of the repository where you can make your own changes and commit to your own repository without issues. You will also be able to push your local copy of the repistory up to the cloud repository you cloned it from. This is how you would push changes to the main codebase. We will be going further into detail with the upcoming sections. First, we will go over making your own repository.  
  
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
As we have already cloned our repository we can replace the <remote> (https://github.com/Duru-E/Git-Github-Handoff.git) with "origin"
git pull origin <branch> 

```
git pull origin WorkInProgress
```
![Pull](https://duru-e.github.io/Git-Github-Handoff/4E_Pull.png) 


For more details on PULL see the [Official DOCS](https://github.com/git-guides/git-pull)  


-----------------------------------------------------------

## Staging
![Staging](https://github.com/Duru-E/Git-Github-Handoff/blob/Duru-E-patch-1-1/Staging.png)  

Understanding Staging in GitHub

Staging in GitHub is the preparation of changes before committing them to a repository. We can do this easily through Git, where we use a quick and simple command to add our changes to the Staging Area. We will start with the local repository in order to add changes. 

First is the local repository which we retrieve by cloning the remote cloud repository to our machine using the following command:
```
git clone <repository-url>
```
  
At this stage we will be making our changes to the code and files.  
  
Now to stage our changes and set them in a prepared state, we will use the following command:
```
git add <file-name>
```

![STAGING](https://duru-e.github.io/Git-Github-Handoff/Staging_A.png)  

  
Or to stage all changes, use: 

```
git add .
```  

![STAGING](https://duru-e.github.io/Git-Github-Handoff/Staging_B.png)  

Now that all the changes are staged, they are ready to be PUSHED with:  

```
git commit -m "Your commit message"
```
![STAGING](https://duru-e.github.io/Git-Github-Handoff/Staging_C.png)  

Staging is essential for Git workflow, it allows you to easily pick and choose which changes are ready to be committed and sent to the repository. 


For more details on STAGING see the [Official DOCS](https://docs.github.com/en/enterprise-server@3.17/admin/installing-your-enterprise-server/setting-up-a-github-enterprise-server-instance/setting-up-a-staging-instance)  

-----------------------------------------------------------

## Push

Before we can push we need to tell git the location to send the push to.  
this is done with the following:

git remote set-url origin git@github.com:<username>/<repo>.git
the username is the REPO OWENERS username and may not be your own

```
 git remote set-url origin git@github.com:Duru-E/Git-Github-Handoff.git
```

![PUSH](https://duru-e.github.io/Git-Github-Handoff/Push_B.png)  


After all your changes to the active branch have been made it is time to Push them to the repo  
This is done with the following command  
git push origin <branch>

```
git push origin pushDemo
```

![PUSH](https://duru-e.github.io/Git-Github-Handoff/Push_A.png)  


For more details on PUSH see the [Official DOCS](https://github.com/git-guides/git-push)  

---------------------------------------------------------

## Commits

To complete a Commit from a branch into your main Repo you must first Select the branch in GitHub  
![COMMIT](https://duru-e.github.io/Git-Github-Handoff/Commit_A.png)  

Then click on the Blue text stating X Commits ahead of main to review the changes  
![COMMIT](https://duru-e.github.io/Git-Github-Handoff/Commit_B.png)  

Once the changes have been Validated you may cick -> Create pull request  
![COMMIT](https://duru-e.github.io/Git-Github-Handoff/Commit_D.png)  
  



For more details on COMMITS see the [Official DOCS](https://github.com/git-guides/git-commit)  


----------------------------------------------------------



# Common Mistakes


*****************

Branch fell behind main  
Needed to Merge with Main before Push was allowed

![COMMIT](https://duru-e.github.io/Git-Github-Handoff/MergeConflict_Fix.png)  


## Merge Conflicts

For more details on RESOLVING MERGE CONFLICTS see the [Official DOCS](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github)

## Committing to Main

## Committing to Wrong Branches

## Forgetting to Pull before Push

Simply forgetting to pull the latest version of the repository before releasing your version could cause many issues. For example, if an important bug-fix is released after you pulled your close and you forget to update, your version will not contain this bug-fix. This can cause major issues in the main repository and it could even cause further bugs due to possible conflicts. It is important to always pull the latest version of the repository to ensure your repository is not missing any key updates and will work efficiently with the current version.

## Forgetting to Delete Merged Branches


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


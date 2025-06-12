GIT and GITHUB

1) what will happen if we do git fetch

	git fetch + git merge = git pull
	
2) Git merge vs git rebase

	git merge : a new commit will be created and branches get merged
	git rebase : a linear form of commits gets created
	
	newer commits will be places last in the git history
	older commits will be formed in first position

3) explain the branching strategy that are using in your organization

4) explain the git workflow ?

5) how can we clone only specific branch

6) what is git cherry pick ?

## Scenario 1
* You've accidentally comitted sensitive information, such as APT keys or pesswords, to a Git repository. How would you handle this situation?

**Answer**:

I would first try to remove the sensitive information from the commit history using “git filter-branch’ or "git rebase -i'. If the information has been pushed to a remote repository, I would then force-push the changes after modifying the history locally. Additionally, I would rotate any compromised credentials and take measures to ensure that sensitive information is properly handled in the future, such as using environment variables or gitignore files.


## Scenario 2
* You are working on a feature branch and need to incorporate changes from the main branch into your feature branch. How would you do this?

**Answer**:

First, I would ensure that my feature branch is up to date by checking it out (git checkout feature-branch’) and pulling the latest changes from the main branch ("git pull origin main’).Then, I would rebase my feature branch onto the main branch ("git rebase main’). This would apply my changes on top of the latest changes from the main branch, ensuring a clean history. Finally, I would resolve any conflicts that may arise during the rebase process. 

## Scenario 3
* You've made several commits on your feature branch but realize that one of the earlier commits introduced a bug. How would you fix this without losing the other changes on your branch?

**Answer**:

I would use 'git rebase -i' to interactively rebase my feature branch, specifying the commit where the bug was introduced. During the interactive rebase, I would mark the buggy commit as "edit". Once Git pauses at that commit during the rebase process, 
I would make the necessary changes to fix the bug and then use “git commit --amend’ to update the commit. After fixing the bug, I would continue the rebase process (‘git rebase ~~continue), allowing Git to apply the subsequent commits on top of the fixed commit.

## Scenario 4 
* You've been working on a feature branch for some time and want to share your progress with your team for review. How would you go 
about this?

**Answer**:

First, I would ensure that my feature branch is up to date with the latest
changes from the main branch by rebasing it (' git rebase main’). Then, I would push my 
feature branch to the remote repository ("git push origin feature-branch’). Finally, I
would create a pull request (PR) or merge request (MR) in the repository’s hosting platform 
(e.g., GitHub, GitLab) to initiate the review process. I would provide relevant details in 
the PR/MR description and notify my team members for their review and feedback. 

## Scenario 5 
* You've accidentally deleted a file that you need from your local repository. How would you recover it?

**Answer**:

I would use the "git checkout” command to restore the deleted file from the Git
repository’s history. For example, I could use 'git checkout HEAD~1 --path/to/deleted/file' to retrieve the file from the previous commit. If the deletion was recent and I ;
haven't made many changes since, I could also use "git reflog’ to find the commit where the 
file was deleted and then checkout that commit to restore the file.
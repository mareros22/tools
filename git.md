# What??
If you are not familiar with Git and you feel like everyone around you already knows what they are doing, that is totally normal. 

## What is a Repository?
A repository is a set of files and their history. The repository is hosted on a server, and you can make changes to the files (or add or remove files) locally by making a copy (or clone) of the repository on your local machine. Typically we make a new repository for each course or project.

## What is a Commit?
A commit is like a checkpoint. When you make a commit, you are saving the current state of the repository. You can later return to that commit and access the saved version of each of your files. When you make changes locally, you will need to commit those changes and push them to the server so that they are saved globally.

## I'm still confused
Check out this awesome geeksforgeeks resource ([link](https://www.geeksforgeeks.org/git/git-introduction/)) for a great introduction to Git.

# Cloning a Repository
1. Visit the Repository webpage and copy the clone link by clicking the Code button and then the copy icon next to the web URL
<img width="250" height="225" alt="image" src="https://github.com/user-attachments/assets/353d943d-4357-48af-b87b-ee5a09866aa5" />

2. Using your command prompt, navigate to the location where you want to clone the repository
3. Type in `git clone <repository>`, where `<repository>` is the web link you copied in step 1

# Pulling from the Repo
Each time you work on the code, you will want to make sure you have the most updated version of the project.
Enter `git pull` to your command prompt to get any updates from the server.

# Making Changes
When you make changes to the code, you will want to save your changes to the repository. There are three steps to do this:
1. Adding: you will need to stage your changes by adding any files you changed to the commit using `git add <filename>`
   - You can use `git add --all` to add all changes
   - Use `git status` to see which files have unstaged changes
2. Committing: When you have added all the files, bundle your changes into a commit with `git commit -m "<message>"`, where `<message>` is a commit message
  - Your commit message should be a description of the changes that you have made. Some courses have guidelines for commit messages, so refer to any relevant specifications and style guides.
3. Pushing: You then need to send your commit to the server to update it globally. Use `git push`.
If you want to hide local changes, you can use `git stash`. You can then revisit these changes with `git stash pop` or discard them with `git stash drop`

# Branches
Sometimes it is useful to test out changes without it impacting the whole project. You can use branching to create a copy of the repository. This copy has the same functionality of the main branch, and you can later merge the changes you make in the branch to another branch.
- Create a branch with `git branch <branch_name>`
  - You can use `git branch` to see a list of the branches in your repository. There will be a * next to the branch you are currently on
- To move between branches, use `git checkout <branch_name>`
- To delete an (merged) branch, use `git branch -d <branch_name>`
  - If you need to delete an unmerged branch, you can force the deletion with `git branch -D <branch_name>` 

# Merging
To merge the changes you have made in one branch to another, you should first switch to the branch you want to merge into, then use `git merge <branch_name>`
- Example: if we have a branch _test-branch_ that we want to merge into _main_, we would do the following:
  1. Ensure all changes have been committed in _test-branch_
  2. `git checkout main` to switch to _main_
  3. `git merge test-branch` to merge _test-branch_'s changes to _main_

# Conflicts
When your code conflicts with another commit that was made since you last pulled, or when you are merging to a branch with incompatable changes, it will warn you that there is a merge conflict. This will need to be resolved before you can finish what you are doing.
You have a few options:
- Cancel the merge with `git merge --abort`
- Fix the conflict
  - Use `git status` to see which files have conflicts
  - Open the files in your editor - your editor should show you the differences between the versions
  - Make any necessary fixes
  - Stage your changes with `git add <filename>`
  - Once all conflicts are fixed, commit your changes

# Undoing Changes
- Unstaged changes:
  - To undo all unstaged changes on your local machine, use `git reset --hard HEAD`
  - To undo unstaged changes to one file, use `git restore <filename>` or `git checkout HEAD -- <filepath>`
- Staged changes:
  - Unstage the changes with `git restore --staged <filename>`, then use the Unstaged Changes approach
  - To revert commited changes, use `git reset --soft HEAD~1`
- Pushed Changes:
  - To return to a previous commit, use `git reset <commit>`, where `<commit>` is the commit hash obtained from running `git log`
  - To undo the current commit, use `git revert <commit>` where `<commit>` is the commit hash of the current commit
  - To return just one file to a previous commit's version, use `git restore source=<commit> <filename>`, where `<commit>` is the commit hash to return to

# Tags
Tags can be useful to mark commits. For many courses, you will be required to tag the commits you are submitting for certain assignments. 
1. You can tag the current commit with `git tag <tagname>`
2. Push the tag with `git push --tags`
Tag names must be unique, so to change which commit the tag is attached to, you will need to delete the tag and re-add it. To remove a tag, follow these steps:
1. `git tag -d <tagname>`
2. `git push origin --delete <tagname>`
   
# Useful Commands
- `git status`: view current branch, staged and unstaged files, etc
- `git log`: view commit history (including commit hashes)
  - `git log --stat` to show list of files changed per commit

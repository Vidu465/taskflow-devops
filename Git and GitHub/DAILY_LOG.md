## --------------- Git & GitHub --------------------

# What is Git?
Git = A Version Control System (VCS).
Tracks every change made to your project.
Lets you save versions (commits), work with branches, and restore older versions.
Works locally on your computer.

Think of Git as a game save system.

Version 1 → Version 2 → Version 3

# What is GitHub?
GitHub = A cloud website that stores Git repositories.
Used for collaboration with teams.
Stores branches, Pull Requests, Issues, CI/CD workflows, etc.

# Git Workflow
Create Project
   ▼
git clone
   ▼
Create Branch
   ▼
Write Code
   ▼
git add
   ▼
git commit
   ▼
git push
   ▼
Pull Request
   ▼
Code Review
   ▼
Merge
   ▼
main Branch
   ▼
GitHub Actions
   ▼
CI/CD Pipeline
   ▼
Docker Build
   ▼
Deploy


# One-Line Memory Trick
# Command	           |       Simple Meaning
git clone	           |     Copy project from GitHub
git status	           |     Check what's changed
git add .	           |     Prepare changes to save
git commit -m	       |     Save a checkpoint
git push	           |     Upload changes to GitHub
git pull	           |     Get the latest project updates
git fetch	           |     Check for updates without applying them
git log	               |     View project history
git diff	           |     See what changed
git branch	           |     View branches
git checkout -b	       |     Create & switch to a new branch
git checkout	       |     Switch branches
git merge	           |     Combine branches
git rebase	           |     Move your work onto the latest branch history
git stash	           |     Temporarily hide unfinished work
git stash pop	       |     Restore hidden work
git tag	               |     Mark a project version
git push --tags	       |     Upload version tags
git cherry-pick	       |     Copy one commit
git remote -v	       |     Show GitHub connection
git config --list	   |     Show Git settings
docker compose up	   |     Start the application
docker compose up --build	Rebuild and start the application
docker compose down	   |     Stop the application

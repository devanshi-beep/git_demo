# git_demo
# A list of git commands to be needed

Basic Git Commands
git --version          # Check git version
git help               # Git help
git help commit        # Help for a specific command

🔹 Repository Setup
git init               # Initialize a new repo
git clone <url>        # Clone a repository

🔹 File & Status Commands
git status             # Check repo status
git add file.txt       # Add specific file
git add .              # Add all files
git restore file.txt   # Discard changes in file
git rm file.txt        # Remove file

🔹 Commit Commands
git commit -m "message"      # Commit staged files
git commit -am "message"     # Add + commit tracked files
git log                      # Commit history
git log --oneline            # Short log
git show <commit-id>         # Show commit details

🔹 Branching
git branch                  # List branches
git branch new-branch        # Create branch
git checkout branch-name     # Switch branch
git checkout -b new-branch  # Create + switch
git merge branch-name        # Merge branch
git branch -d branch-name    # Delete branch

📁 Create a folder
mkdir project

📄 Create a file
touch index.html


or (Windows-friendly)

echo. > index.html

📂 Create folder + file together
mkdir src
touch src/app.c

🔹 3. Add Files to Staging Area
Add single file
git add index.html

Add all files
git add .

🔹 4. Commit Changes
git commit -m "Initial commit"


Check commit history:

git log


Short version:

git log --oneline

🔹 5. Connect Local Repo to GitHub (First Time)
Add remote repository
git remote add origin https://github.com/USERNAME/REPO_NAME.git


Check remote:

git remote -v




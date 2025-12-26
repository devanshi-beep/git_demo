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



1️⃣ Basic flow to push code to GitHub

Git always follows this order:

Edit → Add → Commit → Push

2️⃣ Check repo status
git status


Shows modified, untracked, staged files.

3️⃣ Push ONE specific file
git add filename.ext
git commit -m "Added filename"
git push origin main


📌 Example:

git add index.html
git commit -m "Add index page"
git push origin main

4️⃣ Push multiple selected files
git add file1 file2 file3
git commit -m "Added selected files"
git push origin main

5️⃣ Push ALL files
git add .
git commit -m "Updated all files"
git push origin main


✅ git add . stages everything (new + modified).

6️⃣ Push only tracked files (no new files)
git add -u
git commit -m "Updated tracked files"
git push origin main

7️⃣ Push without writing commit message manually
git commit -am "Quick update"
git push origin main


⚠️ Works only for already tracked files.

8️⃣ First-time push (set upstream)
git push -u origin main


After this, you can just use:

git push

9️⃣ Push to a different branch
git push origin branch_name


Example:

git push origin dev

🔟 Force push (⚠️ dangerous)
git push origin main --force


or safer:

git push origin main --force-with-lease


Use only if you know what you’re doing.

1️⃣1️⃣ Push tags
git push origin --tags

1️⃣2️⃣ Push everything (branches + tags)
git push --all



🔁 Git commit workflow

Edit → Add → Commit

👉 Remember: You cannot commit without adding (staging) first.

1️⃣ Check file status
git status


Shows:

Untracked files

Modified files

Staged files

2️⃣ Commit ONE specific file
git add filename.ext
git commit -m "Commit message"


📌 Example:

git add main.c
git commit -m "Added main program"

3️⃣ Commit multiple selected files
git add file1 file2 file3
git commit -m "Added selected files"

4️⃣ Commit ALL files
git add .
git commit -m "Committed all files"


✅ Adds:

New files

Modified files

Deleted files

5️⃣ Commit only tracked files (no new files)
git add -u
git commit -m "Updated tracked files"

6️⃣ Commit tracked files in one command
git commit -am "Quick commit"


⚠️ Works ONLY for already tracked files
❌ Does not include new files

7️⃣ Commit without -m (opens editor)
git commit


✍️ Git opens editor to write commit message.

8️⃣ Amend (edit) last commit
Change commit message
git commit --amend

Add files to last commit
git add filename
git commit --amend


⚠️ Don’t amend commits already pushed (unless force push).

9️⃣ Commit with detailed message
git commit -m "Short title" -m "Detailed description"

🔟 View commit history
git log


Short form:

git log --oneline

1️⃣1️⃣ Undo last commit (keep files)
git reset --soft HEAD~1

1️⃣2️⃣ Delete last commit completely
git reset --hard HEAD~1


⚠️ Permanent deletion.


🌿 GIT BRANCH COMMANDS
1️⃣ Check current branch
git branch


👉 Current branch shows with *

2️⃣ List all branches
Local branches
git branch

Remote branches
git branch -r

All (local + remote)
git branch -a

3️⃣ Create a new branch
git branch branch_name


Example:

git branch feature-login

4️⃣ Switch to a branch
git checkout branch_name


OR (modern command)

git switch branch_name

5️⃣ Create & switch branch (one command)
git checkout -b branch_name


OR

git switch -c branch_name

6️⃣ Rename a branch
Rename current branch
git branch -m new_name

Rename another branch
git branch -m old_name new_name

7️⃣ Delete a branch
Safe delete (merged branches only)
git branch -d branch_name

Force delete
git branch -D branch_name

8️⃣ Show last commit of each branch
git branch -v

9️⃣ Check which branches are merged
git branch --merged


Unmerged:

git branch --no-merged

🔀 GIT MERGE COMMANDS
🔁 Basic merge workflow

1️⃣ Switch to target branch
2️⃣ Merge source branch

🔟 Merge a branch into current branch
git merge branch_name


📌 Example:

git checkout main
git merge feature-login

1️⃣1️⃣ Fast-forward merge

Occurs automatically when no new commits exist on target branch.

git merge feature-branch

1️⃣2️⃣ No fast-forward merge
git merge --no-ff branch_name


Creates a merge commit even if fast-forward is possible.

1️⃣3️⃣ Abort a merge (if conflict occurs)
git merge --abort

1️⃣4️⃣ Resolve merge conflict

Steps:

Open conflicted file

Fix code

Add file

Commit

git add filename
git commit

1️⃣5️⃣ Check merge conflicts
git status

1️⃣6️⃣ Re-merge after conflict resolution
git commit

🌍 REMOTE BRANCH COMMANDS
1️⃣7️⃣ Push a branch to GitHub
git push origin branch_name

1️⃣8️⃣ Set upstream for branch
git push -u origin branch_name

1️⃣9️⃣ Delete remote branch
git push origin --delete branch_name

2️⃣0️⃣ Fetch remote branches
git fetch

2️⃣1️⃣ Checkout remote branch
git checkout -b branch_name origin/branch_name


OR

git switch branch_name



1️⃣ Check where HEAD is pointing
git show HEAD


or

git log -1

2️⃣ Show HEAD reference
cat .git/HEAD

3️⃣ Move HEAD to a branch
git checkout branch_name


or

git switch branch_name

4️⃣ Detach HEAD (checkout commit)
git checkout <commit-hash>

5️⃣ Create branch from detached HEAD
git checkout -b new_branch


✔ Saves your work.

⏪ HEAD & COMMIT NAVIGATION
6️⃣ Previous commit
git checkout HEAD~1

7️⃣ Go back multiple commits
git checkout HEAD~3

8️⃣ Specific parent commit
git checkout HEAD^


Second parent (merge commit):

git checkout HEAD^2

9️⃣ Compare HEAD with previous commit
git diff HEAD~1

🔁 RESET COMMANDS USING HEAD
🔟 Soft reset (keep changes staged)
git reset --soft HEAD~1

1️⃣1️⃣ Mixed reset (default – keep changes unstaged)
git reset HEAD~1


or

git reset --mixed HEAD~1

1️⃣2️⃣ Hard reset (delete everything)
git reset --hard HEAD~1


⚠️ Permanent deletion

✏️ AMEND USING HEAD
1️⃣3️⃣ Modify last commit
git commit --amend


Uses:

Change commit message

Add files to last commit

🔄 HEAD & REBASE
1️⃣4️⃣ Rebase current branch
git rebase branch_name

1️⃣5️⃣ Interactive rebase (advanced)
git rebase -i HEAD~3


Used for:

Squash commits

Reorder commits

Edit commit messages

📊 LOG & HEAD
1️⃣6️⃣ Show HEAD in logs
git log --oneline --decorate

1️⃣7️⃣ Show HEAD movements
git reflog


🔥 Very important — recover lost commits.

🚨 Recover deleted commits using HEAD
git reset --hard <hash-from-reflog>

🧠 QUICK SUMMARY TABLE
Command	Purpose
HEAD	Pointer to current commit
HEAD~1	Previous commit
HEAD^	Parent commit
git reset --soft HEAD~1	Undo commit, keep staged
git reset --hard HEAD~1	Delete commit
git checkout HEAD~1	View old commit
git reflog	Recover lost commits
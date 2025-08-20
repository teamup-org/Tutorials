Getting Started with Git at AFG (Apps for Good)
Welcome to Git collaboration at AFG! This guide is your go-to reference for collaborating effectively with your team using Git and GitHub.
 Joining the GitHub Organization
You will receive an invitation by email to join the GitHub organization: teamup-org. Make sure to accept it to gain access to the repositories.

🔐 Accessing the Repository
Each project has a private GitHub repository under the teamup-org organization.
Repositories are divided by teams, e.g., capmetro or afg-su-25
Members are invited via email and assigned roles like Maintainer or Write

             📸: Capmetro team members list with Maintainer tags.
👥 Roles
Maintainers: Lead the team on GitHub. They approve pull requests, review code, resolve conflicts, and ensure organization.
Contributors: Team members who push changes via branches and pull requests.
📂 Repo Structure (Example: CapMetro)
/Frontend     : UI-related files
/Backend      : Server logic, APIs
/Database     : Database logic & models
/Docs         : Documentation files (README, API specs, etc.)

📸: Repo folder structure in GitHub.

🔗 Cloning the Repository
Why SSH instead of HTTPS?
SSH offers enhanced security and convenience - once configured, you won't need to enter credentials for each Git operation. SSH doesn't require repetitive authentication for every repository action, which saves time.
Clone with SSH (recommended)
git clone git@github.com:teamup-org/YOUR-REPO-NAME.git
cd YOUR-REPO-NAME
Alternative: Clone with HTTPS (less secure, requires passwords)

git clone https://github.com/teamup-org/YOUR-REPO-NAME.git
cd YOUR-REPO-NAME
💡 Pro tip: Once SSH is set up, all your git push and git pull commands work seamlessly without asking for passwords!
If you want to generate the SSH key yourself instead of copying it:
One-time SSH setup (do this once)
1. Generate your SSH key:
bash
ssh-keygen -t rsa -b 4096 -C "your.email@example.com"
Press Enter to accept default file location, then create a passphrase
2. Add your SSH key to the ssh-agent:
bash
# Start the ssh-agent
eval "$(ssh-agent -s)"

# Add your SSH private key
ssh-add ~/.ssh/id_rsa
3. Copy your public key:
# On Mac/Linux
cat ~/.ssh/id_rsa.pub
# On Windows (PowerShell)
Get-Content ~/.ssh/id_rsa.pub
4. Add the key to GitHub:
Go to GitHub.com → Settings → SSH and GPG keys
Click "New SSH key"
Paste your public key and give it a title
Click "Add SSH key"
5. Test your connection:

ssh -T git@github.com

📋 Simplified Daily Workflow
Most common scenario: Working on your existing branch
bash
# 1. See what's changed (do this often!)
git status

# 2. Add and commit your work
git add .
git commit -m "fix: update login validation"

# 3. Get latest changes from team
git pull

# 4. Send your work
git push

2. Starting a new task (once per feature)

# 1. Make sure you're on main and updated
git checkout main
git pull
# 2. Create your feature branch
git checkout -b feature/your-name-task
# 3. Now work normally (use the workflow above)

📸 Screenshot idea: GitHub showing list of branches.
3. Make your changes
# Check modified files
git status

# Add your files
git add .
# Or add specific files
git add src/components/Button.js

# Commit your changes
git commit -m "Added new UI components for login form"

# Push your branch
git push origin feature/your-name-task
📝 Commit Conventions
Use clear and descriptive messages:
Recommended format:
type: short description

More detailed description if needed
Commit types:
feat: new feature
fix: bug fix
docs: documentation
style: formatting, no logic changes
refactor: code refactoring
test: adding tests
Examples:
feat: add user authentication system
fix: resolve login redirect issue
docs: update API documentation
📩 Making a Pull Request (PR)
Go to your repo on GitHub
Click Compare & Pull Request
Add title & description
Tag reviewers (especially Maintainers)
Submit!
📸: GitHub pull request page with reviewers and labels.
⚠️ Merge Conflicts
Merge conflicts happen when two branches change the same part of a file.
To fix:
Pull the latest main into your branch:
git pull origin main
Git will show where the conflicts are
Edit the file manually to fix the code
Once fixed:
git add .
git commit -m "Resolved merge conflict"
git push
Then re-request review or complete the PR
📸: showing a merge conflict.
🆘 Common Error Handling
Undo last commit (not pushed)
git reset --soft HEAD~1
Undo uncommitted changes
git checkout -- filename.js
# or for all files
git checkout .
Switch branches with uncommitted changes
git stash
git checkout other-branch
git stash pop  # to recover changes
Push fails
# Get latest changes
git pull origin feature/your-branch-name
# Resolve conflicts if needed
git push origin feature/your-branch-name
🔧 Useful Commands
Repository information
git status           # File status
git log              # Commit history
git log --oneline    # Condensed history
git branch           # List local branches
git branch -a        # List all branches
Navigation
git checkout main                    # Go to main
git checkout feature/branch-name     # Go to a branch
git checkout -b new-branch           # Create and go to new branch
Synchronization
git fetch origin     # Get remote info
git pull origin main # Get and merge main
Branch management (when needed
git branch                          # See all branches
git checkout -b feature/new-task    # Create new branch (once per task)
git checkout main                   # Switch back to main (rarely needed)

When you need help
git stash            # Temporarily save changes
git stash pop        # Get stashed changes back

📉 Best Practices
Branch often: One task = one branch
Commit clearly: Describe your changes with meaningful messages
Pull often: Always pull before starting new work
Communicate: Use GitHub issues & PR comments
Test before pushing: Make sure your code works
Keep commits small: Easier to review and debug
Delete merged branches: Keep your workspace clean
✨ For Maintainers
Review pull requests promptly
Ensure code is working and conflict-free before merging
Tag releases, keep main clean
Encourage team to use consistent naming for branches and commits
Provide constructive feedback in code reviews
Help resolve merge conflicts when needed
📸: PR approval view with Maintainer actions.
📚 Git Glossary
Branch: A parallel version of the code to develop a feature 
Commit: A save of your changes with a descriptive message 
Pull Request (PR): Request to merge your branch into main 
Merge: Combine two branches together 
Conflict: When Git cannot automatically merge two versions
 Remote: The distant repository on GitHub 
Local: Your local copy of the repository on your machine
🚀 Complete Workflow - Practical Example
Daily work (most common)

# Check what you've changed
git status

# Save your work
git add .
git commit -m "feat: add user profile validation"

# Get team updates and send your work
git pull
git push
Starting a new feature (once per task)

# Start fresh from main
git checkout main
git pull
git checkout -b feature/john-user-profile

# Work on it (use daily workflow above)
# ... make changes ...
git add .
git commit -m "feat: add user profile page"
git push origin feature/john-user-profile

# Create PR on GitHub, get it merged

# Clean up after merge
git checkout main
git pull
git branch -d feature/john-user-profile

🌟 You're Ready!
You now have what you need to work as a team on GitHub in AFG.
Need help? Ask your Maintainer or reach out on Discord.
Happy coding and collaboration!

AFG Devs Bootcamp 



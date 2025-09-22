## Version Control

Modern software developers collaborate across the world on the same codebase without overwriting each other’s work. This course introduces version control systems, core Linux command-line skills, and a practical Git/GitHub workflow so you can manage code revisions professionally and ship with confidence.

### What you will achieve
- **Implement version control systems**
- **Navigate and configure using the command line**
- **Manage code revisions**
- **Create and use a GitHub repository**

> Key idea: Version control is your project’s time machine. It records every meaningful change, who made it, and why—enabling safe experimentation, rapid collaboration, and reliable releases.

---

## Course Modules

### Module 1: Software Collaboration
In this module, you’ll use version control (and its workflows) to bring order to large software projects and reduce risk from mistakes and bugs.

After completing this module, you will be able to:
- **Describe** how modern software teams collaborate on the same codebase
- **List** different version control systems and methodologies (e.g., Git, centralized VCS)
- **Illustrate** a standard software development workflow (branch → commit → review → merge → release)

> Pro tip: Treat your main branch as always deployable. Work in short-lived feature branches and merge via pull requests after review and CI checks.

---

### Module 2: Command Line
Learn essential Linux/Unix shell commands to traverse directories, manage files, and build workflows with pipes and redirection.

After completing this module, you will be able to:
- **Describe** what the command line is and how it’s used
- **Traverse** your filesystem from the terminal
- **Create, rename, and delete** files and folders using Unix commands
- **Use** pipes `|` and redirection `>` `>>` `<` to automate tasks

Common commands you’ll practice:

```bash
# Navigation
pwd                 # print working directory
ls -la              # list all files with details
cd /path/to/dir     # change directory

# Files & folders
touch notes.txt     # create file
mkdir src           # create directory
mv old.txt new.txt  # rename/move
cp a.txt b.txt      # copy
rm file.txt         # remove file
rm -r folder        # remove directory recursively

# Pipes & redirection
cat access.log | grep "ERROR" > errors.log   # pipe output and save
echo "Hello" >> notes.txt                   # append to file
```

> Remember: Pipes connect commands by passing output of the left command as input to the right one. Redirection sends command output to files.

---

### Module 3: Git
Develop a strong conceptual understanding of Git and how it is used in real projects. You’ll install Git, create a local repository, commit changes, create a remote repository, and push commits.

After completing this module, you will be able to:
- **Outline** Git principles (snapshots, commits, branches, merges)
- **Use** a GitHub repository (clone, push, pull, PRs)
- **Describe** steps in a standard GitHub workflow
- **Create branches** and **merge** different branches and sources
- **Explain** how code flows from local development → version control → production

Canonical GitHub workflow:

```bash
# Setup (one-time)
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Start a project
git init                       # initialize local repo
git add .                      # stage changes
git commit -m "Initial commit" # commit snapshot

# Connect to GitHub (remote)
git remote add origin https://github.com/user/repo.git
git branch -M main
git push -u origin main        # push and set upstream

# Daily workflow
git checkout -b feature/login  # create and switch to feature branch
# ... edit files ...
git status                     # see changes
git add .
git commit -m "feat(login): add form and validation"
git push -u origin feature/login

# Open a Pull Request on GitHub → get review → squash/merge

# Sync local after merge
git checkout main
git pull origin main
git branch -d feature/login
```

> Commit messages matter. Use clear, imperative summaries (e.g., "fix(auth): handle expired tokens"). Smaller, focused commits make review and rollback easier.

Branching and merging tips:
- **Short-lived branches** reduce merge conflicts
- **Rebase locally** to tidy history; **merge** in shared branches to preserve context
- **Protect main** with required reviews and passing CI checks

---

### Module 4: Graded Assessment
You’ll synthesize the skills from previous modules to manage a project on GitHub, then reflect on your learning path.

After completing this module, you will be able to:
- **Recap** all topics covered
- **Apply** all skills in a graded project (repository setup, branching, PRs, merging)

> Success criteria: A repository with clean commit history, a feature branch merged via PR with review, and a short README describing your workflow.

---

## Quick Reference

### Core Git commands
```bash
git init
git clone <url>
git status
git add <path> | .
git commit -m "message"
git log --oneline --graph --decorate --all
git remote -v
git push | git pull | git fetch
git checkout -b <branch>
git switch <branch>
git merge <branch>
git rebase <base>
```

### Helpful patterns
- **Conventional Commits**: `feat:`, `fix:`, `docs:`, `refactor:`, `chore:`, `test:`
- **PR checklist**: clear title/description, linked issue, tests pass, reviewer assigned
- **.gitignore**: keep repos clean; ignore build artifacts, secrets, local tooling output

```bash
# Example .gitignore snippets
node_modules/
dist/
.env
.DS_Store
```

---

## Outcomes
By the end of this course, you’ll confidently collaborate using Git and GitHub, automate routine tasks via the command line, and maintain a clean, reviewable project history suitable for professional teams and production deployments.



## Version Control

Modern software developers collaborate across the world on the same codebase without overwriting each other’s work. This course introduces version control systems, core Linux command-line skills, and a practical Git/GitHub workflow so you can manage code revisions professionally and ship with confidence.

### What you will achieve
- **Implement version control systems**
- **Navigate and configure using the command line**
- **Manage code revisions**
- **Create and use a GitHub repository**

> Key idea: Version control is your project’s time machine. It records every meaningful change, who made it, and why—enabling safe experimentation, rapid collaboration, and reliable releases.

---

## Understanding Version Control

Version control tracks changes to files over time, letting you revisit earlier versions, understand who changed what and why, and collaborate safely at scale. It’s also called source control or source code management—a practical "time machine" for your project.

### Benefits of Version Control
- **Revision history**: Revert or roll back to stable points with confidence
- **Accountability**: Each change records the author and timestamp for clear ownership
- **Traceability**: Analyze how files evolved and why decisions were made

### Collaboration and Efficiency
- **Parallel work**: Multiple developers can safely work on the same project
- **Peer review**: Changes are reviewed before merging to improve quality
- **Fewer conflicts**: Structured workflows reduce merge issues

### Role in Development Operations (DevOps)
- **Quality and speed**: Enables CI/CD, automated testing, and reliable releases
- **Workflow automation**: Integrates with tools to automate builds, checks, and deployments

### Primary Goals
- **Access full change history** of a project
- **Revert to previous versions** when needed
- **Enhance collaboration** through transparent records of modifications

### Main Features
- **Revision history**: View diffs and restore prior states
- **User identity tracking**: Know who made each change and when
- **Collaboration**: Safely coordinate work across teams and time zones
- **Branching and merging**: Isolate work for features or experiments and integrate later
- **Peer review**: Use pull requests to discuss and improve changes before merge
- **Automation**: Hook into CI/CD systems to test, lint, and deploy automatically

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

### Workflow

Using version control without a proper workflow is like building a city without traffic lights—without process, chaos ensues. A good workflow defines how work is proposed, reviewed, integrated, and released so teams avoid conflicts and reduce risk.

#### Why workflows matter

- Prevent conflicting edits by defining how and when changes are merged.
- Protect critical systems by requiring review before changes reach the main branch.
- Set clear steps for onboarding new developers and handling merge conflicts.

#### Typical practices

- Feature branches for isolated work
- Pull requests for peer review
- Required checks (tests, linters) before merging
- Clear conflict‑resolution steps and merge strategies

---

### Continuous Integration (CI)

Continuous Integration automates integrating frequent, small changes into a single mainline. By merging often—sometimes many times per day—teams reduce the likelihood and impact of merge conflicts.

Common CI activities:

- Compile/build the project on every change
- Run automated tests to keep the main branch stable
- Enforce coding standards and static analysis

---

### Continuous Delivery (CD)

Continuous Delivery builds on CI to ensure the application is always in a deployable state. After changes merge into the main codebase, a pipeline automates building, testing, and packaging for a production‑like environment.

Key points:

- Always‑deployable main branch after automated checks pass
- Packaging and release preparation are automated
- Manual approval is required before production release (provides control, slower than Continuous Deployment)

---

### Continuous Deployment

Continuous Deployment extends Continuous Delivery by automating the actual release to production. Any change that passes the pipeline’s automated tests and validations is deployed without manual intervention.

Typical flow:

- Deploy to staging for additional checks
- Promote automatically to production when validations pass
- No manual approval step (faster, demands high test quality and robust monitoring)

Relationship to Continuous Delivery:

- Can be used together: Delivery ensures production‑readiness; Deployment automates the final release
- Combined pipelines add safety via gates but can increase lead time

---

### Conclusion

With defined workflows and CI/CD practices, teams can take code from a developer’s editor to reliable, frequent releases for customers. Operating and scaling a live service involves more topics (monitoring, incident response, observability, security), which build on these foundations.

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

## Staging vs. Production  
### Development Environments  

Every development team, before releasing new features or updates, must ensure that the code going into production will not introduce bugs or issues. To achieve this, teams use multiple **development environments** such as **developer**, **QA (Quality Assurance) or UAT (User Acceptance Testing)**, and **staging** environments. The purpose is to test changes at different levels so issues are caught as early as possible. The more environments used for testing, the less risk there is of introducing bugs into production.  

---

### Staging Environment  

The **staging environment** is designed to **closely mimic the production environment** so that teams can validate features in a nearly identical setup before deployment.  

Key purposes of staging:  
- **New Features**: Developers test newly built features here, often using feature flags to toggle functionality on/off. This ensures the new functionality works without affecting existing features.  
- **Testing**: QA teams use staging to perform unit tests, integration tests, and performance tests. Since staging mirrors production, test results are more reliable. Performance testing can be run here to avoid impacting real users.  
- **Migrations**: Database and schema changes can be safely tested in staging using production-like data. If an error occurs, the migration can be rolled back without customer impact.  
- **Configuration Changes**: Teams can verify infrastructure, service dependencies, and settings in staging to detect misconfigurations before pushing them live.  

Considerations:  
- Staging may not always be a full-scale replication of production due to cost or resource constraints. For example, production may run on 10 servers while staging uses 4, maintaining the same architecture but with limited scale.  
- Staging provides a safe environment for **stakeholders and QA teams** to preview features before public release.  

---

### Production Environment  

The **production environment** is the **live system** where end users interact with the application. Everything here must be reliable, secure, and continuously available.  

Key aspects of production:  
- **Downtime**: Any downtime is costly, especially for revenue-driven businesses. A broken checkout system in an e-commerce app, for instance, means revenue loss and poor user experience.  
- **Vulnerabilities**: Security is critical. Any software patches, upgrades, or dependency changes must be carefully tested beforehand (in staging or QA) to avoid risks.  
- **Reputation**: Outages negatively impact customer trust and can cause long-term brand damage. Production must always appear stable, secure, and professional to users.  
- **Final Verification**: Only thoroughly tested and reviewed code gets deployed to production. By this stage, the risk of bugs and issues should already be minimized thanks to staging and other environments.  

---

### Flow of Development Environments  

| Environment       | Purpose                                          | Key Activities                                             |
|:------------------|:------------------------------------------------|:------------------------------------------------------------|
| Developer         | Local development                               | Writing, debugging, and initial testing                     |
| QA / UAT          | Controlled verification                         | Manual and automated testing, validating new features       |
| Staging           | Production-like testing environment             | Final pre-release tests: feature flags, migrations, configs |
| Production        | Live system accessed by users                   | Hosting stable, secure, and performant application          |

This layered approach ensures **safer deployments, fewer bugs, and maximum uptime**, supporting the core goals of DevOps workflows and CI/CD pipelines.

## About Version Control

Version control is a system that records changes to a file or set of files over time so you can recall specific versions later. It is widely used to manage software source code but can be applied to nearly any type of file.

Key reasons to use version control:  
- **Revert changes:** Easily undo mistakes by rolling back to previous versions  
- **Track history:** See who changed what and when, helping accountability and debugging  
- **Collaboration:** Multiple developers can work on the same project without overwriting each other

### Types of Version Control Systems

- **Local Version Control Systems:** Early tools managing changes locally on a single machine using databases or patch sets. (e.g., RCS)  
- **Centralized Version Control Systems (CVCS):** Use a central server to store all versions and coordinate collaboration (e.g., CVS, Subversion). Single server is a potential single point of failure.  
- **Distributed Version Control Systems (DVCS):** Every collaborator has a full copy of the repository & history locally, improving reliability and flexibility (e.g., Git, Mercurial) [source: Git Book][attached_file:1]  

---

## Benefits of a Distributed Version Control System  

A distributed version control system (DVCS) like Git offers distinct advantages:

| Benefits                   | Description                                                                                         |
|----------------------------|-------------------------------------------------------------------------------------------------|
| Reliable Backup Copies     | Every local clone is a complete backup of the repository, reducing reliance on a central server. |
| Fast Merging & Branching   | Local repositories allow rapid merges and flexible branching strategies without constant server interaction. |
| Rapid Feedback & Fewer Conflicts | Developers can experiment locally and collaborate asynchronously, reducing merge conflicts.         |
| Offline Work Capability    | Most tasks can be performed without internet access since the full repository is local.           |

These features enhance developer productivity, improve workflow flexibility, and ensure robustness against server failures.  
[source: GitLab benefits][attached_file:2]  

---

## What is Cloning?

Cloning a repository means making a full copy of an existing remote Git repository on your local machine. The clone includes all the files, branches, tags, and commit history, allowing you to work independently on your own copy.

Basic clone command:

```bash
git clone https://github.com/user/repository.git
```

After cloning, developers can create branches, make commits, and push changes back to the remote repository to share with others. Cloning is the first step in the typical Git workflow.  
[source: GitHub Docs][web:9]  

---

## Summary

Version control provides a "time machine" for projects, enabling safe experimentation, history tracking, and team collaboration. Distributed version control systems like Git have become the standard for modern software development due to their speed, flexibility, and reliability. Cloning repositories is how developers start working with existing codebases locally before contributing changes.

## Agile Methodologies

For a comprehensive beginner’s guide to Agile methodologies, including detailed comparisons of popular frameworks like Scrum, Kanban, Extreme Programming (XP), Lean, and more, visit the Planview resource:

[Agile Methodologies: A Beginner's Guide](https://www.planview.com/resources/guide/agile-methodologies-a-beginners-guide/)

---

## Installing Git on macOS and Windows

Detailed instructions for installing Git on different operating systems including macOS (via Xcode Command Line Tools or binary installer) and Windows (via official Git for Windows installer or Chocolatey) are available here:

[Installing Git - Git SCM Book](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

---

## Bash Reference and Redirections

Official GNU Bash documentation covering general usage and detailed reference on input/output redirections:

- [Bash Reference Manual - GNU](https://www.gnu.org/software/bash/manual/html_node/index.html#SEC_Contents)  
- [Bash Redirections - GNU Manual](https://www.gnu.org/software/bash/manual/html_node/Redirections.html#Redirections)  

---

## Cheatsheets and Manuals

Handy reference guides and manuals for day-to-day command line tools:

- [Bash Cheatsheet - devhints.io](https://devhints.io/bash)  
- [Grep Cheatsheet - devhints.io](https://devhints.io/grep)  
- [Grep Manual - Linux man pages](https://man7.org/linux/man-pages/man1/grep.1.html)  
- [Unix Commands Cheatsheet](https://cheatography.com/jluis/cheat-sheets/bash-and-unix-commands/)  
- [Vim Cheatsheet](https://vim.rtorr.com/)  

---

## History

- [History and Timeline of Unix](https://unix.org/what_is_unix/history_timeline.html)  
- [History of Vim (Wikipedia)](https://en.wikipedia.org/wiki/Vim_(text_editor))  

---

## Pathnames in Unix

Understanding the difference between relative and absolute paths and how to work with both:

[Absolute vs Relative Pathnames - GeeksforGeeks](https://www.geeksforgeeks.org/absolute-relative-pathnames-unix/)

## Deleting Branches in Git

- Note: You cannot delete the branch you are currently on. Switch to a different branch before deleting:

### Summary Table

| Operation               | Command                                  | Notes                                       |
|------------------------|-----------------------------------------|---------------------------------------------|
| Delete local branch     | `git branch -d <branch_name>`            | Safely delete if merged                      |
| Force delete local      | `git branch -D <branch_name>`             | Force delete even if unmerged                |
| Delete remote branch    | `git push origin --delete <branch_name>` | Deletes branch on remote repository          |

### Additional Tips

- To see all your local branches:
```git
git branch
```

- To see all branches (local + remote):
```git
git branch -r
```

## Using git blame to Track Changes in a File

You can use the `git blame` command to track changes in a specific file by following these steps:

### Steps to Use git blame

1. **Open Terminal:**  
   Navigate to your project directory using the command line.

2. **Run the Command:**  
   Type the command:  

```
git blame 
```

Replace `<filename>` with the name of the file you want to inspect (e.g., `feature.js`).

3. **Understand the Output:**  
The output displays each line of the file along with:  
- **Commit ID:** Reference ID for the commit where the change was made.  
- **Author:** Name of the person who made the change.  
- **Date and Time:** When the change was committed.  
- **Line Number:** Specific line in the file where the change occurred.  
- **Content:** Actual code or text that was added or modified.

4. **Narrow Down the Output:**  
To focus on specific lines, use:  

```git
git blame -L <start-line>,<end-line> <filename>
```

This shows changes only between the specified line numbers.

5. **Further Investigation:**  
To see detailed changes for a specific commit, copy the commit ID from the `git blame` output and use:  

```git
git log -p 
```

### Benefits of Using git blame

By using `git blame`, you can effectively track:  
- **Who made changes** to each line  
- **When changes were made**  
- **The context and content** of the changes  

This enhances your understanding of the project's history and aids in debugging or code review.

---

### Example Output

```example
6f5b4d3d (Alice 2024-12-10 10:32:14 -0800  1) def fetch_data(): 74e2c4e9 (Bob   2024-12-11 14:01:02 -0800  2) return api.get_data()
```


Each line shows the commit hash, author, timestamp, line number, and code line.

---

### Additional Options

- `--date=[relative|iso|short]`: Format date output.  
- `-C` or `-M`: Detect moved or copied lines from other files (useful during refactoring).

---

This command is a powerful tool for tracing the origin of code lines and understanding the evolution of a codebase.

## GitHub: Pricing

GitHub is free to use, but it also offers different pricing models to suit the needs of different-sized teams and organizations. Check out the link below:

[GitHub Pricing](https://github.com/pricing)

---

## Git: An Origin Story

Read about the history and origin of Git in this Linux Journal article:

[Git: An Origin Story](https://www.linuxjournal.com/content/git-origin-story)

---

## Git Cheatsheet

Download a comprehensive Git cheat sheet designed for education purposes:

[Git Cheat Sheet - GitHub Education PDF](https://education.github.com/git-cheat-sheet-education.pdf)

---

## Git Patterns and Anti-Patterns for Successful Developers

Watch this insightful talk covering best practices and common anti-patterns when using Git:

[Git Patterns and Anti-Patterns - YouTube](https://youtu.be/t_4lLR6F_yk)

---

## Tech Talk: Linus Torvalds on Git  

Listen to Linus Torvalds explain Git and its development in this tech talk video:

[Linus Torvalds on Git - YouTube](https://www.youtube.com/watch?v=4XpnKHJAok8)

---

## Vim Cheatsheet

A useful Vim cheat sheet for efficient text editing and navigation in Vim:

[Vim Cheat Sheet - devhints.io](https://devhints.io/vim)






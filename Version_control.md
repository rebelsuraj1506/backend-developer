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
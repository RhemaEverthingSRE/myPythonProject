# My First GitHub Project
I'll combine everything into one complete `README.md` that reflects your current **SRE developer workstation setup** and project direction. Copy the entire content below and replace your existing `README.md`.

# myPythonProject

# SRE Engineering Development Repository

This repository is my SRE (Site Reliability Engineering) engineering workspace for building automation tools, operational scripts, reliability practices, and cloud engineering capabilities.

The goal of this repository is to document my SRE learning journey through practical implementations covering:

* Python automation
* Infrastructure tooling
* Monitoring and observability
* Cloud operations
* CI/CD automation
* Reliability engineering practices
* Operational excellence

---

# Development Environment

## Workstation

* Operating System: macOS Sonoma
* Shell: Zsh
* Editor: Visual Studio Code
* Programming Language: Python 3
* Version Control: Git
* Repository Hosting: GitHub

---

# Git Configuration

Git was configured for local development and GitHub integration.

Configure Git identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Verify Git configuration:

```bash
git config --global --list
```

---

# SSH Configuration (macOS SRE Workstation Setup)

SSH authentication was configured to securely connect the SRE workstation with GitHub.

SSH provides secure authentication for Git operations without storing passwords or personal access tokens.

---

## Generate ED25519 SSH Key

Generate a secure SSH key:

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

Default SSH key location:

```text
~/.ssh/id_ed25519
```

SSH files:

```text
~/.ssh/
├── id_ed25519        # Private key (DO NOT SHARE)
└── id_ed25519.pub    # Public key
```

---

## Start SSH Agent

Start the SSH authentication agent:

```bash
eval "$(ssh-agent -s)"
```

Example:

```text
Agent pid 12345
```

---

## Add SSH Key to macOS Keychain

Add the SSH key:

```bash
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

Verify keys:

```bash
ssh-add -l
```

---

## Copy SSH Public Key

Copy the public key:

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

Display the key:

```bash
cat ~/.ssh/id_ed25519.pub
```

The public key format:

```text
ssh-ed25519 AAAAC3... your-email@example.com
```

---

## Add SSH Key to GitHub

Steps:

1. Open GitHub SSH key settings.
2. Select **New SSH key**.
3. Add a workstation label.

Example:

```text
Mac Sonoma SRE Workstation
```

4. Paste the public key.
5. Save the key.

---

## Test SSH Authentication

Verify GitHub SSH connectivity:

```bash
ssh -T git@github.com
```

Expected response:

```text
Hi <github-user>! You've successfully authenticated, but GitHub does not provide shell access.
```

Successful authentication confirms:

* SSH key is valid
* GitHub recognizes the workstation
* Git operations can securely use SSH

---

# SSH Configuration File

Configure SSH defaults:

```bash
nano ~/.ssh/config
```

Example configuration:

```text
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519
    AddKeysToAgent yes
    UseKeychain yes
```

Secure permissions:

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/config
chmod 600 ~/.ssh/id_ed25519
```

---

# Repository Setup

Create repository:

```bash
git init
```

Add files:

```bash
git add .
```

Create first commit:

```bash
git commit -m "Initial commit"
```

Connect GitHub repository:

```bash
git remote add origin git@github.com:RhemaEverthingSRE/myPythonProject.git
```

Push repository:

```bash
git branch -M main
git push -u origin main
```

---

# Git Workflow

Daily workflow:

Check changes:

```bash
git status
```

Stage changes:

```bash
git add .
```

Commit changes:

```bash
git commit -m "Describe changes"
```

Push changes:

```bash
git push
```

Pull latest changes:

```bash
git pull
```

---

# Python Environment Setup

A Python virtual environment is used to isolate project dependencies.

Create virtual environment:

```bash
python3 -m venv .venv
```

Activate environment:

```bash
source .venv/bin/activate
```

Verify Python:

```bash
which python
```

Expected:

```text
/Users/<username>/myPythonProject/.venv/bin/python
```

---

# Python Project Structure

Current project structure:

```text
myPythonProject/
│
├── .git/
├── .gitignore
├── .venv/
├── README.md
└── main.py
```

---

# Git Ignore Configuration

The following files are excluded from version control:

```text
# Python cache
__pycache__/
*.py[cod]

# Virtual environments
.venv/
venv/

# Environment files
.env

# IDE files
.vscode/

# macOS files
.DS_Store

# Testing files
.pytest_cache/

# Build files
build/
dist/
*.egg-info/
```

---

# First Python Automation Script

Example:

```python
def main():
    print("Hello GitHub from Python!")


if __name__ == "__main__":
    main()
```

Run:

```bash
python main.py
```

Output:

```text
Hello GitHub from Python!
```

---

# SRE Engineering Roadmap

This repository will evolve into an SRE engineering portfolio covering:

## Automation

* Python operational scripts
* System automation
* API automation
* Task automation

## Monitoring and Observability

* Metrics collection
* Logging
* Alerting
* Dashboards
* Service health checks

## Infrastructure as Code

* Terraform
* Cloud provisioning
* Configuration management

## Cloud Engineering

* AWS
* Azure
* Google Cloud
* Cloud reliability practices

## Containers

* Docker
* Kubernetes
* Container monitoring

## CI/CD

* GitHub Actions
* Automated testing
* Deployment workflows

## Reliability Engineering

* Incident response
* Root cause analysis
* Service Level Objectives (SLOs)
* Service Level Indicators (SLIs)
* Error budgets
* Operational excellence

---

# SRE Security Practices

Implemented practices:

* ED25519 SSH authentication
* Secure SSH key storage
* Private key protection
* Git-based change tracking
* Environment isolation using Python virtual environments

Security rules:

* Never commit private keys.
* Never commit secrets.
* Use environment variables for sensitive values.
* Rotate credentials regularly.

---

# Current Status

Completed:

✅ Git installed and configured
✅ GitHub repository created
✅ SSH authentication configured
✅ Git workflow established
✅ Python virtual environment created
✅ Initial Python application created
✅ SRE documentation started

---

# Next Steps

Planned improvements:

* Add Python dependency management
* Add automated tests
* Add logging framework
* Build SRE health-check tools
* Add monitoring integrations
* Add Docker support
* Add GitHub Actions CI/CD pipeline
* Add infrastructure automation examples

---

# Author

SRE Engineering Journey

GitHub:

RhemaEverthingSRE

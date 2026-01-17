## Learn Git basics for Beginners

If you're new to coding, you've probably heard about Git and GitHub. They're essential tools for developers, but they can seem confusing at first. This guide will walk you through everything step by step.

### What is Git

Git is a version control system. Think of Git as a history recorder for your project.

It helps you:

- Track changes in your files
- Go back to previous versions
- Work with others without overwriting their code

### What is GitHub

GitHub is an online platform where you store Git repositories.

It allows you to:

- Back up your code online
- Collaborate with other developers
- Share your project publicly or privately

## Step 1: Installing Git Bash

### For Windows Users:

- Visit [Git Bash](https://git-scm.com)

- Download the Windows installer
- Run the installer with these recommended settings:
  - Select "Use Git from Git Bash only "
  - Choose "Use the OpenSSL library"
  - Select "Checkout Windows-style, commit Unix-style line endings"
  - Choose "Use MinTTY"
  - Leave other options as default

### For Mac Users:

```bash
# Option 1: using Homebrew
brew install git

# Option 2: Download from <git-scm.com>
```

### For Linux Users:

```bash

# Ubuntu/Debian
sudo apt-get install git

#Fedora
sudo dnf5 install git
```

## Step 2: Connecting Git to Your GitHub Account

### 1. Configure Your Identity

```bash
git config --global user.name "your name"
git config --global user.email "your email"
```

### 2. Generate an SSH Key

```bash
# Generate a new SSH key
ssh-keygen -t ed25519 -C "your email"

# Press Enter to accept default location

# Copy the key to your clipboard

# For Windows
C:\Users\YOUR_USERNAME\.ssh\id_ed25519.pub

# For Mac:
~/.ssh/id_ed25519.pub

# For Linux:
~/.ssh/id_ed25519.pub
```

### Add SSH Key to GitHub

- Go to your GitHub account
- Go to settings then click SSH and GPG keys
- Click "New SSH key"
- Paste your key and give it a descriptive name
- Click "Add SSH key"

### Test Your Connection

```bash
ssh -T git@github.com
```

You should see: "Hi username! You've successfully authenticated...."

## Step 3: Git Commands

### Initialize a new repository

```bash
# Create project folder
mkdir my-first-project

# Navigate to your project folder
cd my-first-project

# Initialize git tracking
git init

# list all files and folders in the project directory
ls -la  # you will find .git folder
```

Git creates a hidden `.git` folder to store history.

#### Open Project in VS Code

- Open VS Code
- File -> Open Folder
- Select my-first-project
- Click "Open"
- Click "New File" icon
- Name it "hello.py"
- Add this content

```python
# print Hello World in Python
print("Hello World!")
```

### Check your repository status

```bash
git status
```

Output shows untracked/modified files

### Stage Files

```bash
# Stage specific file
git add hello.py

# Stage multiple files
git add hello.py README.md

# Stage all changes
git add .

# Check what's staged
git status
```

### Commit Changes

```bash
# commit with descriptive message
git commit -m "Add initial Python script and documentation"
```

## Step 4: Connect to GitHub and Push

### Create Repository on GitHub

- Go to your GitHub account
- Click + -> New repository
- Name: my-first-project
- Description: "Learning Git basics"
- Click "Create repository"

### Connect Local to Remote

```bash
# Copy the SSH URL from GitHub
# Example
git remote add origin git@github.com:yourusername/my-first-project.git

# verify connection
git remote -v
```

### Push to GitHub

```bash
# First push (sets upstream)
git push -u origin main

# Subsequent pushes
git push
```

### What happens when you push

- Your local commits are uploaded to GitHub
- Others can now see and access your code
- Your work is backed up in the cloud

## Step 5: Pulling Code from GitHub

### When to pull:

- When starting work on a project
- When teammates have made changes
- Before making your own changes

```bash
# basic pull
# Go to the project directory
git pull

# pull from specific branch
git pull origin feature-branch
```

Everyone makes mistakes with git at first. That's normal! The key is to start with simple workflows and gradually learn more advanced features.

Git is a powerful tool that becomes intuitive with practice.

# Git Practical Tutorial Notes

## Introduction to Git

Git is a distributed version control system used to track changes in files and source code. It helps developers maintain different versions of a project, collaborate with team members, and restore previous versions when needed.

### Why Use Git?

* Tracks every change made to files.
* Allows reverting to previous versions.
* Supports collaboration among developers.
* Maintains project history.
* Prevents accidental loss of code.

---

# 1. Initializing a Git Repository

Before Git can track a project, the project folder must be converted into a Git repository.

### Command

```bash
git init
```

### What Happens?

* A hidden `.git` folder is created.
* Git starts tracking the project.
* The folder becomes a Git repository.

### Example

```bash
mkdir MyProject
cd MyProject
git init
```

### Output

```bash
Initialized empty Git repository
```

---

# 2. Checking Repository Status

Git provides information about the current state of files through the status command.

### Command

```bash
git status
```

### Purpose

Shows:

* Untracked files
* Modified files
* Staged files
* Branch information

### Example Output

```bash
Untracked files:
  index.html
```

### Meaning

Git has found a new file but is not tracking it yet.

---

# Understanding Git Workflow

Git works in three main stages:

## Working Directory

Where files are created and modified.

## Staging Area

Temporary area where selected changes are prepared before committing.

## Repository

Permanent storage of committed snapshots.

### Workflow

```text
Working Directory
       ↓
     git add
       ↓
   Staging Area
       ↓
   git commit
       ↓
   Repository
```

---

# 3. Staging Files

To tell Git which changes should be included in the next commit, files must be staged.

## Stage a Single File

```bash
git add index.html
```

## Stage All Files

```bash
git add .
```

### Purpose

Moves files from:

```text
Working Directory → Staging Area
```

### Verify

```bash
git status
```

Output:

```bash
Changes to be committed:
  new file: index.html
```

This means the file is ready to be committed.

---

# 4. Committing Changes

A commit saves a permanent snapshot of the project.

### Command

```bash
git commit -m "Initial Commit"
```

### Explanation

* `git commit` → Creates a snapshot.
* `-m` → Message option.
* `"Initial Commit"` → Description of changes.

### Example

```bash
git commit -m "Added homepage"
```

### Best Practices

Use meaningful commit messages:

✅ Good

```bash
git commit -m "Added login page"
```

❌ Bad

```bash
git commit -m "changes"
```

---

# 5. Modifying Files

After committing, files may be edited again.

Example:

```html
<h1>Welcome to Git Tutorial</h1>
```

Git detects these changes automatically.

Check status:

```bash
git status
```

Output:

```bash
modified: index.html
```

Meaning:

The file was changed after the last commit.

---

# 6. Discarding Changes

Sometimes changes are made accidentally and need to be removed.

### Command

```bash
git restore index.html
```

### Purpose

Restores the file to its last committed version.

### Before Restore

```html
<h1>Hello World</h1>
```

### After Restore

Git removes uncommitted changes and returns the file to the previous saved state.

### Important Note

Restored changes cannot be recovered unless committed earlier.

---

# Common Git Commands Covered

| Command | Purpose |
|----------|----------|
| git init | Initialize repository |
| git status | Check repository status |
| git add filename | Stage specific file |
| git add . | Stage all files |
| git commit -m "message" | Save snapshot |
| git restore filename | Discard changes |

---

# Practical Example

## Step 1

Create file:

```html
index.html
```

## Step 2

Initialize Git:

```bash
git init
```

## Step 3

Check status:

```bash
git status
```

## Step 4

Stage file:

```bash
git add index.html
```

## Step 5

Commit file:

```bash
git commit -m "Added index page"
```

## Step 6

Modify file content.

## Step 7

Check status:

```bash
git status
```

## Step 8

Discard changes:

```bash
git restore index.html
```

---

# Key Interview Questions

### What is Git?

Git is a distributed version control system used to track and manage changes in source code.

### What is a Git Repository?

A project folder tracked by Git.

### What does git init do?

Creates a new Git repository by generating a hidden `.git` folder.

### What is the Staging Area?

A temporary area where changes are prepared before committing.

### Difference Between git add and git commit?

* `git add` stages changes.
* `git commit` permanently saves changes.

### What does git status show?

Current state of tracked and untracked files.

### What does git restore do?

Reverts uncommitted changes in a file.

---

# Assignment 1: Initialize Git

### Task

1. Create a folder called `GitPractice`.
2. Add a file named `index.html`.
3. Initialize Git.
4. Verify repository status.

### Expected Commands

```bash
git init
git status
```

---

# Assignment 2: Staging Practice

### Task

1. Create three files:

   * index.html
   * style.css
   * script.js

2. Stage only `index.html`.

3. Check status.

### Expected Commands

```bash
git add index.html
git status
```

---

# Assignment 3: Commit Practice

### Task

1. Stage all files.
2. Create a commit.

### Expected Commands

```bash
git add .
git commit -m "Added website files"
```

---

# Assignment 4: Restore Practice

### Task

1. Modify `index.html`.
2. Check status.
3. Restore the file.

### Expected Commands

```bash
git status
git restore index.html
```

---

# Assignment 5: Complete Git Workflow

Perform the complete workflow:

```bash
git init
git status
git add .
git commit -m "First Commit"
git status
```

Take screenshots of each command output and maintain them in a Git Learning Report.

---

# Summary

In this tutorial, we learned:

* What Git is and why it is used.
* How to initialize a repository using `git init`.
* How to check repository status using `git status`.
* How to stage files using `git add`.
* How to create commits using `git commit`.
* How to discard unwanted changes using `git restore`.
* The complete Git workflow from project creation to version tracking.

These commands form the foundation of Git and are essential for every developer before moving to advanced topics such as branching, merging, and GitHub integration.
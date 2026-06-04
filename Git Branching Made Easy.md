# Git Branching - Complete Notes

## Introduction

Git branching is one of the most powerful features of Git. It allows developers to work on different features independently without affecting the main codebase.

For example, if multiple developers are working on:

- Login Feature
- Footer Section
- FAQ Section
- Payment Integration

Each feature can be developed in a separate branch.

---

# What is a Branch?

A branch is an independent line of development in Git.

```text
main
├── login-feature
├── footer-feature
├── faq-feature
└── payment-feature
```

Changes made in one branch do not affect other branches until they are merged.

## Benefits of Branching

- Isolated development
- Safe experimentation
- Better collaboration
- Easier testing
- Prevents breaking production code

---

# Viewing Current Branch

```bash
git branch
```

Example:

```bash
* main
```

The `*` indicates the currently active branch.

---

# Renaming a Branch

## Syntax

```bash
git branch -m new-branch-name
```

## Example

```bash
git branch -m master
```

This renames the current branch to `master`.

### Why Rename Branches?

For better naming conventions and clarity.

Example:

```text
feature1
```

can be renamed to

```text
user-authentication
```

---

# Creating a New Branch

## Syntax

```bash
git branch branch-name
```

## Example

```bash
git branch footer
```

This creates a new branch called `footer`.

```text
main
└── footer
```

However, Git still keeps you on the current branch.

---

# Viewing All Branches

```bash
git branch
```

Example:

```bash
footer
faq
* main
```

Meaning:

- footer branch exists
- faq branch exists
- currently on main branch

---

# Switching Branches

## Syntax

```bash
git checkout branch-name
```

## Example

```bash
git checkout footer
```

Output:

```bash
Switched to branch 'footer'
```

Now all changes will be made inside the `footer` branch.

---

# Verify Current Branch

```bash
git branch
```

Output:

```bash
* footer
main
faq
```

Current active branch:

```text
footer
```

---

# Create and Switch to a Branch

Instead of:

```bash
git branch footer
git checkout footer
```

Use:

```bash
git checkout -b footer
```

This command:

1. Creates the branch
2. Switches to it immediately

---

# Modern Alternative

Git recommends using:

```bash
git switch -c footer
```

This performs the same operation.

---

# Real World Example

## Step 1: Create Branch

```bash
git checkout -b footer
```

## Step 2: Add Footer Code

```html
<footer>
    Copyright 2026
</footer>
```

## Step 3: Commit Changes

```bash
git add .
git commit -m "Added footer"
```

## Step 4: Switch Back

```bash
git checkout main
```

You will notice the footer code is not present in `main`.

Reason:

Changes exist only in the `footer` branch.

---

# Deleting a Branch

## Syntax

```bash
git branch -d branch-name
```

## Example

```bash
git branch -d footer
```

Output:

```bash
Deleted branch footer
```

---

# Force Delete a Branch

If Git shows:

```bash
The branch is not fully merged.
```

Use:

```bash
git branch -D footer
```

### Difference

| Command | Meaning |
|----------|----------|
| `git branch -d` | Safe delete |
| `git branch -D` | Force delete |

---

# Understanding Git Log

Git stores every commit permanently.

View complete history:

```bash
git log
```

Example:

```bash
commit 8a2bc1234f...
Author: Raj
Date: ...

Added footer

commit 5f4de123...
Author: Raj
Date: ...

Created homepage

commit 2ab34cd...
Author: Raj
Date: ...

Initial commit
```

---

# Commit Structure

Every commit contains:

- Commit ID
- Author
- Date
- Commit Message

Example:

```text
commit 8a2bc1234f
Author: Raj
Date: ...

Added footer
```

---

# Commit Hash

Every commit receives a unique identifier.

Example:

```bash
8a2bc1234f
```

or

```bash
8a2bc1234fabcd56789ef
```

Git uses SHA hashing to generate these IDs.

No two commits have the same hash.

---

# Short Commit History

Instead of:

```bash
git log
```

Use:

```bash
git log --oneline
```

Example:

```bash
8a2bc12 Added footer
5f4de12 Homepage created
2ab34cd Initial commit
```

This provides a compact view of commit history.

---

# Checkout a Specific Commit

Suppose:

```bash
git log --oneline
```

returns:

```bash
a111111 Latest
b222222 Footer Added
c333333 Homepage Created
```

Move to commit:

```bash
git checkout b222222
```

Git will show the project exactly as it existed at that point in time.

---

# Detached HEAD State

When checking out a commit directly:

```bash
git checkout b222222
```

Git displays:

```bash
You are in 'detached HEAD' state
```

---

# What is HEAD?

Normally:

```text
HEAD
 ↓
main
 ↓
Latest Commit
```

Detached HEAD:

```text
HEAD
 ↓
Specific Commit
```

HEAD is no longer attached to a branch.

---

# Risks of Detached HEAD

If you make commits in detached HEAD mode:

```bash
git add .
git commit -m "Testing"
```

The commit exists but is not connected to any branch.

You may lose track of it later.

---

# Return to Main Branch

```bash
git checkout main
```

or

```bash
git switch main
```

This returns Git to normal branch mode.

---

# Complete Branching Workflow

```bash
git init

git add .
git commit -m "Initial commit"

git checkout -b footer

# Make changes

git add .
git commit -m "Footer added"

git checkout main

git branch

git log --oneline

git checkout footer

git branch -d footer
```

---

# Command Summary

| Command | Purpose |
|----------|----------|
| `git branch` | Show branches |
| `git branch name` | Create branch |
| `git checkout name` | Switch branch |
| `git checkout -b name` | Create and switch |
| `git branch -m name` | Rename branch |
| `git branch -d name` | Delete branch |
| `git branch -D name` | Force delete branch |
| `git log` | Full commit history |
| `git log --oneline` | Compact commit history |
| `git checkout commit-id` | Move to specific commit |
| `git checkout main` | Return to main branch |

---

# Interview Questions

## 1. Why do we use branches in Git?

Branches allow developers to work independently on features, bug fixes, and experiments without affecting the main codebase.

---

## 2. Difference between `git branch` and `git checkout`?

| Command | Purpose |
|----------|----------|
| `git branch` | Create/List branches |
| `git checkout` | Switch branches |

---

## 3. What does `git checkout -b feature` do?

Creates a new branch and immediately switches to it.

---

## 4. What is a Detached HEAD?

A state where HEAD points directly to a commit instead of a branch.

---

## 5. How can you view commit history?

```bash
git log
```

or

```bash
git log --oneline
```

---

## 6. Difference between `git branch -d` and `git branch -D`?

- `git branch -d` → Deletes only merged branches.
- `git branch -D` → Force deletes even unmerged branches.

---

# Conclusion

Git branching is a fundamental concept used in professional software development. It enables:

- Feature development
- Bug fixing
- Team collaboration
- Safe experimentation
- Efficient project management

Mastering Git branches is essential for working in real-world development teams and preparing for software engineering interviews.


# Git Branching - Top 15 Assignment Questions

## Assignment Objectives

- Understand Git branches
- Practice branch creation and switching
- Learn commit history navigation
- Understand Detached HEAD state
- Practice branch deletion

---

## Question 1

What is a Git branch and why is it used in software development?

---

## Question 2

Initialize a new Git repository and create the first commit with the message:

```bash
Initial Commit
```

---

## Question 3

Display all branches in your repository and identify the active branch.

---

## Question 4

Rename the current branch to:

```text
production
```

Verify that the rename was successful.

---

## Question 5

Create a new branch named:

```text
footer-feature
```

---

## Question 6

Switch to the `footer-feature` branch and verify that it is the active branch.

---

## Question 7

Create and switch to a new branch named:

```text
login-feature
```

using a single Git command.

---

## Question 8

In the `footer-feature` branch:

1. Create a file named `footer.html`
2. Add sample HTML content
3. Commit the changes

---

## Question 9

Display the complete commit history of the repository.

---

## Question 10

Display the commit history in one-line format and identify the latest commit hash.

---

## Question 11

Checkout a previous commit using its commit hash and observe the repository state.

---

## Question 12

What is a Detached HEAD state?

Explain:

- When it occurs
- Why it occurs
- Risks associated with it

---

## Question 13

Return from Detached HEAD state to the `production` branch and verify the current branch.

---

## Question 14

Delete a branch safely using Git and explain the command used.

---

## Question 15

Explain the difference between:

```bash
git branch -d feature
```

and

```bash
git branch -D feature
```

Provide an example scenario for each command.

---

# Bonus Challenge

Create the following branch structure:

```text
production
├── login-feature
├── footer-feature
├── faq-feature
└── payment-feature
```

### Tasks

1. Create all branches.
2. Add one file in each branch.
3. Make one commit in each branch.
4. Display all branches.
5. Display commit history.
6. Checkout an old commit.
7. Return to `production`.
8. Delete one branch safely.
9. Delete one branch forcefully.
10. Document all commands used.

---




# Git GUI Workflow: Staging, Committing, and Discarding Changes

## Introduction

Git is a distributed version control system used to track changes in source code during software development. While many developers use Git through the Command Line Interface (CLI), modern tools such as Visual Studio Code, GitHub Desktop, and SourceTree provide Graphical User Interfaces (GUI) that simplify Git operations.

This guide explains how to manage Git workflows using a GUI, focusing on:

* Tracking Changes
* Staging Files
* Committing Changes
* Managing Multiple Files
* Discarding Changes

---

# 1. Tracking Changes

Git automatically detects modifications made to files in a repository.

### Types of Changes

#### Added Code

Displayed in **green**.

Example:

```java
System.out.println("Welcome to Git");
```

#### Removed Code

Displayed in **red**.

Example:

```java
System.out.println("Old Code");
```

### Benefits

* Easily identify modifications.
* Review code before committing.
* Reduce accidental errors.

---

# 2. Staging Changes

The staging area acts as a temporary holding space before creating a commit.

### Process

1. Modify files.
2. Review changes.
3. Select files to stage.
4. Move selected files to the staging area.

### Why Staging Matters

* Allows selective commits.
* Keeps commits organized.
* Improves project history readability.

### Example

You modified:

* Login.java
* UserService.java
* README.md

You may choose to stage only Login.java and UserService.java while leaving README.md for a later commit.

---

# 3. Committing Changes

A commit permanently records staged changes into Git history.

### Steps

1. Stage files.
2. Enter a meaningful commit message.
3. Click Commit.

### Good Commit Messages

✔ Add JWT authentication middleware

✔ Fix login validation bug

✔ Update API documentation

### Poor Commit Messages

✘ Changes

✘ Updated files

✘ Fix

### Best Practices

* Keep commits small.
* Use descriptive messages.
* Commit related changes together.

---

# 4. Managing Multiple Files

Git GUI tools provide bulk operations.

### Stage All

Moves every modified file into the staging area.

Useful when:

* A feature is complete.
* All changes belong together.

### Unstage All

Removes all staged files back to the working directory.

Useful when:

* You accidentally staged files.
* You want to reorganize commits.

### Example Workflow

Modified:

* UserController.java
* AuthService.java
* README.md

Use:

* Stage All → Stage everything
* Unstage All → Remove everything from staging

---

# 5. Discarding Changes

Discarding removes modifications from the working directory.

### Warning

This action is irreversible.

Once discarded:

* Local changes are deleted.
* Unsaved work cannot be recovered through Git.

### When to Use

* Experimental code is no longer needed.
* Incorrect changes were made.
* You want to revert to the last committed version.

### Example

Before Discard:

```java
String role = "Admin";
```

Changed to:

```java
String role = "Test";
```

After Discard:

```java
String role = "Admin";
```

The file returns to its last committed state.

---

# Real-World Workflow Example

Step 1: Modify code

```
Login.java
AuthService.java
```

Step 2: Review changes

* Green = Added
* Red = Removed

Step 3: Stage files

```
Login.java
AuthService.java
```

Step 4: Commit

Message:

```
Implement JWT Authentication
```

Step 5: Push to remote repository (future topic)

---

# Key Takeaways

* Git automatically tracks file changes.
* The staging area allows selective commits.
* Commits create permanent project history.
* Stage All and Unstage All simplify large updates.
* Discarding changes permanently removes modifications.
* Always review changes before committing or discarding.

---

# High-Level Assignment Questions

## Section A – Conceptual

### 1.

Explain the purpose of the Git staging area and how it differs from the working directory.

### 2.

Why is staging considered an important step before committing changes?

### 3.

Describe the complete lifecycle of a file from modification to commit in Git.

### 4.

What risks are associated with using the Discard Changes feature?

### 5.

Compare Git GUI workflows with Git CLI workflows. Discuss advantages and limitations.

---

## Section B – Practical Understanding

### 6.

You modified five files but only want to commit two of them. Explain how a Git GUI enables this process.

### 7.

A developer accidentally stages all files. How can they correct this using GUI tools?

### 8.

Explain what happens internally when a commit is created.

### 9.

How does Git identify additions and deletions in a file?

### 10.

Why should commit messages be meaningful? Explain with examples.

---

## Section C – Industry-Level Analysis

### 11.

A team member commits unrelated changes in a single commit. What problems can this create during maintenance and debugging?

### 12.

Describe a scenario where using "Stage All" could be harmful in a production project.

### 13.

How would improper use of the "Discard Changes" option affect a software development team?

### 14.

Explain how well-structured commits improve collaboration in large-scale software projects.

### 15.

Design a Git GUI workflow for a team developing an e-commerce application where multiple developers are modifying the same project simultaneously.

---

# Conclusion

Understanding Git GUI workflows is essential for modern software development. Mastering staging, committing, and discarding changes helps developers maintain clean project histories, improve collaboration, and reduce mistakes. These foundational skills prepare developers for advanced Git topics such as remote repositories, GitHub integration, branching strategies, merge conflicts, and collaborative development.

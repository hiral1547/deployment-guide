# Upload an Existing VS Code Project to an Existing GitHub Repository

This guide explains how to upload a local VS Code project to a GitHub repository that **already contains files (such as a README.md)**.

## Prerequisites

* Git installed on your computer.
* A GitHub repository already created.
* The repository URL copied from GitHub.
* Your project opened in VS Code.

---

## Step 1: Open the Project

1. Open **Visual Studio Code**.
2. Open your project folder.
3. Open the terminal:

   * **Terminal → New Terminal**, or
   * Press **Ctrl + `**

---

## Step 2: Initialize Git (if needed)

Check whether Git is already initialized:

```bash
git status
```

If you receive the message **"not a git repository"**, initialize Git:

```bash
git init
```

---

## Step 3: Add Project Files

```bash
git add .
```

---

## Step 4: Commit the Project

```bash
git commit -m "Initial project upload"
```

---

## Step 5: Connect the Local Project to GitHub

Replace `<repository-url>` with your GitHub repository URL.

Example:

```text
https://github.com/username/repository-name.git
```

Add the remote:

```bash
git remote add origin <repository-url>
```

If the remote already exists:

```bash
git remote set-url origin <repository-url>
```

---

## Step 6: Set the Branch Name

```bash
git branch -M main
```

---

## Step 7: Pull the Existing GitHub Repository

Since the repository already contains a **README.md** (or other files), pull those changes first:

```bash
git pull origin main --allow-unrelated-histories
```

If Git asks how to reconcile divergent branches, use:

```bash
git pull origin main --allow-unrelated-histories --no-rebase
```

---

## Step 8: Resolve Merge Conflicts (If Any)

If Git reports a merge conflict (commonly in `README.md`):

1. Open the conflicted file in VS Code.
2. Look for conflict markers:

```text
<<<<<<< HEAD
Your local content
=======
GitHub content
>>>>>>> main
```

3. Edit the file to keep the required content.
4. Remove the conflict markers.
5. Save the file.

Stage the resolved files:

```bash
git add .
```

Commit the merge:

```bash
git commit -m "Merge local project with GitHub repository"
```

---

## Step 9: Push the Project to GitHub

```bash
git push -u origin main
```

Your project is now uploaded to GitHub.

---

# Future Updates

Whenever you make changes to your project:

```bash
git add .
git commit -m "Describe your changes"
git push
```

---

# Complete Command Sequence

```bash
git init
git add .
git commit -m "Initial project upload"

git branch -M main

git remote add origin <repository-url>

git pull origin main --allow-unrelated-histories --no-rebase

# Resolve merge conflicts if prompted

git add .
git commit -m "Merge local project with GitHub repository"

git push -u origin main
```

---

# Common Errors

### Error: `remote origin already exists`

```bash
git remote set-url origin <repository-url>
```

or

```bash
git remote remove origin
git remote add origin <repository-url>
```

---

### Error: `nothing to commit`

This means there are no new changes to commit.

---

### Error: `failed to push some refs`

Run:

```bash
git pull origin main --rebase
git push
```

---

## Verification

1. Open your GitHub repository.
2. Refresh the page.
3. Confirm that your project files have been uploaded successfully.

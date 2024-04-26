 >## **Section: Configuration (Config) Commands**

**1. Listing Configuration Settings:**
- **Command:** `git config -l`
- **Description:** This command lists all Git configuration settings for the current repository, including user settings, aliases, and other configurations.

**2. Listing Configuration Settings with Origin Information:**
- **Command:** `git config -l --show-origin`
- **Description:** This command lists all Git configuration settings for the current repository, along with the file where each setting is defined. It provides additional context by showing the origin of each configuration.

**3. Setting the Global Editor Configuration:**
- **Command:** `git config --global core.editor notepad`
- **Description:** This command sets the default text editor for Git across all repositories on your system to Notepad. Subsequent Git commands that require editing (such as commit messages) will open Notepad for input.

These commands allow you to view and manage Git configurations, including listing all configuration settings, displaying origin information for each setting, and setting global configurations like the default text editor. Understanding and managing Git configurations is essential for customizing your Git workflow and preferences.

>## **Section: Git Log Commands**

**1. Viewing Commit History:**
- **Command:** `git log`
- **Description:** This command displays the commit history of the current branch, showing details such as commit hashes, authors, dates, and commit messages. It presents the history in a chronological order, starting from the most recent commit.

**2. Viewing Compact Commit History:**
- **Command:** `git log --oneline`
- **Description:** This command displays a compact version of the commit history, showing only the first line of each commit message along with the corresponding commit hash. It provides a concise overview of the commit history, suitable for quick reference.

**3. Viewing Pretty-formatted Commit History:**
- **Command:** `git log --pretty=oneline`
- **Description:** This command displays the commit history in a pretty-formatted manner, showing each commit on a single line with additional information such as the commit hash, author, date, and commit message. It offers a more detailed yet concise representation of the commit history.

**4. Viewing Graphical Commit History:**
- **Command:** `git log --pretty=oneline --graph`
- **Description:** This command displays the commit history graphically, showing the relationships between commits using ASCII art. It visualizes branches, merges, and diverging histories, providing a clear overview of the repository's branching structure and commit lineage.

These commands allow you to explore and analyze the commit history of a Git repository, providing various levels of detail and visualization options to suit different needs. Understanding how to use Git log effectively is essential for tracking changes, understanding project history, and identifying potential issues or conflicts.


>## **Section: Git Diff Commands**

**1. Viewing Unstaged Changes:**
- **Command:** `git diff`
- **Description:** This command displays the differences between the changes in your working directory and the last commit. It shows lines added, modified, or removed in each file since the last commit.

**2. Viewing Changes for a Specific File:**
- **Command:** `git diff <file>`
- **Description:** Use this command to see the differences for a specific file between the changes in your working directory and the last commit. It highlights the lines that have been added, modified, or removed in the specified file.

**3. Viewing Staged Changes:**
- **Command:** `git diff --staged`
- **Description:** This command compares the changes between the staging area (index) and the last commit. It shows the differences for files that have been staged but not yet committed.

**4. Comparing Changes Between Two Commits:**
- **Command:** `git diff <commit> <commit>`
- **Description:** Use this command to compare the changes between two specific commits. It displays the differences introduced between the two commits, highlighting lines that have been added, modified, or removed.

**5. Comparing Changes Between Branches:**
- **Command:** `git diff <branch>`
- **Description:** This command compares the changes between your current branch and another branch. It shows the differences between the working directory of the current branch and the specified branch, highlighting lines that differ between the two branches.

These commands provide powerful tools for inspecting and understanding changes in your Git repository. Whether you need to review unstaged changes, compare specific files, or analyze differences between commits or branches, Git diff commands offer valuable insights into your project's history and development.



>## **Section: Staging and Unstaging Changes**

**1. Adding a New File:**
- **Description:** Let's assume you've created a new file named `readme.txt` in your repository.

**2. Staging Changes:**
- **Command:** `git add readme.txt`
- **Description:** This command stages the changes to the `readme.txt` file, preparing it to be committed to the repository.

**3. Unstaging Changes:**
- **Command:** `git reset readme.txt`
- **Description:** This command unstages the changes to the `readme.txt` file, removing it from the staging area. The file's modifications remain in your working directory.

**4. Removing File from Staging Area:**
- **Command:** `git rm --cached readme.txt`
- **Description:** This command removes the `readme.txt` file from the staging area without deleting it from your working directory. The changes to the file are still present in your working directory but are not staged for the next commit.

**5. Restoring File to Staged State:**
- **Command:** `git restore --staged readme.txt`
- **Description:** This command restores the `readme.txt` file to the staged state, reverting any unstaged changes and adding it back to the staging area.

**Difference Between Commands:**
- **`git reset readme.txt`:** Unstages changes in the specified file, reverting it to the state of the last commit.
- **`git rm --cached readme.txt`:** Removes the file from the staging area, but retains it in your working directory.
- **`git restore --staged readme.txt`:** Restores the file to the staged state, undoing any unstaged changes and adding it back to the staging area.

These commands provide flexibility in managing changes to your repository, allowing you to stage, unstage, and remove files from the staging area as needed during the development process. Understanding how to manipulate the staging area is essential for controlling which changes are included in your next commit.

>## **Section: Working with Remote Repositories**

**1. Adding a Remote Repository:**
- **Command:** `git remote add origin https://repositoryURL`
- **Description:** This command adds a remote repository with the specified URL under the name "origin" to your local repository. "Origin" is a common convention for the default name of the remote repository.

**2. Pushing to the Remote Repository:**
- **Command:** `git push -u origin main`
- **Description:** This command pushes the local main branch to the remote repository named "origin" for the first time. The `-u` option sets the upstream branch, linking your local main branch to the remote main branch. After setting the upstream, subsequent pushes can be done simply with `git push`.

**3. Pushing Additional Commits:**
- **Command:** `git push`
- **Description:** Once the upstream branch is set, this command pushes any new commits made to the local main branch to the remote repository without needing to specify the branch or remote. It automatically pushes to the upstream branch.

**4. Cloning a Remote Repository:**
- **Command:** `git clone https://repositoryURL`
- **Description:** This command clones a remote repository with the specified URL into a new local repository on your machine. By default, it creates a directory with the name of the repository.

**5. Cloning into the Current Directory:**
- **Command:** `git clone https://repositoryURL .`
- **Description:** This command clones a remote repository with the specified URL into the current directory. The dot at the end indicates that the repository should be cloned into the current directory instead of creating a new directory for it.

**6. Fetching Changes from Remote Repository:**
- **Command:** `git fetch`
- **Description:** This command fetches changes from the remote repository without merging them into your local branch. It updates your local repository's knowledge of the remote branch, allowing you to see changes without automatically merging them into your working branch.

**7. Pulling Changes from Remote Repository:**
- **Command:** `git pull`
- **Description:** This command fetches changes from the remote repository and automatically merges them into the current local branch. It's a combination of `git fetch` and `git merge`, pulling changes and incorporating them into your working branch in one step.

**8. Difference Between Fetch, Merge, and Pull:**
- **Fetch:** Retrieves changes from the remote repository and updates your local repository's knowledge of the remote branches without merging them into your working branch.
- **Merge:** Combines changes from a different branch into your current working branch, integrating the changes into your codebase.
- **Pull:** Fetches changes from the remote repository and automatically merges them into your current working branch, effectively updating your local branch with the changes from the remote branch.

Understanding the difference between these commands is essential for efficient collaboration and managing changes between local and remote repositories.
##

>## Introduction to Pull Requests:

Definition: A pull request (PR) is a mechanism for proposing changes to a repository hosted on platforms like GitHub. It allows contributors to notify project maintainers about changes they've made and request that those changes be reviewed and merged into the main codebase.


**1. Creating a Pull Request:**
- **Step 1:** Fork the Repository: If you don't have write access to the repository, fork it to your own GitHub account.
- **Step 2:** Clone the Repository: Clone the "Demo" repository to your local machine.
  ```bash
  git clone https://github.com/your_username/Demo.git
  ```
- **Step 3:** Create a New Branch: Create a new branch named "feature/branch" for your changes.
  ```bash
  git checkout -b feature/branch
  ```
- **Step 4:** Make Changes: Add a new file "e.txt" to the repository.
  ```bash
  notepad e.txt
  ```
- **Step 5:** Stage and Commit Changes:
  ```bash
  git add e.txt
  git commit -m "Added new file e.txt"
  ```
- **Step 6:** Push Changes to Remote:
  ```bash
  git push origin feature/branch
  ```
- **Step 7:** Open a Pull Request: Navigate to the repository on GitHub and click on the "Pull Request" tab. Then click "New Pull Request" and select the "feature/branch" branch.

**2. Reviewing a Pull Request:**
- **Step 1:** Notification: Maintainers are notified of the new pull request and can review it on GitHub.
- **Step 2:** Code Review: Reviewers examine the changes, including the addition of "e.txt".
- **Step 3:** Feedback and Discussion: Reviewers may leave comments on the pull request, suggesting improvements or asking questions.
- **Step 4:** Iterative Changes: You can make additional commits to the "feature/branch" branch to address feedback received during the review process.

**3. Merging a Pull Request:**
- **Step 1:** Approval: Once the changes are deemed satisfactory, a maintainer approves the pull request.
- **Step 2:** Merge: Click "Merge Pull Request" to merge the changes into the main branch of the "Demo" repository.
- **Step 3:** Confirm: Confirm the merge action, optionally deleting the source branch after merging.

**4. Closing a Pull Request:**
- **Step 1:** Notification: You are notified once your pull request has been merged.
- **Step 2:** Cleanup (Optional): You can delete the "feature/branch" branch after it has been merged.
  ```bash
  git checkout main
  git branch -d feature/branch
  ```
- **Step 3:** Feedback (Optional): Maintainers may provide feedback on the closed pull request, explaining reasons for acceptance or suggesting improvements for future contributions.

This example demonstrates the Pull Request process using a practical scenario with the "Demo" repository and the addition of a new file "e.txt" in the "feature/branch" branch.

 >### Pull the changes from the remote repository to the local repository after the Pull Request has been merged:

**4. Pulling Changes to Local Repository:**
- **Step 1:** Switch to the main branch of your local repository.
  ```bash
  git checkout main
  ```
- **Step 2:** Pull the latest changes from the remote repository to update your local main branch.
  ```bash
  git pull origin main
  ```

This step ensures that your local main branch is synchronized with the changes merged from the Pull Request on the remote repository.

 >## **Section: Git Merge and Rebase**

**1. Merging Changes from Main Branch:**
- **Command:** `git merge main`
- **Description:** This command integrates changes from the "main" branch into the current branch. It combines the commit history of both branches, creating a new merge commit if necessary. This is typically used to incorporate changes from the main branch into a feature branch or to update a feature branch with the latest changes from the main branch.

**2. Rebasing Changes onto Main Branch:**
- **Command:** `git rebase main`
- **Description:** This command reapplies commits from the current branch onto the tip of the "main" branch. It effectively moves the entire branch to begin from the tip of the "main" branch, rewriting the commit history. This is useful for maintaining a cleaner, linear history and resolving conflicts before merging changes into the main branch.

**Difference Between Merge and Rebase:**

- **Merge:** 
  - Combines the commit history of two branches, creating a new merge commit.
  - Preserves the existing commit history of both branches.
  - Maintains a branching structure in the commit history, showing where branches diverged and merged.
  - Suitable for integrating feature branches into the main branch or combining changes from multiple contributors.

- **Rebase:**
  - Rewrites the commit history of the current branch, applying commits onto a new base.
  - Results in a linear commit history, with all commits appearing in chronological order.
  - May create a cleaner, more linear history, but can lead to conflicts if changes conflict with the base branch.
  - Useful for maintaining a clean and orderly commit history, especially in long-running feature branches or when preparing changes for integration into the main branch.

Understanding the differences between merging and rebasing is crucial for choosing the appropriate strategy when incorporating changes from one branch into another. While merging preserves the branching structure and creates a merge commit, rebasing provides a cleaner, linear history by rewriting the commit history onto a new base. Each approach has its advantages and use cases, depending on the project's needs and workflow preferences.
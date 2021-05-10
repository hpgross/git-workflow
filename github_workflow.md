# Git/Github workflow

## 1. Creating a new project (repo)

### A. On Github

<https://github.com/new>

creates a new empty repo, with options for a README or .gitignore

### B. Locally

    git init

initializes a new empty git repo at the cwd

## 2. Updating the project locally (tracking, staging, and commits)

| command                           | purpose                                                               |
| ---                               | ---                                                                   |
| git add \<newfile>                | adds the file to the list of tracked files for the local repo         |
| git add \<file>                   | stages the changed file                                               |
| git status                        | shows status of working tree and staging area                         |
| git commit                        | commits the changes currently in the staging area and opens a text editor to make a commit message |
| git commit -m "\<commit message>" | commits the changes with an instant commit message as a parameter     |
| git commit -a                     | commits all current tracked changes without having to manually add files to the staging area |
| git rm \<file>                    | removes a file and makes it untracked                                 |
| git mv \<old> \<new>              | renames a file or moves it if you have subdirectories                 |
| git commit --amend                | amends the previous commit to have the new extra changes (don't do if you have updated remote) |

## 3. Reverting changes

| command                | purpose                                               |
| ---                    | ---                                                   |
| git checkout           | reverts to the stored snapshot in HEAD before staging |
| git reset HEAD \<file> | resets staged changes before a commit                 |
| git revert HEAD        | applies an inverse commit to the latest commit        |

## 4. Getting a repo onto a local machine (cloning)

    git clone <url>

clones the repo at the url to a new repo at the cwd/project

## 5. Getting those updates onto the internet (pull request, or push)

    git push

pushes the local main to the remote main if you have permissions to do so

## 6. Grabbing updates from the internet

    git fetch

grabs changes but DOESN'T APPLY THEM so that your working tree isn't changed

    git pull

grabs the changes to the remote main and puts them into your local main (it is fetch + merge)

## 7. Branch work

| command                 | purpose                                          |
| ----------------------- | ------------------------------------------------ |
| git branch              | lists the branches of the repo                   |
| git branch \<name>      | creates a new branch named name                  |
| git checkout \<branch>  | switches the working tree to the selected branch |
| git checkout -b \<name> | creates a new branch and moves to it instantly   |
| git branch -d \<branch> | deletes the selected branch, -D for hard delete  |
| git merge \<branch>     | merges the branch with the trunk                 |
| git merge --abort       | aborts the merge if it can't be resolved easily  |
| git branch - r          | lists the remote read-only branches              |

## Appendices

### A. Comparing files without vcs

    diff -u <file1> <file2>

can add > change.diff to get a changelog/patch
man page for diff is at <http://man7.org/linux/man-pages/man1/diff.1.html>

### B. Applying changes without vcs

    patch <file> < <file.diff>

man page for patch is at <http://man7.org/linux/man-pages/man1/patch.1.html>

### C. Helpful links and commands

| command                                           | purpose                                                      |
| ------------------------------------------------- | ------------------------------------------------------------ |
| git --version                                     | displays the installed version of git                        |
| git config -l                                     | tells the current config status of the local repo in the cwd |
| git config --global user.email "\<email address>" | sets your email address                                      |
| git config --global user.name "\<name>"           | sets your name                                               |
| git log                                           | generates the list of commits of the repo                    |
| git log -p                                        | generates the patches for each commit                        |
| git show \<substring of hash>                     | shows the specific commit in detail                          |
| git diff                                          | shows unstaged changes to HEAD                               |
| git log --graph --oneline                         | generates an ascii visual version tree                       |
| git config --global core.editor "\<editor> --wait"| changes the editor, if vscode --wait recommended             |

the --global flag in the above commands can be replaced with certain repo names for different projects

Full Git Documentation is at <https://git-scm.com/doc>

GitHub's git cheat sheet is at <https://training.github.com/downloads/github-git-cheat-sheet.pdf>

Setting up better workspace security management can be done by

* caching your password:     <https://help.github.com/en/articles/caching-your-github-password-in-git>
* setting up ssh:    <https://help.github.com/en/articles/generating-an-ssh-key>

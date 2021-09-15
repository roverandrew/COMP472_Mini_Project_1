# COMP472_Mini_Project_1

## Setup Instructions/Resources:
  ### Installing Python with Homebrew (for package management)
  * Install Homebrew: https://brew.sh/
  * Install Python 3.8.12 (latest 3.8 version) with brew: https://stackoverflow.com/questions/49470367/install-virtualenv-and-virtualenvwrapper-on-macos (use `brew install python@3.8`)

  ### Repo Setup
  * We will be using the Forking Workflow, for more info see: https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow
  1) Fork this repo
  2) `git clone [url-of-fork]`
  3) Set the upstream branch (main repo) on your local: `git remote add upstream https://github.com/roverandrew/COMP472_Mini_Project_1`
  4) Set the origin branch (The server-side copy of the repo, the fork), on your local: `git remote add origin [url-of-fork]`
  5) double-check the remotes have correctly been set using `git remote -v`

## Git Workflow
  ### What is `rebase` and why are we using it?:
  <img width="565" alt="Screen Shot 2021-09-15 at 1 52 16 PM" src="https://user-images.githubusercontent.com/54918397/133484503-4d14cd90-9d01-46d8-bbef-f053d46d1ca3.png">
  - Basically, it stacks branches on top of eachother.
  - It's easy to use and keeps the commit history linear, allows use of interactive rebase git commands which basically allow you to rename commits, squash multiple commits into one, and other cool stuff.
  - Also because I've never used merge before lol

  ### Updating your local with the latest upstream changes
    `git pull --rebase upstream main`
   - Here we are fetching the latest changes from the codebase, and rebasing from it (meaning we are stacking our latest changes on top of it, if there are any)

  ### Creating a Pull Request
  `git push --set-upstream origin [name of branch describing feature/task/wtv]`
  * If a PR is not to be reviewed, just immediately merge if there are no conflicts. This will probably be most cases. If a PR is to be reviewed, merge it once approved and there are no conflicts.
  
  ### Updating a PR
  `git push --force-with-lease`
  
  ### General workflow is:
  1) Have a main branch on your local that you keep up-to-date with `git pull --rebase upstream main`, should be a reflection of the upstream `main` branch.
  2) Whenever working on a feature, `git checkout` a new branch and add all your new commits on that branch.
  3) Push your changes to the new repo. BUT before doing so, update your feature branch using `git pull --rebase upstream main` to stack your recently made commits on top of the latest version of the upstream repo. So in summary when ready to push: Update feature branch, then push changes.
  4) And repeat for any new features, keeping your local `main` updated, and created feature branches off of it.

  ### Fixing Merge Conflicts
  * Rebasing involves re-writing git history, so merge conflicts may have to be fixed for multiple commits. If working on a feature that has many commits, I'd encourage squashing commits together (see: https://www.youtube.com/watch?v=V5KrD7CmO4o), to avoid this and make things easier.
  1) Make the changes that fix the merge conflicts for the given commit, then `git add` them.
  2) run `git rebase --continue`, which will implement these fixes, and then move to the next commit that is to be rebased, repeating the process.

# COMP472_Mini_Project_1

## Setup Instructions/Resources:
  ### Installing Python with Homebrew (for package management)
  * Install Homebrew: https://brew.sh/
  * Install Python 3.8.12(latest 3.8 version) with brew: https://stackoverflow.com/questions/49470367/install-virtualenv-and-virtualenvwrapper-on-macos


## Git Workflow
  ### What `Rebase` does in a nutshell:
  <img width="565" alt="Screen Shot 2021-09-15 at 1 52 16 PM" src="https://user-images.githubusercontent.com/54918397/133484503-4d14cd90-9d01-46d8-bbef-f053d46d1ca3.png">
  - Basically, it stacks branches on top of eachother.
 
  ### Why use it?
  - ez
  - Keeps the commit history linear, allows use of interactive rebase git commands which basically allow you to rename commits, squash multiple commits into            eachother, and other cool stuff.
  - Also because I've never used merge before lol
  
  ### Pulling changes from the remote:
    ```git pull --rebase upstream main```
   - Here we are fetching the latest changes from the codebase, and rebasing from it (meaning we are stacking our latest changes on top of it, if there are any)

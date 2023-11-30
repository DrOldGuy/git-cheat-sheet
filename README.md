# How to use git and GitHub

## Prerequisites

Install the git client following the instructions in my [promineo-installation-instructions](https://github.com/DrOldGuy/promineo-installation-instructions) repo.

## Create a repository (repo) in GitHub

When working in a Cmd or Terminal window, you must press the Enter key after typing each command to execute the command.

1. Log into GitHub
1. Click your profile picture or the "missing image" picture at the top-right of the page. Click on "Your repositories".
1. Click the bright green  _New_  button.
1. Enter the name of the new repository. Make sure that the repository is public. Click  _Add a README file_ . Click  _Add .gitignore_  and select  _Java_  as the .gitignore template. Click the bright green  _Create repository_  button. (You may need to scroll the page to see it.)
1. From the  _Your Repositories_  page in GitHub, click on the new project name.
1. Click the bright green  _Code_  button. Make sure that  _SSH_  is selected. Click on the  _copy_  icon to the right of the repository name.
1. Open a Cmd or Terminal window. Navigate to the workspace directory (the directory that has a .metadata folder in it - may be hidden), which will be the parent directory of the new project. Type **git clone** then paste the content of the clipboard onto the command line. So, for my repo named git-cheat-sheet, I would navigate to my workspace directory and then type: **git clone https://github.com/DrOldGuy/git-cheat-sheet.git**. This creates a subdirectory named  _git-cheat-sheet_ . This directory has a .git folder in it (may be hidden).

## Link the repository to an Eclipse project

1. Start Eclipse or Spring Tool Suite (STS), selecting the workspace in which you cloned the GitHub repo.
1. Click  _File_  in the top menu. Then select  _New / Java Project_ .
1. Enter the project name. This should be the same name as the git repo (actually the same name as the project directory that git created). Ensure that  _Create module-info.java file_  is  _not_  selected. Click  _Finish_ . The project will be created in Eclipse.
1. Expand the project in the Package Explorer. You should see a file named .gitignore. If you don't, click the button with 3 dots at the top of the Package Explorer. In the popup menu, select  _Filters..._ . In the scrolling window in the middle of the  _Java Element Filters_  panel, uncheck  _.*resources_ . Click _OK_ . Now, you should see the .gitignore file. Open .gitignore in the editor.
1. Add these lines at the bottom and save the file:

```
# Eclipse files
.settings/
bin/
target/
```

## Push the Eclipse project to GitHub

After making changes to your project you will need to push the changes to GitHub so that others can see them. After you have typed a command in this section you will need to press the Enter key to execute the command.

1. Open a Cmd or Terminal window and navigate to the project directory - it is the directory with the .git folder in it. If you type **dir** (Windows) or **ls -l** (MacOS) you will not see this folder. For Windows, type **dir /a**. For MacOS, type **ls -al**.
1. Type **git status**. You should see changed files in red test.
1. Type **git add --all**. This will stage the changed files.
1. Type **git commit -m "{{upload-message}}"**, where {{upload-message}} is a meaningful message, like "Added Java class files for week 3".
1. Type **git push**. This will upload and merge all changed files without creating a Pull Request. (You won't need a Pull Request unless you are working on a team project.)

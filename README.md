git-pre-commit-hook-unity-assets
================================

Pre-commit hook script for Unity to check that every folder that just has marked to be ignored in .gitignore 
has an entry for its meta file to be ignored too.

Example: MyProject/Assets/Imports/LocalTest is a new folder that should not be under version control. So in 
.gitignore there is a new line:
MyProject/Assets/Imports/LocalTest

The pre-commit hook checks if there is a line containing "LocalTest.meta" in the changes of .gitignore too. 
If so everythingis alright, if not commit will be aborted and a message is shown:

MyProject/Assets/Imports/LocalTest found in .gitignore but not the corresponding meta file! Please add 
LocalTest.meta to .gitignore

Put the file pre-commit into directory .git/hooks. To disable it remove it from there.

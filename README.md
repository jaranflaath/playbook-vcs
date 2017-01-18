# playbook-vcs
Version Control System Playbook

#Git
Git is the preferred VCS. Unless there is a technical reason it is unsuited, every code project should be in a git repository.

##Branches
A feature or fix branch name includes the identifier of the task it is related to (JIRA or otherwise), to facilitate hooks and to make work traceable in both directions. Start branch name with fix/ or feature/, followed by the task name separated by hyphens. E.g. `feature/NR-123-name-of-task`.

##Commits
A git commit message should have  
Title: `JIRA-REF: What did you do / which changes did you make`  
Description: `Motivation for task and why did you do it in this way.`

Where there's no specific jira task you may use domain identifiers like `Fastlane`, `Readme`, `Xcode`.

Examples
```
BAXAPP-94: Change format of public key / ebaxtoken

Server expects public key to be in base64 instead of hex
```
```
BAXAPP-76: Change text in label on home screen

We should use "Touch ID / PIN" concistently throughout the app
```
```
Fastlane: Disable use_legacy_build_api

This makes app size go from 60mb to 9mb
```
```
Xcode: Updating xcode project files

Opening the project in Xcode 8.2.1 made these changes automatically
```

## Do not check in commented out code
Don't do it

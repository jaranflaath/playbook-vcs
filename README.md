# playbook-vcs
Version Control System Playbook

#Git
Git is the preferred VCS. Unless there is a technical reason it is unsuited, every code project should be in a git repository.

##Branches
A feature or fix branch name includes the identifier of the task it is related to (JIRA or otherwise), to facilitate hooks and to make work traceable in both directions. Start branch name with fix/ or feature/, followed by the task name separated by hyphens. E.g. `feature/NR-123-name-of-task`.

## Do not check in commented out code
Don't do it

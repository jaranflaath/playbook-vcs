# playbook-vcs
Version Control System Playbook

# Git
Git is the preferred VCS. Unless there is a technical reason it is unsuited, every code project should be in a git repository.

## Branches
Our branching is git-flow-like:
* one master branch where HEAD is most recent completed development 
* feature-branches
    * branch from master
    * created for each task, whether it is feature, story, improvement, fix or what-have-you
    * merge into master once task is complete and verified by the project's test/qa/code review
* release-branches
    * branch from master
    * created if necessary: 
        * if a release candidate is built, but a critical bugfix or other change needs to be included in the release _and_ further development which was not intended for this release has happened on the master branch
        * if an issue is discovered in a released build which needs to be addressed immediately, _and_ there are changes on the master branch which are not ready for release (e.g. requires changes to server code not scheduled for deploy yet)
    * once build is actually released, merge into master
* hotfix-branches 
    * branch from release-branches
    * created if an issue that must be fixed is discovered after release process is started
    * merge into release-branch and into master branch
* For each build actually released, tag the commit that build was created from
 
A notable difference from git-flow as originally outlined (http://nvie.com/posts/a-successful-git-branching-model/) is that we use master for development rather than have a separate develop branch and using master for archiving most recent release. This is because the version tags provide sufficient archival information and the further benefit described by Driessen, of allowing automatic roll-out from each commit on master, is rarely, if ever, useful to us.

*Note: All branches apart from master should strive to be shortlived to minimize conflicts and attendand problems when merging.*

### Branch names
A feature or hotfix branch name consists of the identifier of the task it is related to (JIRA or otherwise), to facilitate hooks and to make work traceable in both directions. Start branch name with feature/ or hotfix/, followed by the task id separated by hyphens: `feature/ACME-123`. Release branches are named release/&lt;version number&gt;: `release/1.5.1`.

## Commits
A git commit message should have  
Title:
`JIRA-REF: What did you do / which changes did you make`  
Description (Optional, suggested for non-trivial commits):
`Motivation for task and why did you do it this way.`

Occasional small changes may not have an associated task, such as bumping version number or updating README. It is suggested, but not required, to use simple domain identifiers for these, to keep the format similar, e.g. `Fastlane`, `Readme`, `Xcode`.

Examples
```
ACME-94: Change format of public key / acmetoken

Server expects public key to be in base64 instead of hex
```
```
ACME-76: Change text in label on home screen

We should use "Touch ID / PIN" concistently throughout the app
```
```
ACME-123: Change pager opening animation: slide in from right rather than bottom
```
```
Fastlane: Disable use_legacy_build_api

This makes app size go from 60mb to 9mb
```
```
Readme: Added section explaining the Alertify feature
```
```
Xcode: Updating xcode project files

Opening the project in Xcode 8.2.1 made these changes automatically
```

## Pull requests

All code goes through pull requests before they are merged to development or release branches. Pull requests is a good way to both get a second pair of eyes on your code, and to spread knowledge about changes done in the projects. All team members should be added to all pull requests, both to spread visibility of the changes made, and to spread the workload of doing the reviews. 

### Workflow for pull requests

1. Submitter
   1. Squash commits into one or more logical commits outlining the changes you have made in your feature branch. Your pull request should contain as few commits as possible. 
   1. Submit pull request and add all your relevant team members as reviewers (if you work on the Android version of an application, add all the Android developers on your team to the pull request). You should also add any non-project resources that you know will have input on your change. I.e. if you have made some changes to to the authentication code of your project, you can add resources that you know are experts in this field to get their eyes on your changes as well.
1. Reviewer
   1. Perform your code review (to be added: link to checklist / guidelines for performing a good code review)
   1. When done, 
      * if there are things that needs the submitter's attention before the pull request can be merged, post a comment informing the submitter that you want your comments to be looked at before the pull request is merged. 
      * if there are no comments, merge the pull request and ignore the rest of this list
1. Submitter
   1. Wait until the reviewer(s) explicitly comments that their round of review is done, to prevent both reviewing and updating of the code happening at the same time
   1. Review and perform any changes requested by the reviewer(s).
   1. Commit all your changes as _one_ commit, this makes it much easier for the reviewer(s) to review the updates 

## Do not check in commented out code

Don't do it


## License
<p xmlns:dct="http://purl.org/dc/terms/" xmlns:vcard="http://www.w3.org/2001/vcard-rdf/3.0#"><a rel="license" href="http://creativecommons.org/publicdomain/zero/1.0/"><img src="https://licensebuttons.net/p/zero/1.0/88x31.png" style="border-style: none;" alt="CC0" /></a><br />To the extent possible under law, <a rel="dct:publisher" href="http://agens.no"><span property="dct:title">Agens AS</span></a> has waived all copyright and related or neighboring rights to<span property="dct:title">Playbook-vcs</span>. This work is published from: <span property="vcard:Country" datatype="dct:ISO3166" content="NO" about="http://agens.no">Norway</span>.</p>

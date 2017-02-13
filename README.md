# playbook-vcs
Version Control System Playbook

#Git
Git is the preferred VCS. Unless there is a technical reason it is unsuited, every code project should be in a git repository.

##Branches
A feature or fix branch name consists of the identifier of the task it is related to (JIRA or otherwise), to facilitate hooks and to make work traceable in both directions. Start branch name with fix/ or feature/, followed by the task id separated by hyphens. E.g. `feature/NR-123`. Release branches are named on the format of `release/1.5.1`.

##Commits
A git commit message should have  
Title:
`JIRA-REF: What did you do / which changes did you make`  
Description (Optional, suggested for non-trivial commits):
`Motivation for task and why did you do it this way.`

Occasional small changes may not have an associated task, such as bumping version number or updating README. It is suggested, but not required, to use simple domain identifiers for these, to keep the format similar, e.g. `Fastlane`, `Readme`, `Xcode`.

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
IVYA-123: Change pager opening animation: slide in from right rather than bottom
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

## Do not check in commented out code

Don't do it


## License
<p xmlns:dct="http://purl.org/dc/terms/" xmlns:vcard="http://www.w3.org/2001/vcard-rdf/3.0#"><a rel="license" href="http://creativecommons.org/publicdomain/zero/1.0/"><img src="https://licensebuttons.net/p/zero/1.0/88x31.png" style="border-style: none;" alt="CC0" /></a><br />To the extent possible under law, <a rel="dct:publisher" href="http://agens.no"><span property="dct:title">Agens AS</span></a> has waived all copyright and related or neighboring rights to<span property="dct:title">Playbook-vcs</span>. This work is published from: <span property="vcard:Country" datatype="dct:ISO3166" content="NO" about="http://agens.no">Norway</span>.</p>

# git

## submodules
git submodule add https://github.com/inveniosoftware/flask-menu
- just points to the external repo
git submodule init
git submodule update

# scalar
- for bigger repos

scalar clone
 - used for new repo
 - uses partial clone, sparse checkout, git maintenance, optimizing stuff

scalar register
- optimize and maintain that direcory. used for existing repo

# github signin w/Entra ID
- requires github enterprise
From Entra:
- uses saml sso 
- add aad users to github sso
From Github
- enable saml
- configure link to aad tenant

# incorporate changelogs
- trail of commits
- keep running list of updates, useful for teams
## Manually creating / viewing changes
git log
git log --oneline
git log --pretty="- %s"
## automation options
- third party apps
- ide plugins (generate release notes (crossplatform))
- pipelines plugins (jenkins has a plugin)

# fork
press fork in azdo, cline to vsc.

in vsc
git remote add upstream {upstream_url}

after pr is accepted:
git fetch upstream main
git rebase upstream/main
git push origin
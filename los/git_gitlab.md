# delete permanently commits from remote repository with https://gitlab.amc.nl

git log 
git reset --hard 0c804fdd2398b63e08e97e
git push origin master --force
# can't do that because of restrictions in the GitLab repository.

#To solve: https://gitlab.amc.nl/dhdresschers/ptvd/-/settings/repository#js-protected-branches-settings
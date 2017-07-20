use branches to get the index in a test state: repo_mixed, repo_crlf, repo_lf

do NOT commit .gitattributes. rename dot.gitattributes for a new working copy
working copy one will be used if there is not one in the index
it's listed in .gitignore so it doesn't appear as untracked in git status

pay attention to the settings of core.eol and core.autocrl
can set them locally for testing
for example: git config --local core.eol lf ; git config --local --unset core.eol

git ls-files --eol is useful
or git-files --eol | grep crlf

rebuilding the index is necessary for new eol settings to be reflected:
git rm --cached -r .
git reset

to update all working copy files :
git rm -rf .
git reset --hard

#git subtree お勉強

## combineリポジトリへ取り込み
git remote add subtree01_origin https://github.com/seekersjp/subtree01.git
git subtree add --squash --prefix=module/subteee01 subtree01_origin master

## combineリポジトリで変更
git commit -m "modify: module/subtree01"
git subtree split --prefix=module/subtree01 -b combine/develop
git checkout combine/develop
git push subtree01_origin
git checkout develop

## ひょっとしてこれでもOK?
git subtree push --prefix=module/subtree01 subtree01 combine/develop

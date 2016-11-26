#git subtree お勉強

## combineリポジトリへ取り込み
git remote add subtree01_origin https://github.com/seekersjp/subtree01.git
git subtree add --squash --prefix=module/subteee01 subtree01_origin master

## combineリポジトリで変更
git commit -m "modify: module/subtree01"
git subtree push --prefix=module/subtree01 subtree01_origin combine/develop

github側でpullrequestなりを投げてmasterにマージ

git subtree pull --prefix=module/subtree01 subtree01_origin

# 別でcloneしたところから投げて、拾ってみる
git subtree pull --prefix=module/subtree01 subtree01_origin develop

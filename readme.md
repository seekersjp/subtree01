#git subtree お勉強

## subtree01

## combineリポジトリで変更

git subtree push --prefix=module/subtree01 subtree01 master

master ブランチが更新される。(考えてみれば当然)

## combineリポジトリで変更, splitしてsubtree01/developへpush

git commit -m "modify: module/subtree01"
git subtree split --prefix=module/subtree01 -b develop

履歴がおかしくなったのでリトライ
git subtree split --prefix=module/subtree01 -b develop

git checkout subtree01/develop

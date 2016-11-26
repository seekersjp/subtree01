#git subtree お勉強

## subtree01

## combineリポジトリで変更

git subtree push --prefix=module/subtree01 subtree01 master

master ブランチが更新される。(考えてみれば当然)

## combineリポジトリで変更, splitしてsubtree01/developへpush

git commit -m "modify: module/subtree01"
git subtree split --prefix=module/subtee01 -b develop

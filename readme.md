#git subtree お勉強

## combineリポジトリへ取り込み

``` bash
git remote add subtree01_origin https://github.com/seekersjp/subtree01.git
git subtree add --squash --prefix=module/subteee01 subtree01_origin master
```

## combineリポジトリで変更

``` bash
git commit -m "modify: module/subtree01"
git subtree push --prefix=module/subtree01 subtree01_origin combine/develop
```

github側でpullrequestなりを投げてmasterにマージ

``` bash
git subtree pull --prefix=module/subtree01 subtree01_origin
```

## 別でcloneしたところから投げて、拾ってみる

``` bash
git subtree pull --prefix=module/subtree01 subtree01_origin develop
```

# まとめ

## 別のリポジトリからモジュールなりライブラリを取込む時

``` bash
git remote add <refname> <repo_url>
git subtree add --squash --prefix=<path/to/module> <refname> <commit>
```

## モジュールなりライブラリなりの変更を反映

``` bash
git subtree pull --prefix=<path/to/module> <refname> <commit>
# マージコミットメッセージの入力を促されるので入力する
```

## 自分の中でモジュールなりライブラリなりを変更した内容をpush

``` bash
git subtree push --prefix=<path/to/module> <refname> <commit>
# この時のcommitは適当に名前をつけてコミット 親モジュール名/develop とかで被らないようにしてたらいいんじゃね？
```

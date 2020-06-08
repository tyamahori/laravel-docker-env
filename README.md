# このリポジトリは？
Docker for Mac の利用を前提としたlaravelサンプルプロジェクトです。

# 対象は？
Laravelプロジェクトにて、Docker for Mac の挙動が遅いと感じている人。

# 何を得られるのか？
Docker for Mac のスピードアップのための対応策。

# 注意点
laravel/vendorディレクトリはホスト側から消さないでください。

# ポイント
1. あくまでもローカル開発用です。Docker環境の改善点は多々あります。
1. NginxコンテナではLaravelのpublicディレクトリのみをマウントしています。
1. vendorディレクトリを直接マウントしてません。
1. vendorディレクトリがコンテナにあるだけだと、PhpStormなどでIDE補完が効かなくなります。なので docker cp を使いローカルにvendorディレクトリを持ってきます。
1. シェルスクリプトにてコマンドをラップしました。docker/formac/formac を確認してください。

# セットアップ方法
1. `cd docker/formac`
1. `./formac setup`
1. `./formac logs` (ログを出力したい場合)

# バージョン情報
|項目名|バージョン|
|:---:|:---:|
|PHP|7.4|
|Laravel|7.4|
|MySQL|8.0|


```
docker build -t tyamahori-nginx:latest -f docker/aws/nginx/Dockerfile .
docker build -t tyamahori-php:latest -f docker/aws/php/Dockerfile .
```

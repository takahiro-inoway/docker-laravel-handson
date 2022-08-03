# docker-laravel-handson
0:gitの準備
```
$ git config --global user.name "takahiro-inoway"
$ git config --global user.email "takahiro.inoway@email.com"
$ git config --list
```
1:cloneしてビルド
クローン方法について→https://pengi-n.co.jp/blog/github-clone/
```
[mac] $ git clone git@github.com:takahiro-inoway/docker-laravel-handson.git projectname
[mac] $ cd docker-laravel-handson
[mac] $ docker compose up -d
```
2:権限付与とインストール
```
[mac] $ docker compose exec app bash
[app] $ chmod -R 777 storage bootstrap/cache
[app] $ composer install
```
3:.envファイルの作成
```
[app] $ cp .env.example .env
```
4:Laravelアプリケーションキーの作成
```
[app] $ php artisan key:generate
```
5:シンボリックリンクの貼付
```
[app] $ php artisan storage:link
```
6:マイグレーション
```
[app] $ php artisan migrate
```

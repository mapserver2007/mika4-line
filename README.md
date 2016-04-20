# mika4-line
## インストール
以下のものをインストール。
* `node.js`,`npm`,`nvm`

以下のコマンドを実行

```sh
$> npm install -g hubot coffee-script generator-hubot
$> mkdir bin
$> cd bin
$> yo mika4
```

アダプターは`line-trial`を指定する。

## ローカル実行
OSX

```sh
$> brew install redis
$> redis-server /usr/local/etc/redis.conf
$> bin/hubot --name mika4
```

## LINE設定
* LINE Developersにてアカウントを取得する
* FIXIEでIPアドレスを固定し、`Server IP Whitelist`に登録する
* コールバックURLを指定する
* 秘密情報は`config/hubot.secret.yml`に記述する

## Herokuデプロイ
```sh
$> heroku login
$> heroku create
$> rake heroku_env
$> rake
```

プラグインは以下のものを入れる。
* Process Scheduler
    * 8:00-2:00
* Heroku Scheduler
    * hubot-heroku-keepaliveを指定時間に起動するためのスケジューラ
    * curl ${HUBOT_HEROKU_KEEPALIVE_URL}heroku/keepalive
    * UTCなので開始時間の9時間前を指定。開始時間は8:00なので23:00を指定

## LINEにインストール
QRコードを読ませる。

## License
Licensed under the MIT  
http://www.opensource.org/licenses/mit-license.php

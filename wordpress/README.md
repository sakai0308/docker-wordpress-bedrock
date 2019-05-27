# docker-composeを起動
```
自身のPC
$ docker-compose build
  ↑一度だけ実行するコマンド
$ docker-compose up -d
```

# Docker内のWordPressサーバに接続
```
自身のPC
$ docker-compose exec wordpress bash
```

# WordPressをインストールする手順
```
Docker内
# composer create-project roots/bedrock
```

ブラウザで以下URLを打鍵
http://localhost/

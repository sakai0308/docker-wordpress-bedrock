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
$ docker-compose exec wp bash
```

# WordPressをインストールする手順
# (既にwordpress/html/bedrockが存在する場合は不要)
```
Docker内
# composer create-project roots/bedrock
```

# 事前準備
```
Docker内
# cd bedrock
# composer install
```

ブラウザで以下URLを打鍵
http://localhost/

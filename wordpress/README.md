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

# 以下ファイルを書き換える
/etc/apache2/sites-enabled/000-default.conf
```
<VirtualHost *:80>
        DocumentRoot /var/www/html/bedrock/web

        DirectoryIndex index.php index.html index.htm

        <Directory /var/www/html/bedrock/web>
            Options -Indexes

            # .htaccess isn't required if you include this
            <IfModule mod_rewrite.c>
                RewriteEngine On
                RewriteBase /
                RewriteRule ^index.php$ - [L]
                RewriteCond %{REQUEST_FILENAME} !-f
                RewriteCond %{REQUEST_FILENAME} !-d
                RewriteRule . /index.php [L]
            </IfModule>
        </Directory>
</VirtualHost>
```

ブラウザで以下URLを打鍵
http://localhost/

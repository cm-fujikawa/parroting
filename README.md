# parroting

## 概要

オウム返しするだけのWebアプリケーションです。

## 使い方

1. 次のいずれかのコマンドを実行し、コンテナを起動/停止してください。

    * `Dockerfile`を使用する場合

        ```shell
        docker build -t cm-fujikawa/parroting .
        docker run -d --rm -p 8080:80 -v $(pwd)/html:/var/www/html --name parroting cm-fujikawa/parroting
        docker stop parroting
        ```

    * `docker-compose.yml`ファイルを使用する場合

        ```shell
        docker-compose up -d
        docker-compose down
        ```

2. 次のURLにアクセスしてください。

    http://localhost:8080/env.php

## トラブルシュート

### 403 Forbidden

* コンテナにログインし、`/var/www/html`ディレクトリに所有者以外への実行権限を付与してください。

    ```shell
    chmod 755 /var/www/html
    ```

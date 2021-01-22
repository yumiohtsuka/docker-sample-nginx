# docker-sample-nginx

A sample nginx container for training

Cloneする前に以下のコマンドでウェブサーバーを起動してみる

```
$ docker run --rm -d -p 8080:80 --name web nginx
```

ブラウザーで　http://localhost:8080 にアクセスして動作確認

動作を停止

```
$ docker stop web
```

このレポジトリーをClone

```
$ git clone https://github.com/osonoi/docker-sample-nginx.git
```

Dockerfileを参照、index.htmlを編集
イメージを作成

```
$ docker build -t webserver .
```

イメージを起動

```
$ docker run --rm -d -p 8080:80 --name web webserver
```

動作を停止

```
$ docker stop web
```

イメージをDockerHubにアップロード

```
$ docker login
$ docker tag webserver yosonoi/webserver
$ docker push yosonoi/webserver:latest
** yosonoiのところはご自分のアカウント名にしてください。
```

dockerHubでイメージを確認

https://hub.docker.com/

DockerHubのイメージで起動

```
docker run -it --rm -d -p 8080:80 --name web yosonoi/webserver
```


# docker-sample-nginx

a sample nginx container to display container name

Cloneする前に以下のコマンドでウェブサーバーを起動してみる

$ docker run -it --rm -d -p 8080:80 --name web nginx

ブラウザーで　http://localhost:8080 にアクセスして動作確認

動作を停止

$ docker stop web

このレポジトリーをClone

$ git clone https://github.com/osonoi/docker-sample-nginx.git

イメージを作成

$ docker build -t webserver .

イメージを起動

$ docker run -it --rm -d -p 8080:80 --name web webserver

イメージをDockerHubにアップロード

$ docker login
$ docker tag webserver yosonoi/webserver
$ docker push webserver:latest
** yosonoiのところはご自分のアカウント名にしてください。

dockerHubでイメージを確認

https://hub.docker.com/

DockerHubのイメージで起動

docker run -it --rm -d -p 8080:80 --name web yosonoi/webserver



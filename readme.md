自作 nginxコンテナを作ろう
====

```
docker run -it --rm debian:jessie bash
```

rootでログインして、linuxで
apt-get update
apt-get install -y nginx
nginx -g "daemon off;"
を実行

### ここまでの作業をdockerfileにしてみよう

dockerfileを作る

``` dockerfile
FROM debian:jessie

RUN apt-get update
RUN apt-get install -y nginx

CMD ["nginx", "-g", "daemon off;"]
```

powershellで
docker build -t my-nginx .
docker run -it --rm -p "80:80" my-nginx

docker run

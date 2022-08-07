# DockerBuild-RaspberryPi64-Dnsmasq
RaspberryPi(64bit)にDockerでDnsmasqを構築（内部向けのDNS構築）

## 環境
- kernel：Linux ホスト名 5.15.32-v8+ #1538 SMP PREEMPT Thu Mar 31 19:40:39 BST 2022 aarch64 GNU/Linux
- OS：Debian GNU/Linux 11 (bullseye)

## ドメイン名を変更
./conf/dnsmasq.conf<br>
[ドメイン名]を変更する(例: local or example.com)

## コンテナ起動
docker-compose.ymlを配置したフォルダに移動して実行
~~~
$ docker-compose up -d --build
~~~
alpine linuxベースなのでコンテナに入るときは`bash`ではなく`ash`を使う
~~~
$ docker exec -it [コンテナid] /bin/sh
~~~

## 名前解決は/etc/hostsで行う
~~~
$ vi /etc/hosts
~~~

## DNSに問い合わせ
~~~
digの場合
$ dig @[DNSホストのIP] ドメイン名
nslookupの場合
$ nelookup ドメイン名　[DNSホストのIP]
~~~

## 参考
- [DnsmasqをDockerで起動する](https://scribble.washo3.com/dnsmasq_on_docker.html)
- [DockerでDnsmasqを使ったローカル環境の内部DNSを構築するメモ](https://7me.nobiki.com/2020/04/22/dnsmasq-docker-memo/)

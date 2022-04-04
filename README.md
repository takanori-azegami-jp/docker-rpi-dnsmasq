# DockerBuild-RaspberryPi64-Dnsmasq
RaspberryPi(64bit)にDockerでDnsmasqを構築（内部向けのDNS構築）

## コンテナ起動
docker-compose.ymlを配置したフォルダに移動して実行
~~~
$ docker-compose up -d --build
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
[DnsmasqをDockerで起動する](https://scribble.washo3.com/dnsmasq_on_docker.html)

RaspberryPi(arm64bit)環境でビルドされた下記Dockerイメージを使用<br>
[Docker Hub：4km3/dnsmasq](https://hub.docker.com/r/4km3/dnsmasq)

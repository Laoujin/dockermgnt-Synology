# dockermgnt

Pihole & Portainer.


## Install

```sh
git clone https://github.com/Laoujin/dockermgnt-Synology
cp .env-example .env

docker network create --driver macvlan --subnet [IPADDRESS]/[CIDR} --gateway [IPADDRESS] --opt parent=eth0 mainLan

# example
# with 192.168.1.1 the Telenet router IP
docker network create --driver macvlan --subnet 192.168.1.0/24 --gateway 192.168.1.1 --opt parent=eth0 mainLan
```


## Start

```sh
docker-compose up -d
```

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

## Pi-hole Config

### Automatically for all devices

- Connect with cable, not Wifi
- Settings > DHCP
    - DHCP server enabled
    - Router (gateway) IP address: Take Telenet modem IP (probably 192.168.1.1)
    - Enable DHCPv4 rapid commit (fast address assignment)
    - Pi-hole domain name: pongit.synology.me
- On Telenet modem disable DHCP


### After setup

- Settings > Teleporter
- Backup settings


## Unifi Config

- Settings > Networks > Edit "MainLan / Port=LAN1"
    - DHCP Mode: None
    - DHCP Guarding
        - Enable
        - IP: IP of Pi-hole (.env: PIHOLE_IP)

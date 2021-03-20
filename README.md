# docker_wireguard

## Server
- mkdir wireguard-server
- docker-compose up -d
- docker exec -it wireguard wg --> para ver el estado del servicio
- scp wireguard-server/config/peer1/peer1.conf CLIENTE

---
## Cliente
- sudo apt install -y wireguard resolvconf
- mv peer1.conf /etc/wireguard/wg0.conf
- wg-quick up wg0

---
Para agregar mas clientes hay que aumentar el numero de peers en el docker-compose.yml y reinicar el container con:
- docker-compose up -d --force-recreate
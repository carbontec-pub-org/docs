# Polymer testnet setup.

## Requirements

Make sure you have fresh docker installed.\
Make sure you have opened and not binded with other applications 8575/tcp, 30311/udp ports in order to communicated with node via rpc endpoint(8575) and also node can communicate with other nodes in network via p2p(30311). Websocket modules avialable at 8576 port. Also make sure you dont covered by nat or any other network stuff.
Make sure you login into carbontec public registry. In order to do that use following commands:

```bash
docker login https://registry.devgraphite.com
```
now promt will be ask for credentials. Use next credentials to identify your slf.

Pull latest docker image.
```bash
docker pull registry.devgraphite.com/polymer-testnet:amd64
```

Cleanup old containers if needed.
```bash
docker rm --force polymer-testnet
```

Wipe previous data folder if needed.
```bash 
sudo rm -rf /home/User/polymer-data && mkdir /home/User/polymer-data
```

### Anonymous entrypoint node setup instructions.

In order to run localy with docker you need to create folder for persist data inside container. In example folder is ```/home/User/polymer-data``` . \
After creating folder you need to run init task to inject genesis and persist it. You can do it with following command:
```bash
docker run -it -v /home/User/polymer-data:/var/lib/graphite/data registry.devgraphite.com/polymer-testnet:amd64 graphite --datadir /var/lib/graphite/data init /var/lib/graphite/genesis.json
```
Now you can run your node. In order to do it use following command:
```bash
docker run -d --name polymer-testnet --network host -v /home/User/polymer-data:/var/lib/graphite/data registry.devgraphite.com/polymer-testnet:amd64 graphite --datadir /var/lib/graphite/data --config /var/lib/graphite/config.yaml
```
Now you can check node sync proggress with following command:
```bash
docker logs polymer-testnet --follow
```
To interact node with graphite js console use following command:
```bash
docker exec -it polymer-testnet graphite attach /var/lib/graphite/data/geth.ipc
```
Node rpc api is avaialable at ```http://127.0.0.1:8575```

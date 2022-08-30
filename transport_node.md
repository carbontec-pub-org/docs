# Polymer testnet setup

## Requirements

Make sure your docker version is up to date.
Make sure you have opened and not bound 8575/TCP, and 30311/UDP ports with any other applications in order to communicate with the node via RPC endpoint(8575). Graphite nodes can also communicate with other nodes in the network through P2P (30311) Websocket modules available at the 8576 port. 
Make sure your network is not covered by NAT or any other network stuff.
Make sure you are logging into Carbontec public registry. In order to do that use the following command:

```bash
docker login https://registry.devgraphite.com
```
Now prompt will ask for credentials. We keep them private for now, contact developers to get yours.
Pull the latest docker image.

```bash
docker pull registry.devgraphite.com/polymer-testnet:amd64
```

Clean up old containers if needed.

```bash
docker rm --force polymer-testnet
```

Wipe the previous data folder if needed.

```bash 
sudo rm -rf /home/User/polymer-data && mkdir /home/User/polymer-data
```

### Anonymous entry-point node setup instructions.

To run a local docker node you’ll need to create a folder to persist data inside a container. In the following example this folder is located at  ```/home/User/polymer-data``` 

After creating the folder run the init task to inject genesis and persist it. Use the following command:

```bash
docker run -it -v /home/User/polymer-data:/var/lib/graphite/data registry.devgraphite.com/polymer-testnet:amd64 graphite --datadir /var/lib/graphite/data init /var/lib/graphite/genesis.json
```

Now you can run your node. Use the following command to initialize:

```bash
docker run -d --name polymer-testnet --network host -v /home/User/polymer-data:/var/lib/graphite/data registry.devgraphite.com/polymer-testnet:amd64 graphite --datadir /var/lib/graphite/data --config /var/lib/graphite/config.yaml
```

Check node sync progress with

```bash
docker logs polymer-testnet --follow
```

To interact with the node through Graphite JS console use 

```bash
docker exec -it polymer-testnet graphite attach /var/lib/graphite/data/geth.ipc
```

Node RPC API is available at ```http://127.0.0.1:8575```

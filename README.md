# Hydrachain Hydragon Testnet Docker Files

This repository contains Dockerfiles for creating and running a node for the Hydragon testnet of Hydrachain.

## Docker Images

### 1. Create a Node - `hydragon-base`

To create a Hydragon node, use the `hydragon-base` image.

#### Run the Image
```bash
docker run -it --name <name> -v $(cd ~/<local_directory> && pwd):/hydragon santoae/hydragon-base


This repository is for dockerfiles that create and run a node for Hydragon testnet of Hydrachain.


Create a node - hydragon-base 

To run the image : docker run -it --name < name > -v $(cd ~/< local directory >&& pwd):/hydragon santoae/hydragon-base
--replace < name > and < local directory > for your use case.

After running this container the configurations files will be in out < local directory >

Run a node : hydragon-node

To run the image : docker run -it -p 1478:1478 -p 8545:8545 -p 9632:9632 --name < name > --restart unless-stopped -v $(cd ~/< local directory >&& pwd):/hydragon santoae/hydragon-node
--replace < name > and < local directory > for your use case.

Interactive mode is needed to put the password (for now). Leave the container running with ctrl-p + crtl-q


If you need to interact with your node, running the following will open a local session, where you can execute any command:
docker exec -it $(sudo docker ps|grep "hydragon-node" | awk '{print ($1)}') bash

Check node status:
docker exec $(sudo docker ps|grep "hydragon-node" | awk '{print ($1)}') hydragon-node/hydra status
